# CONSIDERAÇÕES DO SEMINÁRIO I DA PROFESSORA MARIA CLÁUDIA

Seminário I, 18/11/2026. Fonte: `seminario_I/transcricao/video_falantes_turnos.md`
(os tempos entre colchetes remetem à transcrição).

## PEDIDOS DE ALTERAÇÃO NO TEXTO

### 1. Zonas *versus* ETL: não afirmar que o ETL só grava no final [00:24:33 – 00:26:45]
- Disse que a afirmação "no ETL, só o resultado final é gravado" **não é exatamente verdade**: a literatura é variada.
- Lembrou que há arquiteturas com **ODS** (*Operational Data Store*), que guardam dados intermediários. Segundo ela, o *Lake House* já foi muito chamado de ODS, mas tem uma estrutura mais bem pensada para receber dados de todos os tipos.
- Vê até uma **correspondência entre o ETL com etapas intermediárias e a arquitetura de três camadas** (bronze/silver/gold).
- Pediu para **não se apegar** a esse argumento e evitar a "armadilha de algumas publicações". Disse que não é preciso aprofundar o assunto, só ajustar a redação.

### 2. Modelo canônico: ressalvar que a abordagem é simplificada [00:26:45 – 00:29:27]
- Achou boa a ideia de usar um modelo canônico com mapeamento vertical (fonte → canônico) em vez de mapear par a par. Lembrou que as "receitas de tradução" são o que se chama de **de-para**.
- Mas considera a visão **um pouco simplista**: dentro do estudo de caso é fácil chegar ao modelo canônico, mas em situações mais amplas e complexas isso **é custoso** e exige **modelagem conceitual**.
- Pediu para deixar explícito que:
  - o modelo canônico exige um **acordo prévio**, que envolva todas as unidades;
  - o acordo é **arquitetural**: vale para outras operações e interações, e não só para uma operação;
  - em **operações conjuntas** será preciso alinhar o modelo com a **Marinha** e a **Força Aérea**.

### 3. Escopo: execução, não planejamento [00:29:31 – 00:31:03]
- Observou que o trabalho cobre a **execução** da operação (relatos, relatórios, mensagens) e não o **planejamento e a preparação da ordem de operação**. O Silvio confirmou.
- Pediu (de forma implícita) para deixar essa delimitação clara no texto.

### 4. Trabalhos futuros: incluir a ordem de operação como fonte [00:31:03 – 00:32:00]
- Sugeriu como perspectiva futura que o *Lake House* ingira **outras fontes**, como os documentos de **planejamento e emissão da ordem de operação**.
- O motivo: é na ordem de operação que aparece a distinção entre **missão** (mais ampla) e **tarefas**, e as tarefas viram missões para os escalões subordinados. Isso responde ao ponto de missão e tarefa levantado na qualificação.

### 5. Citar o trabalho complementar do IME (Ten Adnet Alves) [00:27:50 – 00:31:01; 00:35:00 – 00:35:59]
- O **Ten Adnet Alves** (CDS, equipe de C2, Rio) faz mestrado no IME, orientado por ela, e está no 2º ano. O trabalho modela a **ordem de operação** e a distinção missão/tarefa.
- O estudo de caso dele é uma **operação conjunta Exército–PM**: a partir das ordens de operação das duas instituições, identificar as missões, as tarefas e quem é responsável por cada uma. O trabalho **não chega à execução**.
- Ela vê os dois trabalhos como **complementares**: o dele cobre o planejamento e o do Silvio a execução.
- Sugeriu **citar ou mostrar na conclusão** essa possibilidade de cooperação UnB–IME, com possível continuidade depois da defesa e como incentivo a novos mestrados.

### 6. Ler e citar o artigo dela sobre missão e tarefa [00:32:20 – 00:32:50]
- Ela vai enviar o **artigo publicado sobre a distinção entre missão e tarefa**. O artigo traz um núcleo de ontologia e chega à parte de **delegação**.
- Sugeriu dar uma olhada no artigo e, se fizer sentido, citá-lo na conclusão.

## OUTROS PONTOS (sem alteração no texto)
- Elogiou a evolução do trabalho, o nível de detalhe do estudo de caso e, em especial, o **registro da proveniência e dos prompts**.
- Pediu para **usar os dados sintéticos** (a "Operação Perseu de mentirinha") no trabalho do grupo dela. O Silvio autorizou.
- Ela vai passar ao Ten Adnet Alves o que o Silvio tiver escrito.

## PENDÊNCIAS DE AÇÃO
- [ ] Receber o artigo de missão e tarefa (a professora vai enviar).
- [ ] Pegar o contato do Ten Adnet Alves (ver também as considerações do Victorino). O Silvio pode falar com o Breda.
