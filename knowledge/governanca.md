# Governança — Returns & EHA

## Cadências

### WBR (Weekly Business Review)
- **Frequência:** Semanal
- **Preparação:** Harllen consolida updates de todos os PICs
- **Fonte:** Planilha PMO (Summary PMO) + ClickUp

### E-mail de Update Semanal
- **Dia:** Quinta-feira
- **Formato:** HTML com seções: números do portfólio, distribuição por estágio/tipo, destaques/riscos, updates por estágio, marcos e dependências
- **Destinatários:** ~30 stakeholders (Planning, Engenharia, Operações, Produto, Seller Ops)
- **Regra:** e-mails que dão bounce são removidos da lista

### Auto-task: Update PMO Semanal
- **Gatilho:** Toda quinta (horário ajustável)
- **O que faz:** Cruza ClickUp + Planilha PMO e atualiza a coluna G ("Updates W-0") para todos os PICs
- **Fonte do ClickUp:** Tasks do space "PROJETOS - RETURNS" com comentários mais recentes

## Regras de status
- Projeto só é "Concluído" quando validado em produção
- "Help Needed" = flag no PMO indicando bloqueio que precisa de escalação
- ETA vencido = ETA < data atual sem conclusão

## Regras do Dashboard PMO
- Aba "🚀 Dashboard PMO" na planilha
- Tema escuro com laranja Shopee
- Fórmulas ligadas à Summary PMO (atualiza automaticamente)
- Colunas R a W não devem ser editadas manualmente

## Submissão de demandas (POP)
- Portal POP para solicitações ao time de Produto
- Campos obrigatórios: Request Name, Classification, Product Line, Business Case anexo
- Referência: guia "POP BR local module User Guide"
