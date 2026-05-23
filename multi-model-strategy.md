# Multi-Model Strategy

Este arquivo é **referência** do que o usuário deseja ter disponível.

## LLMs desejados

| LLM            | Prioridade   | Como configurar                          | Quando usar                              |
|----------------|--------------|------------------------------------------|------------------------------------------|
| Grok (xAI)     | Principal    | Via xAI OAuth                            | Tarefas gerais e orquestração            |
| Claude         | Alta         | Anthropic API key                        | Raciocínio complexo e código             |
| Cursor         | Fundamental  | IDE externo (não configurado no Hermes)  | Edição pesada de código na IDE           |
| Ollama         | Opcional     | Instalar localmente                      | Tarefas simples (economia de tokens)     |
| AWS Bedrock    | Opcional     | IAM role                                 | Alternativa enterprise                   |

## Regras de Uso

- Hermes é o orquestrador principal.
- Código pesado ou raciocínio complexo → sugerir **Cursor** ou **Claude**.
- Tarefas simples → priorizar **Ollama** quando disponível.
- Sempre verificar o status atual antes de oferecer configuração.

## Durante o Onboarding

O agente deve:
- Verificar o status real de cada LLM (usando `hermes doctor`, `hermes config`, etc.)
- Mostrar tabela com o que está pendente
- Oferecer configurar apenas o que o usuário ainda não configurou
- Parar de perguntar quando o usuário indicar que não quer mais configurar

**Importante:** Este arquivo não afirma o que já está configurado. O agente sempre verifica o estado atual.