# Multi-Model Strategy

Este arquivo é **referência** do que o usuário deseja ter disponível.

## LLMs desejados


| LLM          | Prioridade  | Como configurar                     | Quando usar                                    | Status atual       |
| ------------ | ----------- | ----------------------------------- | ---------------------------------------------- | ------------------ |
| Grok (xAI)   | Principal   | Via xAI OAuth e API                 | Tarefas gerais e orquestração                  | Subscription + API |
| Cursor       | Fundamental | IDE externo                         | Edição pesada de código e desenvolvimento      | Subscription + API |
| Claude       | Alta        | Anthropic API key                   | Raciocínio complexo, revisão e código complexo | Subscription + API |
| OpenAI       | Média       | OpenAI API key                      | Tarefas gerais / fallback                      | API                |
| Groq         | Alta        | Groq API key (free tier disponível) | Tarefas rápidas e baratas                      | Modelo free        |
| Ollama       | Opcional    | Instalar localmente                 | Tarefas simples (economia de tokens)           | Local              |
| Hugging Face | Opcional    | Via API ou local                    | Modelos open-source                            | -                  |


## Regras de Uso

- Hermes é o orquestrador principal.
- Edição pesada de código → priorizar **Cursor**.
- Raciocínio complexo ou código muito elaborado → sugerir **Claude**.
- Tarefas simples e rápidas → priorizar **Groq** ou **Ollama** quando disponível.
- Sempre verificar o status atual antes de oferecer configuração.

## Durante o Onboarding

**Regra importante:** Durante o onboarding o agente **não sabe** o que já está configurado. Por isso deve sempre seguir este fluxo:

O agente deve:

- Verificar o status real de cada LLM usando `hermes doctor`, `hermes config`, `hermes model`, etc.
- Mostrar tabela clara com o que está pendente
- Oferecer configurar **apenas** o que o usuário ainda não configurado
- Continuar perguntando enquanto houver pendências
- Parar imediatamente quando o usuário disser que não quer mais configurar

**Importante:** Este arquivo é apenas referência. O agente nunca deve assumir que algo já está configurado sem verificar primeiro.