# Security Recommendations

Configurações de segurança recomendadas:

## Approvals
- `approvals.mode: smart` (recomendado)
  - Usa LLM auxiliar para aprovar comandos de baixo risco automaticamente
  - Pede confirmação apenas em comandos destrutivos ou de alto risco

## Redação de segredos
- `security.redact_secrets: true`
  - Oculta automaticamente chaves de API, tokens e segredos antes de entrarem no contexto

## PII
- `privacy.redact_pii: false` (padrão)
  - Manter desativado a menos que haja necessidade específica de privacidade

## Regras gerais
- Nunca usar `--yolo` por padrão
- Sempre confirmar comandos destrutivos (rm, git reset --hard, etc.)
- Manter toolsets restritos quando possível (evitar browser + terminal juntos em sessões sensíveis)

## Comandos úteis
```bash
hermes config set approvals.mode smart
hermes config set security.redact_secrets true
hermes config set approvals.mode manual   # mais conservador
```