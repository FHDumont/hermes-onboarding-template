# Setup Verification & Missing Configurations

Durante o onboarding, o agente deve **verificar** o estado atual antes de pedir qualquer configuração.

## Processo recomendado

1. Executar comandos de verificação
2. Identificar o que **já está configurado**
3. Identificar o que **está faltando**
4. Perguntar apenas sobre os itens faltantes
5. Gerar resumo claro no final

## Comandos de verificação

```bash
hermes config
hermes tools list
hermes doctor
hermes model
```

## Itens que devem ser verificados

### Providers / Modelos
- Grok (xAI)
- Claude (Anthropic)
- Ollama (local)
- Hugging Face
- Outros provedores configurados

**Pergunta padrão:**
"Deseja configurar [provedor]?"

Só perguntar se o provedor **não** estiver configurado.

### Segurança
- `approvals.mode`
- `security.redact_secrets`

**Perguntas:**
- Deseja configurar `approvals.mode`? (opções: manual, smart, off)
- Deseja ativar redação automática de segredos?

### Memory
- Provider atual de memória
- Se `user_profile_enabled` está ativo

### Toolsets
- Quais toolsets estão habilitados vs desabilitados

## Resumo esperado

No final da verificação, o agente deve apresentar algo como:

**Configurado:**
- Grok
- Memory (built-in)
- Toolsets principais

**Faltando configurar:**
- Claude → pedir API key
- Ollama → confirmar se está rodando + modelo
- Segurança (`approvals.mode` e `redact_secrets`)

## Regra importante

Nunca assumir que algo já está configurado.  
Sempre verificar primeiro e só solicitar configuração do que realmente estiver ausente.