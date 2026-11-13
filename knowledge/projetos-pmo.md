# Projetos PMO — Returns & EHA

> Última sincronização com a aba "Summary PMO": 13/11/2026

## Visão Geral
- **Total no portfólio:** 49 projetos
- **Em andamento:** 30 (Wip 12 · With Products/Reg 14 · With Expansion 3 · Blocked 1)
- **Concluídos:** 15 · **Cancelados:** 4
- **Help Needed = Yes:** 5 (Aéreo Azul LAM, Aéreo Azul LRO, Aéreo Azul Fortaleza, 3PL XD, Reroute HD → SP)
- **Planilha fonte:** Google Sheets "PMO Projects RTS/EHA" (aba Summary PMO)
- **Acompanhamento:** WBR (Weekly Business Review) + e-mail semanal

### Distribuição por estágio
| Estágio | Qtde |
|---|---|
| 1. Iniciação | 1 |
| 2. Planejamento | 7 |
| 3. Desenvolvimento | 9 |
| 4. Validação | 16 |
| 5. Encerramento | 16 |

### Distribuição por tipo
| Tipo | Qtde |
|---|---|
| Melhoria | 22 |
| Feature | 14 |
| For vis | 13 |

### Distribuição por PIC
| PIC | Total | Em andamento | Concluídos | Cancelados |
|---|---|---|---|---|
| Rafael Mattos | 19 | 10 | 7 | 2 |
| Kemily Serrudo | 17 | 11 | 5 | 1 |
| Harllen Dias Gomes | 13 | 9 | 3 | 1 |

## Status utilizados na planilha
- **Wip** — em andamento, conduzido pelo time de Planning
- **With Products/Reg** — em andamento, dependente de Produto ou Regional
- **With Expansion** — em andamento, dependente do time de Expansão / PMO Aéreo
- **Blocked** — travado aguardando decisão/terceiro
- **Planning** — em planejamento/discovery
- **Done** — concluído (entregue e validado)
- **Cancelled** — descontinuado / congelado

## Estágios (pipeline)
- 1. Iniciação → 2. Planejamento → 3. Desenvolvimento → 4. Validação → 5. Encerramento

## Tipos de projeto
- **Melhoria** — melhoria de processo/fluxo operacional, equipamento ou malha
- **Feature** — desenvolvimento ou ajuste sistêmico com Produto
- **For vis** — projetos acompanhados para visibilidade (conduzidos com outras áreas)

## Projetos principais (destaques)

### Faded & Non-AWB (IA) — ✅ Concluído
- **O que faço:** Recupera pacotes com etiqueta apagada ou sem AWB via OCR + SKU matching com IA
- **Resultado:** +75.000 pacotes recuperados, +US$ 1.1M em ganho financeiro
- **Taxa de recuperação:** 29%
- **Continuidade:** governança de Faded Local em RJ02; projeto complementar "Órfãos - Complemento Faded" (Rafael Mattos) em validação em RJ02
- **PIC:** Harllen

### Cubadores Estáticos — 5. Encerramento · With Products/Reg
- **O que faço:** Medição automática de dimensões via laser (myCUBI)
- **Resultado:** 103 pph (5x mais que manual com trena)
- **Status:** integração concluída em 12 SOCs (SP02, ES02, SC01, RJ04, RJ01, SP08, SP06, SP24, PE02, PE04, MG02, BA02), todos aguardando aprovação de Seller Ops; bloqueio de conectividade com página da incubadora (~30% máquinas processadas); ETA 23/11
- **PIC:** Harllen

### Intercept to Measurement of SKUs — 4. Validação · With Products/Reg
- **O que faço:** Intercepta pacotes com divergência entre dimensão declarada e real
- **Status:** correções de CAP e interceptação implantadas no fim de outubro; teste retoma em 18/11 após campanha; bugs registrados em MyCubi, CAP, critérios de confiança e interceptação após packing
- **Desdobramento:** "Ajuste de dimensão de pacotes" (Rafael Mattos, 2. Planejamento)
- **PIC:** Harllen

### Impressoras Portáteis — 3. Desenvolvimento · With Products/Reg
- **O que faço:** Substitui PCs fixos por PDA + Zebra portátil para impressão
- **Cenário atual:** Turtle + computador → Zebra via Wi-Fi; limitante é o PDA
- **Cenário futuro:** foco do uso do equipamento em Super Bulky
- **Dependências:** Turtle Mobile, funcionalidades no SPX App, etiquetas HUB com fornecedor
- **PIC:** Harllen

