# Setup Verification & Onboarding Flow

Durante o onboarding, o agente deve seguir rigorosamente este fluxo.

## Fluxo Obrigatório (não pular etapas)

### 1. Localização do Projeto (Passo Obrigatório)
- Caminho padrão: `~/Developer/Github/<nome-do-projeto>`
- Perguntar ao usuário se deseja manter ou alterar o caminho
- **Não continuar** enquanto o usuário não confirmar o caminho final

### 2. Nome do Agente (Passo Obrigatório)
- Perguntar: "Qual nome você quer me dar?"
- **Não continuar** enquanto o usuário não definir o nome do agente

### 3. Verificação de Estado Atual
Executar comandos de verificação:
```bash
hermes config
hermes tools list
hermes doctor
hermes model
```

Identificar o que já está configurado vs o que está faltando.

### 4. Aplicar Dados do Onboarding (usando referências)

Os arquivos deste repositório servem **apenas como referência**. O agente deve:

- Ler `agent-persona.md` + `rules.md` → Atualizar `SOUL.md` (arquivo oficial)
- Ler `user-profile.md` → Guardar via ferramenta `memory` (user profile)
- Ler `multi-model-strategy.md` → Guardar preferências de modelo via memory
- Ler `security.md` → Aplicar configurações de segurança (approvals.mode, redact_secrets)
- Ler `toolsets.md` → Sugerir ativação dos toolsets recomendados

**Regra importante:** Nunca criar arquivos USER.md ou MEMORY.md. Usar apenas os mecanismos oficiais do Hermes.

### 5. Finalização do Onboarding

O onboarding **só pode ser finalizado** quando:
- Todos os passos obrigatórios (1 e 2) foram concluídos, **ou**
- O usuário disser explicitamente "finalizar onboarding" ou "pode finalizar"

**Antes de finalizar automaticamente**, o agente deve sempre verificar se existe alguma pendência (configurações de segurança, toolsets, provedores, etc.). Se houver pendências, elas devem ser apresentadas ao usuário antes de concluir.

Ao finalizar, apresentar:

**Resumo do que foi feito:**
- Caminho do projeto definido
- Nome do agente definido
- SOUL.md atualizado
- Dados de perfil salvos via memory
- Configurações de segurança aplicadas (se aceitas)
- Toolsets recomendados sugeridos

**Mensagem de boas-vindas** personalizada.

## Itens que devem ser verificados

### Providers / Modelos
- Grok (xAI)
- Claude (Anthropic)
- Ollama (local)
- Outros provedores

Só perguntar configuração se o provedor **não** estiver configurado.

### Segurança
- `approvals.mode` (recomendado: smart)
- `security.redact_secrets` (recomendado: true)

### Memory
- Verificar se memory está ativo

### Toolsets
- Sugerir ativação dos toolsets listados em `toolsets.md`

## Resumo esperado ao finalizar

**Configurado com sucesso:**
- Localização do projeto
- Nome do agente
- Personalidade (SOUL.md)
- Perfil do usuário (memory)
- Estratégia multi-modelo
- Recomendações de segurança

**Boas-vindas:** "Bem-vindo de volta, Fernando. Seu Hermes está configurado e pronto para trabalhar com você."