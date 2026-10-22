# 📦 Base de Conhecimento — Returns & EHA

**SPX Express Brasil | Shopee**

Base unificada de conhecimento da área de Projetos de Returns e EHA. Projetada para ser consumida por qualquer agente de IA (Migoo, ChatGPT, Gemini, Claude, Seawork, Copilot) mantendo contexto consistente.

## 🗂 Estrutura

```
.
├── README.md                    # Este arquivo
├── knowledge/
│   ├── perfil-owner.md          # Perfil do dono da base (Harllen)
│   ├── projetos-pmo.md          # Os 47 projetos do PMO com status, PICs, KPIs
│   ├── stakeholders.md          # Stakeholders, reporting lines, times
│   ├── glossario.md             # Glossário operacional (BR, RTS, EHA, SOC, PIC...)
│   └── governanca.md            # Regras de governança, WBR, cadências
├── skills/
│   └── clickup-drive-hub.md     # Skill de integração ClickUp + Drive
├── automations/
│   ├── update-pmo-semanal.md    # Auto-task: atualização do PMO toda quinta
│   └── email-semanal.md         # Formato e regras do e-mail de update
├── templates/
│   ├── business-case.md         # Template de Business Case (padrão F Code)
│   ├── roteiro-video.md         # Roteiro de vídeo institucional
│   └── email-update.md          # Template do e-mail semanal
└── prompts/
    └── system-prompt.md         # Prompt de sistema para outras IAs
```

## 🚀 Como usar com outra IA

1. Copie o conteúdo de `prompts/system-prompt.md` como prompt de sistema
2. Referencie os arquivos de `knowledge/` conforme o contexto necessário
3. Para manter atualizado, os commits refletem mudanças reais nos projetos

## 📋 Fontes de dados

- **ClickUp:** space "PROJETOS - RETURNS" (via API key)
- **Google Drive:** pastas compartilhadas de Returns & EHA
- **Planilha PMO:** Google Sheets com 47 projetos (Summary PMO + WBR)
- **Migoo:** memórias e automações acumuladas desde set/2026

## ⚠️ Nota de segurança

Este repositório NÃO contém dados financeiros sensíveis, e-mails de destinatários ou API keys. Esses dados vivem apenas nas ferramentas autorizadas (Migoo, ClickUp, Google Workspace).
