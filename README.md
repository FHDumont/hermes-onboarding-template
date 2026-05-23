# Hermes Onboarding Template

Este repositório contém dados de referência para fazer onboarding rápido e padronizado no Hermes Agent.

## Regras Importantes do Onboarding

- Os arquivos deste repositório são **apenas referência**.
- O agente deve ler os arquivos, extrair as informações e guardar usando os mecanismos oficiais do Hermes (principalmente a ferramenta de memory + SOUL.md para personalidade).
- **Não criar** USER.md nem MEMORY.md (não fazem parte da estrutura oficial).
- SOUL.md **é oficial** e pode ser atualizado com base nos dados de persona + rules.

## Como usar

1. Clone o repositório
2. Diga para o Hermes: "fazer onboarding conforme repo ~/Developer/Github/hermes-onboarding-template"
3. O agente seguirá o fluxo obrigatório abaixo.

## Fluxo Obrigatório do Onboarding

O onboarding **só avança** se as seguintes etapas forem concluídas:

### Passo 1 - Localização do Projeto
- Perguntar o caminho padrão: `~/Developer/Github/<nome-do-projeto>`
- Dar opção de manter ou alterar o caminho
- **Não continuar** enquanto o usuário não confirmar o caminho

### Passo 2 - Nome do Agente
- Perguntar: "Qual nome você quer me dar?"
- **Não continuar** enquanto o usuário não definir o nome

### Passo 3 - Aplicar Configurações
- Ler os arquivos de referência
- Atualizar SOUL.md com persona + regras
- Salvar dados de perfil e preferências via memory tool
- Aplicar recomendações de segurança e toolsets

### Finalização
- O onboarding só pode ser finalizado quando todos os passos obrigatórios forem concluídos **ou** o usuário disser explicitamente para finalizar.
- Ao finalizar, mostrar:
  - Resumo do que foi configurado
  - Mensagem de boas-vindas

## Estrutura do Repositório

- `user-profile.md` → Referência para dados do usuário (guardar via memory)
- `agent-persona.md` + `rules.md` → Referência para SOUL.md
- `multi-model-strategy.md` → Preferências de modelo
- `security.md` → Recomendações de segurança
- `setup-verification.md` → Fluxo detalhado de verificação
- `toolsets.md` → Toolsets recomendados
- `skills.md` → Skills sugeridas
- `config-snippets/` → Exemplos de configuração

## Observação

Este template é específico para Fernando (Solutions Architect - Splunk/Cisco - Observabilidade).