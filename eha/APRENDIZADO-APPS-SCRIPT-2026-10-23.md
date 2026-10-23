# Aprendizado: publicação do site EHA no Google Apps Script

Registro de continuidade baseado nos arquivos locais de 23/10/2026. As evidências descrevem uma publicação anterior; o estado online deve ser conferido antes de qualquer nova alteração.

## Arquitetura

1. O web app corporativo do Google Apps Script atende pela URL `/exec`.
2. `doGet()` usa `HtmlService` para entregar um HTML compilado guardado em arquivo privado no Google Drive.
3. O frontend consulta `google.script.run.getEhaData()` para receber projetos, links, detalhes de Help, bugs e referências de formulário.
4. O backend lê as fontes autorizadas, incluindo Google Sheets e integrações opcionais, e aplica cache de aproximadamente 60 segundos.
5. O acesso é restrito ao domínio corporativo configurado. A execução ocorre como o proprietário do script.

## Como atualizar com segurança

1. Confirmar projeto, implantação, versão, permissões e URL atuais. Trabalhar na cópia EHA, preservando o PMO original.
2. Salvar backup do HTML do Drive e, quando possível, de todos os arquivos e manifesto do Apps Script.
3. Comparar o novo HTML e o backend com a versão em uso. Preservar `doGet()`, `getEhaData()`, título, favicon e integração nativa.
4. Validar sintaxe e fluxo de resposta com testes locais. Distinguir testes simulados de execução real.
5. Se o backend mudar, salvar o código no editor, recarregar e confirmar persistência. Executar função de teste selecionada e verificar logs.
6. Atualizar o conteúdo do mesmo arquivo HTML no Drive. Conferir ID, tamanho e checksum da resposta.
7. Se o backend mudar, usar **Implantar → Gerenciar implantações → Editar → Nova versão**, preservando a implantação e sua URL `/exec`.
8. Abrir a URL oficial, considerar o cache de 60 segundos e conferir conteúdo, abas, links e acesso corporativo.

Uma mudança apenas no HTML do Drive pode aparecer sem nova versão do backend, porque `doGet()` lê esse arquivo dinamicamente. Por isso, frontend e backend precisam permanecer compatíveis durante a atualização.

## Resultado registrado em 23/10/2026

- As evidências locais registram a versão 4 publicada na implantação existente.
- HTML atualizado no mesmo arquivo do Drive e checksum conferido.
- Backend salvo e confirmado após recarga do editor.
- Execução real de `doGet()` concluída sem erro.
- Página oficial abriu com menu novo e indicador visual de fonte ativa.
- Testes locais de sintaxe e RPC simulado passaram.

Esses registros **não comprovam** teste exaustivo de todas as abas, links, cenas 3D, vídeo, dispositivo móvel físico ou correção de todos os dados. A função `testPayload` não foi executada na operação registrada.

## Limitações e cuidados

- A API do Apps Script retornou `403 insufficient authentication scopes` no ambiente anterior. A edição foi concluída pela interface web, após solicitação do usuário.
- Não há atualização instantânea: consulta e cache usam intervalo de 60 segundos, sem mecanismo push.
- O frontend recebido era HTML/JavaScript compilado. Não havia projeto-fonte React para recompilar.
- O adaptador usado era específico para o bundle recebido e verificava ocorrências únicas antes de substituir trechos. Uma compilação diferente exige nova análise.
- ClickUp e enriquecimento de pastas Drive eram opcionais e não tiveram cobertura completa certificada.
- A reversão pode exigir restaurar tanto o HTML no Drive quanto a versão do Apps Script; reverter só o backend não restaura o HTML automaticamente.
- Um commit GitHub registra conhecimento, mas não publica o Apps Script. Não havia pipeline automático confirmado.
- Nunca enviar ao repositório público HTML com dados corporativos, `Code.gs` interno, fotos, vídeos, IDs privados, tokens, cookies ou logs de autenticação.

## Fontes do registro

- `ATUALIZACAO-APPS-SCRIPT-2026-10-23.md`
- `GUIA-ATUALIZACAO-APPS-SCRIPT.md`
- `eha-CONTEXTO.md`
- Pacote interno: `validation.json`, `deployment-after.json`, `drive-update-result.json`, `mock-validation.json` e `LEIA-ME.md`

Os arquivos internos permanecem fora deste registro público.
