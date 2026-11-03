---
name: ep01-flow-pipeline
description: "Pipeline do EP01 do Canal Finanças: narração aprovada -> imagens no Google Flow 16:9 -> download via canvas + servidor local -> Ken Burns -> mix -14 LUFS."
---

# Canal Finanças — pipeline EP01 (narração aprovada -> vídeo final)

Objetivo: dado um roteiro com narração já aprovada (audio/raw/narracao_cena_XX.mp3 + audio/raw/audio_voiceover_elevenlabs.wav), produzir o MP4 final com visuais gerados no Flow.

## Passo a passo

1. **Inventário**: confirme que existem por cena narracao_cena_01..13.mp3 e o voiceover completo; meça a duração de cada cena (ffprobe). A soma deve fechar com o voiceover.
2. **Prompts do Flow** (1 por cena, em pt-BR): "imagem 16:9, estilo editorial dark — fundo grafite, textura de jornal, marca-texto amarelo neon" com o conteúdo de cada cena. Uma imagem por cena.
3. **Gerar no Flow** (navegador persistente openbot_browser): abrir o projeto do Flow correspondente (ou criar um novo) e colar o pedido completo com todas as cenas; 1 geração, modelo Nano Banana 2.x. Aguardar "Todas as N imagens ... foram geradas".
4. **Baixar as imagens do Flow** (o pulo do gato — não existe download direto):
   a. Criar um servidor HTTP local mínimo em Python (upload_server.py) que aceita POST com X-Filename e salva em pasta de destino; bind 127.0.0.1:8457; CORS Access-Control-Allow-Origin: *.
   b. No openbot_browser.evaluate, rodar JS que busca cada <img> cujo src contém /asb/, desenha num canvas 1024px de largura, exporta toDataURL('image/jpeg', 0.65) e faz fetch('http://127.0.0.1:8457/imgN.jpg', {method:'POST', headers:{'X-Filename':'flow_N.jpg','Content-Type':'image/jpeg'}, body: bytes}).
   c. Confirmar os arquivos no disco; **matar o processo do servidor** ao final.
   d. Identificar qual imagem é qual cena (pela ordem do DOM) e renomear para cena_XX.jpg em assets/graphics/.
5. **Uma imagem que falhar ou faltar**: gerar no Higgsfield soul_2 (plano grátis, 1 job por vez) ou usar asset existente; nunca inventar conteúdo factual.
6. **Montagem** (build_v4.ps1 de referência no projeto canal-financas/ep01-economia-brasil/):
   - por cena: scale=2200:1238:force_original_aspect_ratio=increase,crop=1920:1080,zoompan=z='min(zoom+0.0009,1.17)':d=<frames@60fps>:s=1920x1080:fps=60, preset veryfast, crf 20;
   - concat (-f concat -safe 0 -c copy);
   - mix: [voiceover][bgm(loop, volume 0.22)]amix=inputs=2:duration=first:weights='1.0 0.22',loudnorm=I=-14:TP=-1.0:LRA=11;
   - output render/epNN_FINAL_flow.mp4 1080p/60fps; verificar com ffprobe + ebur128/loudnorm.
7. **BGM**: faixa da library local (audio/bgm/library/dark_times.wav, loopada); nunca o stem sintético como trilha final. **SFX**: só se houver SFX reais.
8. **Entrega**: anexar o MP4; relatar LUFS/TP reais, duração e custo.

## Verificação
- ffprobe: 1920x1080, h264, 60 fps, duração ~= soma das cenas; loudnorm ~-14 LUFS (+/-0,5), TP <= -1,0 dBTP.
- Checar 1 frame do meio do vídeo para confirmar ordem das cenas.

## Armadilhas
- Download de imagens do Flow NÃO funciona com Invoke-WebRequest/curl — URLs flow.google.com/asb/... exigem a sessão; usar sempre o canvas + servidor local.
- openbot_browser.evaluate trunca resultados >64 KB — nunca trazer base64 pelo tool; usar o POST direto para o servidor local.
- master.py quebra no loudnorm em algumas máquinas (ffmpeg sem ffprobe no PATH); usar o ffprobe do Remotion em node_modules/@remotion/compositor-win32-x64-msvc/ffprobe.exe e rodar loudnorm manual.
- Não publicar nem enviar a ninguém sem aprovação.

## Caso de referência (EP01, 2026-11-03)
- Narração ElevenLabs 9min44s já aprovada; 12 cenas geradas no Flow (projeto "nov. 03 - 14:48"); cena 9 (navios) via Higgsfield soul_2 (~1 crédito); custo extra ~R$ 0.
- Resultado: ep01_FINAL_v4_flow.mp4, 1080p/60fps, -14,55 LUFS, TP -0,79 dBTP, pasta render/.
