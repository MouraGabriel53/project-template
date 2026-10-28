# Documentação

| Documento | O que tem | Quando muda |
| --- | --- | --- |
| [architecture.md](architecture.md) | Visão geral, stack, dependências e camadas | Ao adicionar uma dependência ou mudar a estrutura |
| [api.md](api.md) | Onde ver a API (Swagger) e a lista de endpoints | A cada operação que expõe ou altera um endpoint |
| [development.md](development.md) | Requisitos, comandos, CI, commits e pull requests | Ao mudar uma ferramenta, um comando ou um workflow |
| [decisions/](decisions/README.md) | Por que as escolhas não óbvias foram feitas | A cada escolha não óbvia |
| `<contexto>/` | O contexto e uma spec por operação | A cada operação |

## Contextos

<!-- Uma linha por contexto. -->

| Contexto | Documento |
| --- | --- |

## Modelos

| Para criar | Copie | Para |
| --- | --- | --- |
| Um contexto | [_templates/000_context.md](_templates/000_context.md) | `<contexto>/000_<contexto>_context.md` |
| Uma operação | [_templates/NNN_operation.md](_templates/NNN_operation.md) | `<contexto>/NNN_<operação>.md` |
| Uma decisão | [_templates/decision.md](_templates/decision.md) | `decisions/NNNN-titulo-curto.md` |

Uma operação começa como spec **Rascunho**, é aprovada antes de qualquer
código e, depois de concluída, descreve o sistema como ele é.