### Aéreo Azul (Manaus / Rondônia / Fortaleza) — With Expansion
- **O que faço:** Modal aéreo para rotas longas de Returns
- **Manaus (LAM):** 5. Encerramento · ETA 30/11 — sem retorno do PMO Aéreo sobre blockers sistêmicos para produtos fora do perfil
- **Rondônia (LRO):** 4. Validação · ETA atualizado 30/11 — pendente estudo de processamento nos SOCs e push com Listings
- **Fortaleza (LCE):** 3. Desenvolvimento · ETA 12/11 — início adiado para 17/dez; impacto nas demais malhas em discussão
- **PICs:** Rafael (LAM, LCE), Kemily (LRO)

### Goleiros com HC EHA — 4. Validação · Wip
- **O que faço:** Substituição de goleiros por HC EHA, mini nurse e bipagem de pacotes na gaiola
- **Resultado:** -86% erro operacional (MG2 e SC1), +18%/6% produtividade no gaiola EHA
- **Próximos passos:** cronograma enviado; implementação em 2 waves; PR1 e PR4 iniciados em 02/11
- **PIC:** Rafael Mattos

### Salvados de Alto Valor — ✅ Concluído
- **O que faço:** Triagem por valor para recuperação de itens premium
- **Resultado:** taxa 18% → 60%
- **PIC:** Kemily Serrudo

### OTP to Seller — 3. Desenvolvimento · With Products/Reg
- **O que faço:** Código OTP para confirmação de entrega RTS ao seller
- **Status:** fluxo operacional pausado em 06/11 e retomado em 09/11; FM Wave 1 (100 sellers) em 16/11 e Wave 2 (500) em 23/11; LM 20 sellers em 10/11 e expansão para 134 elegíveis em 16/11; Turbo/Instant 100% ativo
- **PIC:** Harllen

### Stage In — 4. Validação · Wip
- **O que faço:** Planejamento de capacidade EHA / gestão de ocupação de docas com 4 zonas
- **Status:** projeto com 86% de conclusão; SP10, RJ04 e SP05 em stuck/atraso; 5 SOCs em preparação dentro do prazo (20/11): SP07, RJ06, SP18, SP25 e SP35
- **ETA:** 04/12/2026
- **PIC:** Rafael Mattos

### 3PL XD for RTS — 3. Desenvolvimento · With Products/Reg
- **O que faço:** Cross-dock via parceiro 3PL para Returns (SPX > 3PL > Correios)
- **Valor estimado:** R$ 122 mil
- **Status:** PRD de RTS/RR esperado para revisão em 13/11 e sign-off em 20/11; mapping de Correios pendente de validação com Produto; push com FP&A sobre forecast sem resposta
- **Help Needed:** Yes (retorno de Produto/FP&A)
- **PIC:** Kemily Serrudo

### [DS] Returns (RR e RTS HUB) — ✅ Concluído
- **O que faço:** LMH exclusivo para Returns entre os HUBs de Vila Guilherme e Lapa
- **Status:** finalizado pela frente de projetos; configuração de malha em 28/10 e alinhamento de volume de impacto em SP2, SP6, SP8 e SP25 concluídos
- **PIC:** Rafael Mattos

### Reroute HD → SP — 4. Validação · Wip · Help Needed
- **O que faço:** Após 3 tentativas de entrega sem sucesso, redireciona para retirada em PUDO/SVP, evitando RTS
- **Piloto:** Carandiru e Vila Guilherme
- **Taxa de retirada:** 64% (amostra 28/09–04/10: 16/25)
- **ETA:** 30/10/2026
- **PIC:** Harllen

### Site de Projetos EHA & Returns — ✅ Concluído
- **O que faço:** site do PMO que reúne o portfólio de projetos EHA e Returns (status, update semanal, links do Drive), integrado à aba Summary PMO e ao ClickUp
- **Recursos:** Help – Gestão, Bugs e Melhorias (formulário) e assistente de consulta
- **Status:** publicado e em uso desde 26/10/2026; acompanhamento finalizado
- **PIC:** Harllen

