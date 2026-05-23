# Setup Verification & Missing Configurations

Durante o onboarding, o agente deve **verificar** o estado atual antes de pedir qualquer configuração.

## Processo recomendado

1. Executar comandos de verificação
2. Identificar o que **já está configurado**
3. Identificar o que **está faltando**
4. Perguntar apenas sobre os itens faltantes
5. Gerar resumo claro no final
6. Ler o README do projeto e salvar entendimento na memória (ver seção abaixo)

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

## Salvar Entendimento do Projeto na Memória (Passo Obrigatório)

Após carregar o repositório, o agente **deve**:

1. Ler o arquivo `README.md`
2. Entender o propósito e a estrutura do projeto
3. Salvar fatos importantes na memória persistente

Fatos que devem ser salvos:
- Este é o projeto de onboarding do Hermes Agent (`hermes-onboarding-template`)
- Local do repositório: `~/Documents/GitHub/hermes-onboarding-template`
- Finalidade: permitir onboarding rápido e consistente em novas instalações do Hermes
- Quando o usuário pedir "atualizar o projeto com os dados atuais", o agente deve ler os arquivos do repo e atualizar com informações da sessão atual
- O projeto contém arquivos que definem perfil do usuário, regras do agente, estratégias de modelo, segurança, etc.

Isso garante que em sessões futuras o agente já saiba exatamente o que fazer quando o usuário solicitar atualizações ou melhorias no projeto.

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