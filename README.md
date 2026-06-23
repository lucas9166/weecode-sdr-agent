# Weecode SDR Agent

Estrutura inicial para um agente SDR B2B da Weecode. O agente apoia a pesquisa, organização, qualificação, priorização e sugestão de abordagens para instituições de saúde. Ele não realiza contatos nem automações de envio.

## Produto foco

Integração de Nota Fiscal Eletrônica com ERP hospitalar: apoio à organização do fluxo de NFe, XML e DANFE entre fornecedores, SEFAZ e os processos de compras, suprimentos, financeiro, fiscal e contábil.

## Estrutura

- `AGENTS.md`: papel, ICP, regras de coleta e saída esperada do agente.
- `compliance/`: regras de LGPD e abordagem responsável.
- `data/leads_qualificados.csv`: modelo de registro de leads; os exemplos existentes são inteiramente fictícios.
- `prompts/`: prompts operacionais para busca, qualificação, WhatsApp, e-mail e follow-up.
- `crm/`: funil e campos mínimos para acompanhamento.
- `outputs/`: modelos de relatório semanal e mensagens personalizadas para revisão.

## Fluxo operacional

1. Pesquisar somente fontes públicas, institucionais, profissionais ou voluntariamente fornecidas.
2. Registrar a fonte, data de coleta e dados disponíveis no CSV.
3. Usar `prompts/prompt_qualificacao.md` para separar fatos de hipóteses e classificar A, B, C ou D.
4. Eliminar duplicidades, registros com opt-out, fontes não rastreáveis e perfis fora do ICP.
5. Gerar rascunhos consultivos com os prompts de mensagem.
6. Submeter toda mensagem e qualquer próximo passo à revisão humana.
7. Atualizar o status no CSV e no funil; nunca registrar um envio automático.

## Como usar os prompts

Forneça ao prompt apenas dados permitidos e com origem registrada. O resultado deve preservar `não identificado`, `provável` e `necessita validação` sempre que não houver confirmação. Os prompts produzem rascunhos, não comandos de envio.

## Registro de leads

Cada linha em `data/leads_qualificados.csv` é um registro de trabalho. Os campos `fonte_principal`, `data_coleta`, `nivel_confianca`, `opt_out`, `duplicado`, `status` e `status_revisao_humana` são obrigatórios para uso operacional. Nunca substitua dados ausentes por suposições.

## Compliance

Siga `AGENTS.md` e `compliance/regras_lgpd.md`. São permitidos dados públicos e institucionais; são proibidos dados de pacientes, dados sensíveis, bases vazadas, contatos pessoais fora de contexto profissional e disparos automáticos. Uma pessoa da Weecode deve revisar qualquer mensagem antes do envio.

## O que o agente pode fazer

- Pesquisar fontes autorizadas.
- Organizar e deduplicar registros.
- Qualificar, priorizar e explicar critérios.
- Sugerir canais, perguntas de diagnóstico e mensagens.
- Preparar relatórios e rascunhos para revisão humana.

## O que o agente não pode fazer

- Enviar WhatsApp, e-mails ou qualquer outra mensagem.
- Automatizar disparos ou follow-ups.
- Tratar dados de pacientes, sensíveis ou sem fonte rastreável.
- Inventar fatos, contatos, ERP, dores ou resultados.
- Ignorar opt-out, duplicidade ou reprovação humana.

## Rotina semanal sugerida

1. Revisar fontes e novos registros elegíveis.
2. Deduplicar e atualizar evidências, fonte e nível de confiança.
3. Qualificar e priorizar os leads com o prompt de qualificação.
4. Preparar rascunhos somente para os registros aprovados para revisão.
5. Realizar revisão humana, registrar decisões e opt-outs.
6. Consolidar o relatório semanal sem incluir dados pessoais desnecessários.