### Liquidation Improvements — 2. Planejamento · Wip
- **O que faço:** Melhoria contínua e tratamento de gaps do Liquidation Flow (puxados pela frente de Returns)
- **Status:** risco de operadores aplicarem liquidation em pacotes em movimentação reforçado; permissões EHA em discussão; validação com Malha pendente (ETA 12/11)
- **PIC:** Kemily Serrudo

## Lista completa de projetos

### Em andamento (30)

| Projeto | Tipo | Estágio | Status | PIC | ETA | Help Needed | KPI |
|---|---|---|---|---|---|---|---|
| Cubador estático | Melhoria | 5. Encerramento | With Products/Reg | Harllen | 23/11/2026 | No | Ticket Médio |
| Config ER FUA de acordo com station e role | For vis | 5. Encerramento | With Products/Reg | Kemily Serrudo | 07/08/2026 | No | Loss |
| Aéreo Azul - Manaus (LAM) | Melhoria | 5. Encerramento | With Expansion | Rafael Mattos | 30/11/2026 | Yes | Lead Time |
| G400 (WH SIP+CB+Lovito) | For vis | 4. Validação | Wip | Harllen | 31/12/2026 | No | Seller Satisfaction |
| Intercept to measurement of SKUs | Feature | 4. Validação | With Products/Reg | Harllen | 18/11/2026 | No | Produtividade EHA |
| Reroute HD → SP | Feature | 4. Validação | Wip | Harllen | 30/10/2026 | Yes | — |
| [Shopee Box] Locker BSC - Fluxo RTS | For vis | 4. Validação | With Products/Reg | Harllen | 31/01/2027 | No | Padronização |
| Aéreo Azul - Rondônia (LRO) | Melhoria | 4. Validação | With Expansion | Kemily Serrudo | 30/11/2026 | Yes | — |
| Double compensation Buyer | Melhoria | 4. Validação | Blocked | Kemily Serrudo | 16/07/2026 | No | Loss |
| Driver App / SP Interception | Feature | 4. Validação | With Products/Reg | Kemily Serrudo | 14/10/2026 | No | Total Open |
| Handover from 3pl RTS trigger | Melhoria | 4. Validação | With Products/Reg | Kemily Serrudo | 24/08/2026 | No | — |
| Migração RTS LMH para FMH | For vis | 4. Validação | Wip | Rafael Mattos | 21/08/2026 | No | — |
| Proof on Hold - Automatization | For vis | 4. Validação | With Products/Reg | Kemily Serrudo | 24/08/2026 | No | — |
| FTE 100% em EHA | For vis | 4. Validação | Wip | Rafael Mattos | 30/12/2026 | No | Produtividade EHA |
| Goleiros com HC EHA | Melhoria | 4. Validação | Wip | Rafael Mattos | 21/08/2026 | No | — |
| RR Pickup | For vis | 4. Validação | Wip | Kemily Serrudo | 03/08/2026 | No | — |
| Stage In | Melhoria | 4. Validação | Wip | Rafael Mattos | 04/12/2026 | No | Produtividade EHA |
| Órfãos - Complemento Faded | Melhoria | 4. Validação | Wip | Rafael Mattos | 20/11/2026 | No | — |
| Automate the identification and handle of Duplicated parcels | Feature | 3. Desenvolvimento | With Products/Reg | Harllen | 25/09/2026 | No | — |
| Impressoras Portáteis | Melhoria | 3. Desenvolvimento | With Products/Reg | Harllen | 09/09/2026 | No | Produtividade EHA |
| OTP to Seller | Feature | 3. Desenvolvimento | With Products/Reg | Harllen | 23/11/2026 | No | Salvados |
| Teste AMS | For vis | 3. Desenvolvimento | With Products/Reg | Harllen | 11/12/2026 | No | CPO |
| 3PL XD for RTS orders | Melhoria | 3. Desenvolvimento | With Products/Reg | Kemily Serrudo | 11/09/2026 | Yes | Lead Time |
| Aéreo Azul - Fortaleza | Melhoria | 3. Desenvolvimento | With Expansion | Rafael Mattos | 12/11/2026 | Yes | — |
| BRD - Digitalisation EHA Staging & Handover Process | Feature | 3. Desenvolvimento | With Products/Reg | Rafael Mattos | 16/11/2026 | No | Loss |
| Block the fullfillment order account in the liquidation flow | Feature | 2. Planejamento | With Products/Reg | Kemily Serrudo | 30/09/2026 | No | Salvados |
| Improvements 3PLs | Melhoria | 2. Planejamento | Wip | Kemily Serrudo | 16/10/2026 | No | Padronização |
| Ajuste de dimensão de pacotes | Melhoria | 2. Planejamento | Wip | Rafael Mattos | 20/11/2026 | No | — |
| Fechamento automático de TOs salvados por $ | Feature | 2. Planejamento | Wip | Rafael Mattos | 19/09/2026 | No | — |
| Liquidation Improvements | Melhoria | 2. Planejamento | Wip | Kemily Serrudo | — | — | — |

