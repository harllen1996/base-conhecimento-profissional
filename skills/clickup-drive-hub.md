# Skill: ClickUp + Drive Knowledge Hub

## O que faz
Integra ClickUp (via API) e Google Drive ao Migoo, permitindo que qualquer pessoa do time consulte em linguagem natural:
- Status de projetos e tasks
- PICs e responsáveis
- Dependências e bloqueios
- Tasks atrasadas
- Documentos do Drive

## Por que foi criada
- 30 pessoas no time, apenas 14 com licença do ClickUp
- Drive difícil de navegar sem saber a estrutura de pastas
- Bot anterior (Smart) não integrava com ClickUp

## Como funciona
1. Recebe uma pergunta em linguagem natural ("qual o status do projeto Faded?", "quem é o PIC do cubador?")
2. Consulta a API do ClickUp (space "PROJETOS - RETURNS")
3. Cruza com arquivos do Google Drive quando necessário
4. Retorna resposta estruturada

## Configuração
- **ClickUp workspace:** PROJETOS - RETURNS
- **Tipo de consulta:** apenas leitura (sem escrita)
- **Idioma de resposta:** Português (pt-BR)

## Triggers (palavras-chave)
- "status do projeto", "project status", "quais tasks"
- "quem é o PIC", "dependências", "buscar documento"
- "procurar no drive", "find document", "what's the status"
- "overdue tasks", "tarefas atrasadas"
