# Continuidade para agentes

1. Leia README.md e eha/CONTEXTO.md antes de alterar qualquer recurso.
2. No repositório do site, leia também AGENTS.md, apps-script/Code.gs e docs/OPERACAO.md.
3. Trate este material como contexto histórico: verifique o estado remoto antes de executar. Não suponha que uma aba, OAuth, permissão ou versão continua válida.
4. Atualize a cópia EHA Site — API Vercel. NÃO altere o projeto original PMO Projeto.
5. Preserve acesso Shopee Mobile; não publique a planilha, fotos, vídeo, código ou dados como solução de CORS. URL secreta não é controle de acesso.
6. Preserve Harllen Gomes, Kemily Serrudo, Rafael Ribeiro e Rafael Pinotti (gestor). Maria e Karine ficam fora da equipe, mas seus projetos históricos permanecem.
7. Preserve a URL do Apps Script: Gerenciar implantações → Editar → Nova versão. Não crie uma implantação nova a cada alteração.
8. HTML é servido de um arquivo privado no Drive. Alterar só o HTML não exige nova versão do backend. Alterar Code.gs exige salvar e publicar uma nova versão na implantação existente.
9. Não prometa atualizações instantâneas: consulta/cache de 60 segundos, sem mecanismo push.
10. Distinga teste estático, execução Apps Script, publicação e teste visual. Não declare hover, 3D, vídeo ou integração completa aprovados só porque o upload foi aceito.
11. Nunca reutilize credenciais da conversa, imprima segredos ou peça tokens pelo chat. Use o fluxo seguro disponível no ambiente atual.
12. Faça backup, mudanças mínimas, teste, confira a versão/URL e registre pendências. Em erro ou write incerto, reconcilie antes de repetir.
13. Explique em português, de forma direta: o que foi concluído, como acessar, o que falta e se o usuário precisa agir. Não sugira que há trabalho em segundo plano.
14. O GitHub não estava conectado a um deploy automático na última confirmação. Um commit não publica automaticamente Apps Script nem Vercel.

## Ambiente anterior (não assumir no novo agente)

Ferramentas usadas: arquivos locais, Node em WASM/WASIX, gws CLI para Drive, navegador explícito para Apps Script e Vercel. A API Apps Script via gws falhou por escopo insuficiente; o usuário solicitou o uso da interface web. No editor Monaco, inserir código de uma única linha e selecionar/apagar o conteúdo evitou duplicações/autoindentação. Cliques às vezes retornavam antes da UI atualizar: conferir estado e não repetir mutações incertas. O ambiente não tinha git ou gh instalados.