### Concluídos (15)

| Projeto | Tipo | Estágio | Status | PIC | ETA | Help Needed | KPI |
|---|---|---|---|---|---|---|---|
| Salvados de CB | Feature | 5. Encerramento | Done | Kemily Serrudo | 17/07/2026 | No | Salvados |
| Salvados Pet | For vis | 5. Encerramento | Done | Rafael Mattos | 02/07/2026 | No | Salvados |
| Nurse | Melhoria | 5. Encerramento | Done | Rafael Mattos | 31/05/2026 | No | Produtividade EHA |
| Tintas na Operação | Melhoria | 5. Encerramento | Done | Rafael Mattos | 02/07/2026 | No | Total Open |
| Salvados de Alto Valor | Melhoria | 5. Encerramento | Done | Kemily Serrudo | 18/06/2026 | No | Salvados |
| Salvados Own Flex | Feature | 5. Encerramento | Done | Kemily Serrudo | 02/06/2026 | No | Salvados |
| Faded and Non-AWB Recovery | Feature | 5. Encerramento | Done | Harllen | 03/06/2026 | No | Loss |
| AS Dimension | For vis | 5. Encerramento | Done | Harllen | 25/06/2026 | No | Ticket Médio |
| Dimensionador Portátil Zebra | Melhoria | 4. Validação | Done | Harllen | 19/06/2026 | No | Ticket Médio |
| Double compensation Seller | Melhoria | 5. Encerramento | Done | Kemily Serrudo | 24/06/2026 | — | — |
| Padronização pesca de BRs em sorters | Melhoria | 5. Encerramento | Done | Rafael Mattos | 21/08/2028 ⚠️ (provável erro de digitação na planilha) | No | — |
| Etiqueta SP06 > PHX | Melhoria | 5. Encerramento | Done | Kemily Serrudo | 21/08/2026 | No | — |
| Bulky Logs Pilot (Reversa TVs) | For vis | 5. Encerramento | Done | Rafael Mattos | 23/10/2026 | No | Ticket Médio |
| [DS] Returns (RR e RTS HUB) | For vis | 2. Planejamento | Done | Rafael Mattos | 29/10/2026 | No | Lead Time |
| Site de Projetos EHA & Returns | Melhoria | 5. Encerramento | Done | Harllen | 26/10/2026 | No | — |

### Cancelados (4)

| Projeto | Tipo | Estágio | Status | PIC | ETA | Help Needed | KPI |
|---|---|---|---|---|---|---|---|
| Order flow priority revert | Feature | 3. Desenvolvimento | Cancelled | Harllen | 30/09/2026 | No | Salvados |
| Smart RTS >> FWD | Feature | 1. Iniciação | Cancelled | Rafael Mattos | 22/04/2026 | No | CPO |
| BRD - Monitor Exception Order Update | Feature | 3. Desenvolvimento | Cancelled | Rafael Mattos | 07/05/2026 | No | Lead Time |
| Pacotes insucesso RR > Liquidating | For vis | 2. Planejamento | Cancelled | Kemily Serrudo | 03/08/2026 | No | — |

## Onde consultar o status atualizado
- **Planilha PMO:** aba "Summary PMO" (atualizada semanalmente)
- **ClickUp:** space "PROJETOS - RETURNS" (tasks detalhadas)
- **Site de Projetos EHA & Returns:** visão consolidada do portfólio, com Help – Gestão, Bugs e Melhorias
- **E-mail semanal:** enviado toda quinta para ~30 stakeholders
