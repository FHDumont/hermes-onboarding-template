# Multi-Model Strategy

Usuário tem acesso a:
- Grok (via assinatura)
- Cursor
- Claude
- Ollama (modelos locais)
- Modelos em cloud (Hugging Face, Grok)

Regras de uso:

- Hermes é o orquestrador principal
- Tarefas de código pesadas → sugerir Cursor ou Claude
- Tarefas simples/rápidas → priorizar Ollama (local) para economizar tokens
- Sempre que possível, usar o modelo mais barato/rápido que atenda a necessidade

Preferência explícita:
- Quando o usuário pedir algo relacionado a código, considerar usar Cursor (para acompanhar na IDE) ou Claude.