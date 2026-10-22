# Auto-task: Update PMO Semanal

## Descrição
Atualiza automaticamente a coluna G ("Updates W-0") da planilha PMO com dados do ClickUp.

## Gatilho
- **Frequência:** Toda quinta-feira
- **Horário:** Ajustável (já foi 7h, 12h, 15:50)
- **Tipo:** Auto-task agendada (cron)

## Fluxo de execução
1. Consulta o ClickUp (space "PROJETOS - RETURNS") para cada projeto
2. Busca os comentários mais recentes das tasks
3. Cruza com a planilha PMO (aba Summary PMO)
4. Atualiza a coluna G com o update consolidado
5. Gera rascunho de e-mail semanal no Gmail

## Fontes de dados
- **ClickUp:** tasks e comentários do space PROJETOS - RETURNS
- **Google Sheets:** Planilha "PMO Projects RTS/EHA", aba "Summary PMO"

## Regras
- Atualiza para TODOS os PICs, não apenas os do Harllen
- Se um projeto não tem update no ClickUp, mantém o último update
- G400 (WH SIP+CB+Lovito) foi excluído do report (decisão de 24/09)
