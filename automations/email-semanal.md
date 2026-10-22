# Auto-task: E-mail de Update Semanal

## Descrição
Gera um rascunho de e-mail HTML com o update semanal de todos os projetos do PMO.

## Formato do e-mail

### Assunto
"📊 Update Semanal — PMO Returns & EHA (DD/MM)"

### Seções
1. **Números do portfólio** — total, em andamento, concluídos, help needed, ETA vencido, lead time médio, updates W-0
2. **Distribuição por estágio** — Discovery, Teste, Rollout, Concluído
3. **Distribuição por tipo** — Processo, Sistêmico, Equipamento, Malha
4. **Destaques e riscos** — avanços importantes e bloqueios
5. **Updates por estágio** — detalhamento por grupo
6. **Próximos marcos** — ETAs da próxima semana
7. **Dependências** — itens aguardando terceiros

### Regras
- Formato HTML (não plain text)
- Sem dados financeiros sensíveis no corpo
- E-mails que dão bounce são removidos da lista
- Versão atual: v4 (evolução desde set/2026)

## Destinatários
Lista mantida no Migoo (~30 pessoas entre Planning, Engenharia, Operações, Produto, Seller Ops). Não incluir neste arquivo por segurança.
