# Projetos Returns & EHA — contexto e transferência

## Objetivo e preferências

Harllen está construindo o site interno de Projetos Returns & EHA / Shopee SPX Brasil. Quer manter a home limpa, os projetos e o histórico, com equipe apenas Harllen Gomes, Kemily Serrudo e Rafael Ribeiro; Rafael Pinotti aparece como gestor, sem exigir entregas próprias. Remover Maria e Karine da apresentação de equipe não significa apagar seus projetos entregues. Fotos da equipe foram incorporadas como data URI no HTML.

O usuário prefere execução direta pelo agente, poucos pedidos de capturas de tela e explicações claras sobre ações realmente necessárias. Não dizer “estou fazendo” se a execução parou.

## Arquitetura atualmente publicada (última confirmação)

```text
Visitante autenticado no domínio Shopee Mobile
  → Apps Script Web App /exec (doGet → HtmlService)
      → arquivo HTML privado no Drive
      → navegador chama google.script.run.getEhaData()
          → SpreadsheetApp lê Summary PMO
          → JSON com projects / clickup / updatedAt
```

- Página: React e CSS já compilados em HTML autossuficiente; fonte original JSX/projeto npm não foi disponibilizada. Não inventar uma pipeline de build.
- - A versão enviada pelo usuário usava fetch de endpoint; foi adaptada para google.script.run para não depender de cookies corporativos no servidor da Vercel.
  - - doGet serve a página; getEhaData retorna JSON como string. Funções auxiliares terminadas em `_` ficam internas ao Apps Script.
    - - Cache de dados: 60s, chave `eha-explicacao-v3`; consulta inicial, a cada 60s se visível e ao retornar à aba. A versão enviada tinha cache de 600s: mantivemos 60s para preservar atualização anterior.
      - - HTML não é gravado dentro do editor: Apps Script lê o arquivo do Drive. Isso evitou colar cerca de 2,8 MB no Monaco.
        - - Execução como Harllen; acesso configurado para “Qualquer pessoa em Shopee Mobile”. Qualquer usuário elegível do domínio pode ver os dados apresentados usando a autorização de Harllen, mesmo sem acesso direto à planilha. Não afirmar que é restrito apenas a três integrantes.
         
          - ## Recursos e separação de ambientes
         
          - | Recurso | Referência | Estado conhecido |
          - |---|---|---|
          - | Projeto Apps Script da cópia | `1lvlNcx4kQxlxXsbkfhTi3G1mvsqL0eYqh6pkych_-jyfogb0rR3NGSyK` | EHA Site — API Vercel; nome legado, hoje hospeda site |
          - | Implantação ativa | `AKfycbzbzKjwGq0nHJLhzgkvSY__TjkizxCIZ8FuiysKkLnv73kXAKjBFFOsvj1jsIXxrWEn` | Versão 2 confirmada em 21/10/2026, 09:37 America/Sao_Paulo |
          - | HTML no Drive | `162dAoxt-lW0eZ2rg8vzfSBg1hsie1Wnb` | eha-apps-script-teste.html; atualizado sem mudar ID |
          - | Planilha | `1WLxSHNkjrCMxqi-PgZawJ_b6eDLNM5O4dGe2MPa4ksU` | aba Summary PMO; leitura do script testada |
          - | Vídeo usado | `1zNuE0ZGuNB2LqPdAqZ3IWNsaRTB8eN1O` | Video final - EHA.mp4; upload de cópia, 50s H.264/AAC, ~29,9MB |
          - | PMO original — NÃO ALTERAR | `1-yX7fylW5sgBmjsRgfCKZe-KHj58bbm3z1QO0-1KnBzYJRmC-kqSImWn` | Outro sistema PMO Returns Control Tower, arquivos/versão próprios |
          - | Vercel | eha4 / eha-inicial-seguro | Site alternativo, não atualizado nas últimas mudanças de Apps Script |
         
          - Site: https://script.google.com/a/macros/shopee.com/s/AKfycbzbzKjwGq0nHJLhzgkvSY__TjkizxCIZ8FuiysKkLnv73kXAKjBFFOsvj1jsIXxrWEn/exec
         
          - Editor da cópia: https://script.google.com/home/projects/1lvlNcx4kQxlxXsbkfhTi3G1mvsqL0eYqh6pkych_-jyfogb0rR3NGSyK/edit
         
          - Vercel: https://eha-inicial-seguro.vercel.app/
         
          - ## Por que Apps Script, e não só Vercel
         
          - O site foi inicialmente empacotado e publicado na Vercel pelo usuário. Um handler `/api/projects` faria POST com token ao Apps Script. As variáveis APPS_SCRIPT_URL/EHA_API_TOKEN não foram configuradas e o endpoint retornava 503. A conta corporativa oferecia apenas “Somente eu” ou “Qualquer pessoa em Shopee Mobile”, sem acesso anônimo; o servidor Vercel não herda o login Google do visitante.
         
          - O usuário confirmou que o público é corporativo e pediu uma cópia hospedada no Apps Script. Isso evita o desenho Vercel → endpoint com login interativo. Não resolver publicando a planilha nem tratando /exec como senha.
         
          - A Vercel tinha Vercel Authentication para All Deployments, e requisições anônimas à home e API redirecionavam para login no teste realizado. Esse controle é separado de login Shopee Mobile; não afirmar que restringe automaticamente ao domínio Shopee. Verificar estado atual antes de usar.
         
          - ## Histórico funcional
         
          - 1. Ajustes de equipe/fotos, preservação de projetos e home.
            2. 2. Pacote estático Vercel com jogo.html, vercel.json e API server-side; upload manual pelo usuário, sem pipeline GitHub.
               3. 3. Integração separada Apps Script criada, planilha autorizada e leitura testada, evitando modificar PMO original.
                  4. 4. Cópia do site passou a ser servida pelo Apps Script via arquivo HTML privado do Drive.
                     5. 5. Vídeo incluído como embed Drive na home. O usuário avisou que já havia uma cópia no próprio Drive, mas a página usa o ID acima que foi enviado pelo agente. Não buscar/apagar outros vídeos automaticamente.
                        6. 6. Primeiro 3D da cubadora incluído em modal grande e responsivo, com simulação de medidas/peso. Arquivo isolado cubadora-3d.html preservado como referência.
                           7. 7. O usuário enviou uma nova versão completa do site e Code.gs, com coluna Explicação, hover 3D, updates e galeria. Essa versão substituiu o modal exclusivo anterior e foi adaptada ao Apps Script corporativo, mantendo equipe/fotos/vídeo.
                             
                              8. ## Versão Explicação 3D
                             
                              9. Comportamento do código recebido (não confundir com teste visual independente):
                              10. - Coluna Explicação após Projeto. Update fica desmarcado por padrão, reativável em Colunas; preferências anteriores do navegador podem persistir.
                                  - - Popup com cena à esquerda e status/PIC/estágio/ETA/updates à direita; W-1 se diferente, W-0 ou W indicado conforme origem.
                                    - - Hover muda a cena; mantém aberto ao entrar no popup; toque no celular; Esc fecha.
                                      - - Botões Detalhes e Abrir 3D completo; galeria Projetos 3D mantida.
                                        - - Cena em iframe gerado a partir de HTML base64 embutido; carregamento preguiçoso e troca por postMessage.
                                          - - `sceneFor_` normaliza caixa e acentos e associa palavras-chave; retorno vazio é “sem 3D”.
                                            - - `testScenes` lê a planilha e registra associação de cada projeto.
                                             
                                              - ### Evidências verificadas
                                             
                                              - - testScenes executado no editor: 47 associações não vazias, execução concluída (21/10/2026 09:35:50–09:35:52).
                                                - - Mapa estático do site: 47 nomes; comparação com sceneFor_ não teve diferenças, inclusive fullfillment/Handover Process/3pl.
                                                  - - Sintaxe dos scripts de HTML e backend verificada com Node.
                                                    - - Upload HTML confirmado por checksum MD5 `5db788ed01610b0d2c3d4ff15b3418e3`, tamanho 2.858.270 bytes (snapshot dessa versão).
                                                      - - Gerenciar implantações confirmou versão 2 e mesma URL.
                                                        - - Navegação à URL publicada retornou título Projetos Returns & EHA; ferramenta sem acesso semântico ao conteúdo do iframe.
                                                          - - Em versão anterior houve captura mostrando home renderizada. Isso não comprova hover 3D da versão nova.
                                                           
                                                            - ### Pendências e limites reais
                                                           
                                                            - - Teste visual ponta a ponta de hover/troca de projeto/drag/zoom/Esc/celular da versão Explicação não realizado pelo agente. O usuário relatou testes próprios no HTML, mas agente não deve atribuí-los a si.
                                                              - - Vídeo: player apareceu, mas Drive ainda processava no teste. Reprodução final e permissão para colegas não foram verificadas; originalmente arquivo privado. Não dizer que foi compartilhado com domínio.
                                                                - - ClickUp: sem token/lista configurados no trabalho. Retorna []; snapshot antigo do site não é prova de dados ao vivo. Comentários limitados por CLICKUP_COMMENT_LIMIT (0 padrão, até 10) para evitar fanout de até 60 chamadas por atualização. Endpoint atual lê só primeira página e tasks.slice(0,60), não é cobertura exaustiva.
                                                                  - - Drive: enriquecimento de links só ocorre com DRIVE_FOLDER_ID. Não configurado/testado. Varredura de subpastas pode exigir revisão de limite antes de ativar.
                                                                    - - Código contém snapshots de dados corporativos. Não torná-lo público, mesmo se a planilha estiver privada.
                                                                      - - GitHub sozinho não cria atualização automática do Apps Script. Pipeline ainda não configurada.
                                                                       
                                                                        - ## Como continuar
                                                                       
                                                                        - Veja docs/OPERACAO.md no repositório do site para atualização do HTML, Code.gs, implantação, testes e rollback. Antes de alterações, ler remoto/confirmar versão e salvar backup. Nunca substituir PMO original. Preservar ID do HTML e deployment para manter URL.
                                                                        - 
