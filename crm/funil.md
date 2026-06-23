# Funil SDR — Weecode

Este funil organiza trabalho interno; nenhuma etapa autoriza envio automático.

| Etapa | Critério de entrada | Ação permitida | Saída esperada |
|---|---|---|---|
| Descoberta | Instituição encontrada em fonte permitida | Registrar dados mínimos e fonte | Rascunho de lead |
| Validação | Fonte, data e aderência inicial registradas | Verificar duplicidade, opt-out e dados permitidos | Lead elegível ou desqualificado |
| Qualificação | Evidências suficientes para avaliar | Classificar A, B, C ou D | Prioridade e justificativa |
| Preparação | Lead A/B/C elegível | Sugerir pergunta e mensagem | Rascunho para revisão |
| Revisão humana | Rascunho completo | Aprovar, ajustar ou reprovar | Decisão registrada |
| Contato humano | Aprovado por pessoa responsável | Pessoa da Weecode decide se envia | Resultado registrado manualmente |
| Acompanhamento | Interação registrada por humano | Sugerir próximo passo, se permitido | Atualização de status |
| Encerrado | Opt-out, duplicidade, D ou falta de aderência | Não abordar | Motivo registrado |

Regras: `opt_out = Sim`, `duplicado = Sim` ou classificação `D` bloqueiam a preparação de mensagens. Todo contato depende de revisão humana documentada.
