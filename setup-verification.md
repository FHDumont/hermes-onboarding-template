# Setup Verification & Missing Configurations

Durante o onboarding, o agente deve **verificar** o estado atual antes de pedir qualquer configuração.

## Processo recomendado

1. Executar comandos de verificação
2. Identificar o que **já está configurado**
3. Identificar o que **está faltando**
4. Perguntar apenas sobre os itens faltantes
5. Gerar resumo claro no final
6. Popular os arquivos oficiais do Hermes usando os dados do repositório (ver seção abaixo)

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

## Popular Arquivos Oficiais do Hermes (Passo Obrigatório)

Após carregar o repositório, o agente deve popular os seguintes arquivos oficiais em `~/.hermes/`:

### 1. `SOUL.md`
- Conteúdo: Personalidade, tom e regras de comportamento do agente
- Fonte principal: `agent-persona.md` + `rules.md`

### 2. `USER.md`
- Conteúdo: Informações do usuário (nome, cargo, preferências, destaques)
- Fonte principal: `user-profile.md`

### 3. `MEMORY.md`
- Conteúdo: Fatos importantes que devem persistir (incluindo entendimento do projeto de onboarding)
- Fontes: `user-profile.md` + `multi-model-strategy.md` + fatos sobre o projeto

**Regra:**
- Os arquivos do repositório servem apenas como **fonte de dados**.
- O agente deve escrever nos arquivos oficiais (`SOUL.md`, `USER.md`, `MEMORY.md`).

## Regra importante

Nunca assumir que algo já está configurado.  
Sempre verificar primeiro e só solicitar configuração do que realmente estiver ausente.

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