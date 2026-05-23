# Hermes Onboarding Template

Este repositório contém dados de referência para fazer onboarding rápido e padronizado no Hermes Agent.

## Regras Importantes do Onboarding

- Os arquivos deste repositório são **apenas referência**.
- O agente deve ler os arquivos, extrair as informações e guardar usando os mecanismos oficiais do Hermes (`memory` + `SOUL.md`).
- **Nunca criar** USER.md nem MEMORY.md.
- SOUL.md é o arquivo oficial de personalidade.
- Os dados do repositório servem apenas para o agente saber quem ele é, quem você é e quais configurações aplicar.

## Fluxo Obrigatório do Onboarding

O onboarding **só avança** quando as etapas abaixo forem concluídas.

### Passo 1 - Localização do Projeto (Obrigatório)

O repositório deve ficar no **home real do usuário**, nunca dentro da estrutura do Hermes (`~/.hermes`).

**Caminho padrão recomendado:**

- **macOS:** `~/Developer/GitHub/hermes-onboarding-template`
- **Linux:** `~/Developer/GitHub/hermes-onboarding-template`

**Regras importantes:**
- O caminho deve ser resolvido para o diretório real do usuário (ex: `/Users/seuusuario/Developer/GitHub/...`)
- **Nunca** deixar o repositório dentro de `~/.hermes/profiles/...`
- Dar opção clara de manter ou alterar o caminho
- **Não continuar** enquanto o usuário não confirmar o caminho final
- Após definir o caminho, mostrar o caminho **absoluto** completo para confirmação

### Passo 2 - Nome do Agente (Obrigatório)
- Perguntar: "Qual nome você quer me dar?"
- **Não continuar** enquanto o usuário não definir o nome

### Passo 3 - Aplicar Configurações
- Ler os arquivos de referência
- Atualizar `SOUL.md` com persona + regras
- Salvar dados de perfil e preferências via `memory`
- Aplicar recomendações de segurança e toolsets
- Verificar e configurar provedores de modelo (multi-model strategy)

### Finalização
O onboarding **só pode ser finalizado** quando:
- Todos os passos recomendados forem concluídos, **ou**
- O usuário disser explicitamente "finalizar onboarding"

Ao finalizar, mostrar:
- Resumo do que foi configurado (usar tabela de status)
- Mensagem de boas-vindas personalizada

## Estrutura do Repositório

- `user-profile.md` → Referência para dados do usuário
- `agent-persona.md` + `rules.md` → Referência para SOUL.md
- `multi-model-strategy.md` → Preferências de modelo (obrigatório verificar)
- `security.md` → Recomendações de segurança
- `toolsets.md` → Toolsets recomendados
- `skills.md` → Skills sugeridas
- `setup-verification.md` → Fluxo detalhado de verificação

## Exemplo de Tabela de Pendências

Usar sempre este formato enquanto houver itens pendentes:

| Provedor       | Status             | Observação                          |
|----------------|--------------------|-------------------------------------|
| Grok (xAI)     | ✅ Configurado     | Modelo atual                        |
| Claude         | ❌ Não configurado | Anthropic API key ausente           |
| OpenRouter     | ❌ Não configurado | -                                   |
| Ollama         | ❌ Não configurado | Precisa instalar + configurar       |
| AWS Bedrock    | ✅ Parcial         | Funciona via IAM role               |

## Observação

Este template é específico para Fernando (Solutions Architect - Splunk/Cisco - Observabilidade).
