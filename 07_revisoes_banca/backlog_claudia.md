# Backlog — Prof.ª Dr.ª Maria Cláudia Cavalcanti (IME)

Fonte: `consideracoes_banca/qualificacao/consideracoes_claudia.md`.
Qualificação em 13/08/2026; considerações recebidas na sequência, ainda em agosto/2026.

Mesma classificação usada no backlog do Andrei:

| | significado | conduta |
|---|---|---|
| **A** | mecânico — erro objetivo | edito direto, sem discussão |
| **B** | esclarecimento local | proponho redação, você aprova |
| **C** | argumentativo / de escopo | **não edito**; decisão é sua |
| **D** | bloqueado | falta figura, capítulo 5 ou resposta dela |

**38 itens** (classificação atual, após as reclassificações do percurso): 5 A · 15 B · 7 C · 7 D · 4 sem tipo (CL-01, 08, 30, 38).
**Abertos: 4** - CL-05 (C) · CL-35, CL-36, CL-37 (D, dependem do cap. 5).

25 feitos: CL-02, 03, 04, 07, 09, 10, 11, 12, 13, 15, 16, 17, 18, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 31, 32 (o CL-14 morreu junto com o CL-13). CL-01, CL-08 e CL-38 encerrados por decisão do Silvio. CL-06 e CL-34 encerrados como pacificados (04/09/2026). CL-19 e CL-33 encerrados por decisão do Silvio (05/09/2026). CL-30 confirmado como não-erro.

### Pendências de comunicação com a banca

Itens **encerrados no texto** que ainda exigem uma fala do Silvio à Prof.ª Cláudia. Não
geram edição; geram resposta. Trazer à tona antes de fechar cada bloco de trabalho.

| item | o que dizer a ela |
|---|---|
| **CL-30** | os `??` das p.73/74/78 **não são erro**: são os três `\ref{cap:poc}` do cap. 4, que o build da qualificação não resolvia por não incluir o cap. 5. Auditoria completa junto: 23/23 referências à mão corretas, zero quebradas. |
| **CL-19** | quais sistemas entram na integração **não vai por escrito**; a identificação é feita na fala do seminário de acompanhamento. O texto descreve as fontes por perfil. |

### Apoio cruzado

Material achado ao trabalhar um item que serve de argumento em **outro**. Antes de
abrir qualquer item, `grep -n "CL-XX\|AN-XX" backlog_claudia.md` — o apoio pode estar
registrado longe do item a que pertence.

| serve em | o quê | veio de |
|---|---|---|
| ~~CL-11~~ | Inmon admite que o *application pond* é "notoriously unintegrated" | CL-10 — consumido |
| CL-14 | Inmon: "data does not have to pass through the raw data pond" | CL-10 |
| AN-10, CL-14 | Inmon manda esvaziar o *raw pond* — divergência a declarar | CL-10 |
| CL-26, CL-33 | `analític*` em 102 usos, 14 colocações só no cap. 4 | leitura inicial |
| CL-06, CL-34 | candidatos a diferencial científico (4 listados no CL-34) | AN-02, AN-16 |
| CL-04 | o parágrafo do AN-04 provavelmente já responde | backlog Andrei |
| CL-30 | auditoria: 23/23 referências à mão corretas, zero quebradas | CL-22 |
| CL-34 | norma entrega o vocabulário-alvo legitimado, não os mapeamentos | CL-24 |
| CL-35 | linhagem de coluna no OM exige SQL/API; decidido nível de tabela | CL-24 |
| CL-33 | `analític*` no cap. 4: 63 -> 54 vivas, após CL-20/21/26 | CL-20 |
| CL-27 | amarre RD-1 -> *Silver*/*Gold* já escrito como remissão | CL-18 |
| ~~CL-11~~ | zona x ETL: diferença mecânica, não terminológica | CL-12 — não usado |
| CL-34 | materializar o bruto: conveniência civil, necessidade militar | CL-12 |
| CL-33 | `analític*` nomeia a *Bronze* (`:27`) e a *Gold* (`:274`) no mesmo cap. | CL-29 |
| CL-06, CL-34 | cocitação recuperou seminais fora da janela: método, não conveniência | CL-07 |

---

## Capa e folha de rosto

### CL-01 — texto do objetivo na capa · **ENCERRADO — sem ação**
> "Checar como outros colegas colocaram na qualificação."

O texto não é do Silvio: é gerado pela classe (`UnB-CIC.cls:627-628`), e está correto —
inclusive "Mestrado **Profissional**" (`UnB-CIC.cls:67`), que na transcrição das
considerações havia saído como "Professional".

**Verificado pelo Silvio em 31/08/2026: está correto.** Nada a fazer.

### CL-02 — data da capa · **A** — FEITO
`monografia.tex:25` trazia `\diamesano{21}{abril}{2026}`, inalterado desde a tag
`qualificacao-ago2026`.

**A qualificação foi em 13/08/2026** (confirmado pelo Silvio em 31/08/2026). A data da
capa estava, portanto, errada — e a anotação dela ("totalmente em desacordo") era literal,
não ambígua. A ambiguidade era minha: eu havia registrado abril como data da qualificação.

Corrigido para `\diamesano{13}{agosto}{2026}`.

**Nota:** na versão de depósito essa data muda de novo, para a data da defesa.

### CL-03 — "Prof.ª Dr.ª" ou "Profa. Dra." · **B** — FEITO
`monografia.tex:27`. Os macros da classe (`UnB-CIC.cls:351,355`,
`\def\@prof@[#1]#2{Prof.a\ #2}`) geram **"Prof.a Dr.a"** — o `a` na linha de base,
sem sobrescrito e sem ponto. Não é nenhuma das duas formas pedidas.

Classe intocável, então os macros foram abandonados **nessa linha só**:

```latex
\membrobanca{Prof.\textsuperscript{a} Dr.\textsuperscript{a} Maria Cláudia Cavalcanti}...
```

Escolhida a forma **"Prof.ª Dr.ª"** por paralelismo: o orientador e o coordenador saem
como "Prof. Dr." na mesma folha. "Profa. Dra." muda a estrutura da abreviatura e
deixaria a professora com tratamento graficamente distinto dos dois homens da página.

`\textsuperscript{a}` e não `\textordfeminine` porque este, na codificação T1 da classe,
costuma vir com traço embaixo (ª). Seguro: o nome é guardado por `\def` e impresso em
célula de tabular (`UnB-CIC.cls:677`), sem passar por metadados de PDF.

Deixado comentário na linha explicando por que a classe não foi usada ali.

### CL-38 — tratamento do Prof./Dr. Andrei · **ENCERRADO — decisão do Silvio**
Levantado por mim ao trabalhar o CL-03, **não** pela banca. Hoje:
`\membrobanca{\dr Andrei Lima Queiroz}` — só `\dr`, enquanto orientador e coordenador
saem como "Prof. Dr.".

Contexto: o Andrei deu aula no Programa, mas o cargo dele na UnB é técnico, na reitoria.

**Decisão (31/08/2026): fica `\dr`.** Razão do Silvio: ninguém cobrou isso, e se alguém
notar no futuro a troca é trivial. O risco também é assimétrico a favor dessa escolha —
"Dr." em quem também é professor é omissão, não erro; "Prof." em quem tem cargo técnico
seria afirmação incorreta em documento oficial.

**Não reabrir** sem provocação externa. Se um dia for preciso: a autoridade é a
portaria/ata de designação da banca, e um vínculo formal com o PPCA (professor
colaborador ou credenciado) tornaria "Prof. Dr." correto independentemente do cargo.

---

## Capítulo 1 — Introdução

### CL-04 — "Alguma investigação sobre os sistemas e dados reais envolvidos?" · **B** — FEITO
Delimitação de escopo. **Provavelmente já resolvido** pelo AN-04 (parágrafo sobre
Pacificador, C2 em Combate e FAC2FTer). Conferir se o texto novo alcança este ponto
ou se falta remissão a partir da delimitação de escopo.

**Conferido em 04/09/2026: a investigação existe e a remissão faltava.** `1_Introducao:30`
caracteriza os três sistemas reais com fonte - C2 em Combate (2002, integrado ao SISFRON),
Pacificador (GLO) e FAC2FTer (Operação Atlas 2025) - e `:32` fecha com a lacuna: *"cada um
produz e armazena seus próprios dados, sob esquemas e convenções próprios [...] Não há entre
eles uma camada que os consolide"*. Onde ela perguntou, porém, liam-se duas negativas
seguidas ("sem acoplamento a sistemas finalísticos em produção", "exclusivamente dados
sintéticos") sem nada apontando para essa caracterização.

Acrescentada remissão em `\entrou{}` no terceiro item do "O que não será feito"
(`1_Introducao:101`): os sistemas em operação e o regime de chegada foram caracterizados na
justificativa; o que se exclui é o acoplamento da PoC a eles, não o seu conhecimento.

**Nota de mecânica:** o capítulo 1 não tem nenhum `\label{}` nem `\ref{}`. A remissão ficou
em prosa ("na justificativa deste capítulo") para não criar âncora isolada num capítulo que
não usa referência cruzada. Se um dia o capítulo ganhar labels, esta é candidata a virar `\ref`.

**Apoio cruzado gerado para o CL-17:** o mesmo parágrafo define Alfa/Bravo/Charlie - ver lá.

### CL-05 — "Mas como demonstrar que a solução proposta é útil?" · **C**
Sobre "Integração com sistemas legados específicos do EB". Pede critério de
validação. Amarra com CL-35 (escopo da PoC).

### CL-06 — justificativa acadêmica · **C** — ENCERRADO: PACIFICADO (04/09/2026)

Mesma pacificação do CL-34: mestrado profissional e conversa do orientador com ela na
qualificação. Sem edição no texto.

**Apoio cruzado (vindo do CL-07)**: ver o achado registrado no CL-34 - a seleção do
portfólio veio de procedimento bibliométrico verificável (cocitação recuperando
seminais fora da janela), não de escolha por conveniência. É material para a
justificativa **acadêmica**, que é exatamente o que ela cobrou aqui.
> "o fato de não haver uma solução específica para o EB não chega a caracterizar
> uma contribuição acadêmica."

**Mesma crítica do CL-34.** Ela levantou no cap. 1 e repetiu no fecho: leu tudo e a
resposta não apareceu. Tratar os dois juntos.

---

## Capítulo 2 — Metodologia

### CL-07 — corte temporal de 2016 · **B** — FEITO
> "Trabalhos anteriores a 2016 não contemplam as abordagens que representam o
> estado da arte atual" → ela: *"no que se refere a? melhorar a justific."*

Falta dizer **em qual disciplina** o corte vale. ~~Candidato: a publicação do
paper do Delta Lake / consolidação dos *open table formats*.~~ **Candidato descartado:**
o paper do Delta Lake é de 2020 (VLDB) e o Lakehouse é de 2021 (CIDR) - nenhuma das
duas datas justifica um corte em 2016. O Silvio derrubou a justificativa tecnológica
inteira: HDFS é de 2006, o conceito de *data lake* é de 2010, Iceberg é de 2017 e Hudi
começou em 2016. As tecnologias **não** são recentes.

Fechado em 2_Metodologia:55 com a v3, que troca de eixo - sai "as tecnologias são
novas" (frágil) e entra justificativa **metodológica + bibliométrica**:

1. **TEMAC recomenda 5 a 10 anos** (`01_protocolo/TEMAC_artigo.md:183`, verbatim:
   *"Atualmente, os estudos tendem a realizar buscas em espaços de tempo de 5 a 10
   anos."*). 2016-2026 são exatamente dez - o limite superior do próprio método.
2. **2016 é onde começa a produção dos autores-âncora** que a própria bibliometria
   apontou (`05_resultados/REL_FINAL/relatorio_bibliometrico_temac.md`, §2.2.2: *"Fase 1
   (2016-2018) - Estabelecimento de Fundamentos [...] HAI RH, com trabalhos
   fundamentais publicados a partir de 2016"*), com Constance e GEMMS, ambos 2016.
3. **A janela filtra o que é buscado, não o que é encontrado** - ver achado abaixo.

Também retirada a menção ao Lakehouse: citar um marco de 2020/2021 para defender um
corte de 2016 era o que convidava a pergunta dela.

---

## Capítulo 3 — Referencial Teórico

### CL-08 — enxugar detalhamentos · **ENCERRADO — decisão do Silvio (01/09/2026)**
> "poderia rever c/ base no que realmente precisa p/ entender a minha proposta."

**Decisão: não cortar conteúdo do cap. 3.** Justificativa do Silvio: nenhum outro
membro da banca levantou o ponto.

Justificativa adicional a usar se ela retomar na defesa: a amplitude do cap. 3 é
resultado do protocolo TEMAC declarado no cap. 2, não de escolha estilística - podar
tópicos por sensação de excesso quebraria a coerência com a metodologia declarada. E
há posição acadêmica publicada dos dois lados (Boote & Beile 2005 defendem revisão
ampla como demonstração de domínio do campo; Webster & Watson 2002 defendem revisão
*concept-centric*). **Conferir essas referências antes de citar.**

**Sobre a evidência, para o registro:** este é o único item de toda a lista dela sem
página e sem frase entre aspas. É fala relatada, provavelmente oral. A sentença
"acho que falei demais, expliquei demais" nas considerações é **do Silvio**, não dela
- não confundir uma coisa com a outra ao reabrir este item.

Não confundir com o CL-33: aquele é sobre **repetição** e tem evidência escrita e
verificável no texto. Continua aberto.

### CL-09 — concordância "Giebler et al. destaca" · **A** — FEITO
`3_Referencial_Teorico.tex:220`. `destaca` → `destacam`.

Não é critério, é lapso isolado: na linha 275 o mesmo sujeito e a mesma referência já
aparecem no plural — "Giebler et al. \cite{giebler_data_2021} **argumentam** que os
metadados...".

Corrigido junto um defeito não apontado por ela na mesma oração: "com mais separações
**contudo,** Giebler et al." anunciava contraste onde não há — a Giebler **concorda**
com mais separações (diz que a segmentação, apesar de mais complexa, dá acesso mais
eficiente), e a concessão já está no "embora... aumente a complexidade". O conectivo
trabalhava contra o argumento.

O Silvio recusou a solução com ponto e vírgula ("pontuação rebuscada, não é como
escrevemos") e a construção com "como Giebler et al., que destacam que..." esbarra num
"que... que". Solução adotada: ponto final, sem conectivo.

Sem marcação de cor.

### CL-10 — "por seu formato" nos *data ponds* · **A** — FEITO
`3_Referencial_Teorico.tex:220`. Ela apontou "por seu formato" e sugeriu "estrutura".

O Silvio trouxe o texto original do Inmon, que nomeia o critério: os dados vão a um
dos três poços *"based on the **kind of data** entailed"* / *"the different **types of
data**"*. Não é formato nem estrutura — é **natureza do dado**. Adotado "natureza"
e não "tipo" porque em português, num texto de banco de dados, "tipo de dado" lê como
*data type*. O parágrafo já usava "natureza" duas frases adiante, ou seja, o texto
acertava no meio e errava no começo.

Provável origem do erro: o Inmon usa "format" ao falar do *conditioning*
("the information is not in a format which is easy... to study") — mas ali descreve o
**resultado do condicionamento**, não o critério de partição.

Aplicado também um segundo ajuste: o *archival data pond* estava pendurado na mesma
lista com "e, finalmente", como se fosse um quarto tipo de dado. O Inmon o define como
estágio final de ciclo de vida (*"In the final stages of the life cycle of data..."*).
Separado em oração própria. Bônus: elimina a repetição de "natureza" em três frases,
que alimentaria o CL-33.

Sem marcação de cor (troca de palavra + ajuste de pontuação, não reescrita).

### CL-11 — "silos disjuntos" / "Será? Literatura marketeira?" · **C** — FEITO

**Fechado em 3_Referencial:224** com a opção (b): ancorar no Inmon. Três mudanças
além da âncora - a crítica passa a ser **atribuída** a Giebler et al. em vez de
enunciada como fato, "inviabilizando" vira "limitando", e a expressão que ela circulou
("silos disjuntos") sai, substituída pela descrição do mecanismo.

Descartado o argumento de autoridade ("autora de renome, publicou na IEEE"): ela não
duvidava do veículo. "Marketeira" mirava o fato de a crítica ao *data pond* partir de
quem propõe a alternativa. Contra isso, prestígio não serve - só corroboração
independente serve, e a de Inmon é a melhor possível, por ser do próprio autor do
modelo criticado.

**Apoio cruzado (vindo do CL-12)**: a melhor defesa contra "marketeira" é a diferença
**mecânica**, não terminológica, entre zona e ETL - já escrita em 3_Referencial:230.
Zona materializa e mantém consultável cada estágio; ETL descarta o intermediário. Isso
mostra que a arquitetura por zonas propõe algo verificável, não renomeia o que já
existia.
`3_Referencial_Teorico.tex:224`.

**Apoio cruzado** (achado ao trabalhar o CL-10) — defesa melhor que o prestígio da Giebler: o próprio Inmon documenta a
fragmentação, descrevendo o *application data pond* — *"the data in the application
pond is **notoriously unintegrated** ... there is a good chance that data in this pond
comes from different applications. It's this multi-application origin of data that
gives the analyst a hard time."*

Ou seja, não é crítica de concorrente vendendo alternativa: é limitação reconhecida
pelo autor do modelo. Isso desarma a suspeita de "literatura marketeira" de um jeito
que "publicou na IEEE" não desarma. Opção de redação: atribuir a crítica e ancorá-la
no próprio Inmon.

### CL-12 — "O que essa definição em zonas tem de diferente da ETL?" · **B** — FEITO
Sobre a Figura 3.4. Pergunta legítima: zonas persistem estados intermediários e
são consultáveis; ETL move dados entre pontos sem materializar os estágios.

Fechado em 3_Referencial:230, parágrafo novo em `\entrou{}` inserido **antes** da
Figura 3.4 - o leitor chega ao diagrama já sabendo que zona não é ETL. Três
consequências nomeadas: reprocessamento sem nova extração na fonte, consumidores
próprios em cada zona, e conformação ao *schema* como estágio interno em vez de
condição de entrada. Fecha com "o ETL não desaparece - deixa de ser a fronteira de
entrada e passa a operar entre zonas".

Citação: uma só, `laurent_use_2020`, que já ancorava o *schema-on-read* na linha 224.
A distinção zona x ETL é articulação do autor, não atribuída a ninguém.

**Apoio cruzado depositado**: ver CL-11 e CL-34.

---

## Capítulo 4 — Proposta de Arquitetura

### CL-13 — Figura 4.1: explicitar as zonas · **D → B** — FEITO (05/09/2026)

**Fechado.** O Silvio renderizou o TikZ no projeto à parte, printou e substituiu a
figura diretamente no Overleaf - não passa por este repo nem por `arquivos-dissertacao/`,
então não há commit de texto correspondente. O fonte do diagrama fica em
`_local/diagrama1_projeto_CL-13.tex` (não versionado). Com ele cai o CL-14.
"Engine de processamento (orquestrado por pipelines)" esconde as zonas.
~~**Falta o arquivo da figura**~~ — o bloqueio caiu, ver abaixo.

**O bloqueio era falso.** A figura nunca foi arquivo de imagem de origem: o Silvio
escreve o diagrama em **TikZ**, renderiza num projeto LaTeX à parte, tira um print e
carrega o PNG no Overleaf. Por isso a `Figura 4.1` no PDF é um bitmap 512x541 a 116 ppi
e não havia fonte em `~/Projetos`. O fonte existe - é código, e ele o forneceu.

**Ela desenhou o substituto.** A margem esquerda da p.50 do PDF anotado traz o redesenho
dela, e é específico: os **processos** viram caixas nomeadas na espinha vertical
(Ingestão -> Padronização -> Conformação + harmonização -> Integração + organização) e
cada **zona** vira um cilindro ao lado do processo que a produz, ligado por seta
bidirecional. É a leitura literal da anotação: *"Sugestão de melhoria p/ explicitar o
processo e sem esconder as zonas de dados"*.

**Feito:** TikZ reescrito conforme o esboço, compilado e conferido visualmente.
Código em `_local/diagrama1_projeto_CL-13.tex`, prévia em
`_local/diagrama1_projeto_CL-13_preview.png`. **Pendente do Silvio:** renderizar no
projeto à parte e subir a imagem ao Overleaf, mantendo o `\figura{diagrama1_projeto}`
de `4_Proposta:24` como está - fluxo confirmado por ele em 04/09/2026.

**Decisão do Silvio (04/09/2026): as três zonas consumíveis entram na figura.** Ele
perguntou se ligava só a *Gold* (para não poluir) ou também *Bronze* e *Silver*. O texto
já decidia: `:192` diz que "a *Bronze* permanece **acessível à camada funcional de
consumo**" e `:214` que "assim como na camada *Bronze*, a *Silver* é também **acessível
diretamente pela camada funcional relacionada a consumo**". Ligar só a *Gold* faria a
figura contradizer o texto corrigido pelo CL-15 e pelo CL-26 - e devolveria sem resposta
a anotação *"A zona S pode ter dados já prontos p/ consulta e visualização"*, que ela
escreveu **nesta figura**.

A poluição foi resolvida por **hierarquia de linha**, não por omissão: *Gold* em linha
cheia e grossa (caminho projetado), *Bronze* e *Silver* em linha fina tracejada, com a
legenda "acesso exploratório". A **Landing não entra** - `:186` diz que a *Bronze* é a
"zona de **primeira** persistência analítica", logo a *Landing* não é consumível. A figura
passa a marcar essa fronteira, que antes não aparecia.

**Mudança colateral a conferir:** para as linhas não se cruzarem, a *engine* de consulta
foi para a **esquerda** da faixa de governança (perto das zonas) e o catálogo para a
**direita** (perto dos processos). Com isso o catálogo passou a ser alimentado pelos
**processos**, e não pelas zonas como na figura original - é o que ela desenhou no esboço,
e casa com o *goldMEDAL*, que trata o *process* como entidade de primeira classe ao lado
da *data entity*. **Custo:** o desenho deixa de mostrar que o catálogo também registra os
conjuntos de dados. O texto (`:260`-`:268`) cobre isso, mas se o Silvio preferir o
contrário, é reverter os dois destinos.

**Exige no preâmbulo do projeto de renderização:** as bibliotecas `positioning`, `calc`,
`arrows.meta` e `shapes.geometric` (o cilindro), mais as 8 cores `\definecolor` - nenhuma
delas existe no `monografia.tex`, que carrega só `shapes.geometric`. O bloco vai
comentado no topo do arquivo.

### CL-14 — "Há dados que chegam direto na Bronze?" · **D** — RESOLVIDO PELO CL-13
Ambiguidade visual da Fig. 4.1. O texto já resolve (RD-4). Depende da figura.

**Morre junto com o redesenho (04/09/2026).** A pergunta nascia da *"Engine de
processamento"*, que ficava fora da espinha com setas entrando em *Bronze*, *Silver* e
*Gold* - eram essas entradas laterais que sugeriam desvio da *Landing*. No layout da
Cláudia a engine se dissolve nas quatro etapas nomeadas e o fluxo fica estritamente
sequencial: a ambiguidade some por construção, sem precisar de texto novo.

O apoio do Inmon (*"data does not have to pass through the raw data pond"*) **não foi
consumido** e fica de reserva, caso ela reformule a pergunta no mérito - se a arquitetura
*deveria* admitir o desvio - em vez de no desenho.

**Apoio cruzado** (achado ao trabalhar o CL-10) — o Inmon admite explicitamente o desvio da zona de entrada —
*"It is worthy of note that **data does not have to pass through the raw data pond**,
although it almost always does. If the developer is sophisticated, it is possible to
send the data directly into the analog, application or the textual pond."*
O criador do modelo de *ponds* autoriza o bypass. Sustenta a resposta com autoridade,
não com engenharia própria.

### CL-15 — Silver com dados prontos para consulta e visualização · **B** — FEITO
Tratado junto com o CL-26: são o mesmo ponto visto por dois lados, e por isso pareciam
pedidos opostos.

### CL-16 — saída da Gold "não necessariamente visão analítica" · **B** — FEITO
BI, API e relatórios também consomem a Gold. Rotular a saída de forma mais ampla.

**Achado ao abrir o item:** o parágrafo da *Gold* (`4_Proposta:246`) era o **último resíduo**
da ideia antiga de consumo restrito à *Gold* e mediado pela governança - a *Bronze* (`:194`) e
a *Silver* (`:218`) já tinham sido corrigidas no CL-15/CL-26, e a `tab:camadas` (`:325`) já
atribui o acesso às visões à camada **Consumo**. Varrido o resto do capítulo: `:41` e `:49`
estão coerentes (o `:276` explica que a *engine* é apresentada na seção de governança por
transversalidade, não por confusão de função). Nada mais a corrigir.

**Redação aplicada** em `\saiu{}`/`\entrou{}`: a saída expõe as visões à camada funcional de
consumo; o dado sai em formato aberto e catalogado, **sem que a arquitetura prescreva a
aplicação que o consome** - painéis, ferramentas de consulta, relatórios ou interfaces
programáticas. É a neutralidade da interface que responde a ela, não uma lista de produtos.

**Definição da zona, dada pelo Silvio em 04/09/2026 (ver CL-29):** a frase final diz a
*característica principal* da *Gold* - a proximidade com o uso, o dado já organizado segundo o
processo doutrinário que o utilizará, ao alcance do CMTE e do EM. Formulação positiva por
pedido dele: dizer "não tem mais qualidade que a *Silver*" engessa o texto.

### CL-17 — "Alfa Bravo Charlie?" · **D → B** — FEITO (05/09/2026)
Junto a "Sistemas subsidiários das Funções de Combate". Hipótese: hierarquia do
FAC2FTer (Charlie = ponta, Bravo = intermediária, Alpha = comando). **Confirmar com ela.**

**Apoio cruzado (vindo do CL-04, 04/09/2026) - a hipótese está confirmada pelo próprio
texto da dissertação.** `1_Introducao:30` já define os três níveis, com citação:
*"a Família de Aplicativos de Comando e Controle da Força Terrestre (FAC2FTer),
demonstrado na Operação Atlas 2025, articula três níveis de emprego: Alfa, nos escalões
superiores; Bravo, embarcado em viaturas; e Charlie, para frações a pé"*
\cite{barros_operacao_2025}. Ou seja: não é preciso perguntar a ela o que ela quis dizer -
basta responder. **O item continua D** por outro motivo: "sistemas subsidiários" não
aparece em nenhum `.tex`, logo a anotação está sobre a Figura 4.1, ausente. Quando a figura
chegar, a saída provável é uma remissão ao parágrafo do cap. 1, não texto novo.

**Desbloqueado (05/09/2026): a figura chegou e o rótulo sobreviveu.** O redesenho do
CL-13 manteve a caixa `Sistemas subsidiários das Funções de Combate` e já decidiu, em
comentário no fonte, que "a remissão aos níveis Alfa/Bravo/Charlie é feita no texto, não
no rótulo da caixa". Essa remissão **ainda não foi escrita**: não há "Alfa" em nenhum
ponto do cap. 4. Âncora: `4_Proposta:27`, o parágrafo que apresenta a figura. **Passa a B.**

**Correção ao apoio cruzado acima - a hipótese não se confirma como estava escrita.** O
cap. 1 confirma **o que são** Alfa/Bravo/Charlie (níveis de emprego de *um* sistema, da
própria Função C2), não que a caixa da figura *seja* isso. A caixa reúne as fontes que
alimentam a arquitetura, e os níveis de emprego de um sistema não são fontes distintas.
Responder "sim, é isso" seria responder errado.

**Intenção do desenho, dita pelo Silvio (05/09/2026):** a caixa reúne **duas naturezas de
fonte**, não uma. De um lado os **sistemas computacionais** finalísticos que se ligam ao
repositório; de outro, o que **não vem de sistema** - mensagem de áudio, documento,
imagem produzidos no curso da operação. É essa segunda natureza que o rótulo atual
esconde, e é provavelmente por isso que a anotação dela caiu justo ali: a caixa promete
menos do que a arquitetura entrega.

**Estado do texto quanto a essa segunda natureza:** `4_Proposta:35` já diz que a
*Landing* "acomoda ainda os formatos que não admitem estruturação tabular direta, como
**áudio e imagem**"; `:318` lista os não estruturados no requisito de armazenamento
(imagens e vídeos de drones, fotografias). **`documento` não aparece em lugar nenhum do
cap. 4** - se entra, é decisão do Silvio.

**Restrição do CL-19 aplicada aqui:** a remissão vai por **classe de fonte**, sem nomear
sistema. O cap. 1 já nomeia; o cap. 4 remete. Ver o CL-19.

**Feito (05/09/2026).** Duas edições, ambas marcadas com `\entrou{}`:

- `4_Proposta:27` - frase nova no parágrafo que apresenta a figura, declarando as duas
  naturezas de fonte que a caixa superior reúne, com remissão ao cap. 1 e ao RD-4. Responde
  ao "Alfa Bravo Charlie?" sem repetir os nomes no cap. 4.
- `4_Proposta:35` - "como áudio e imagem" -> "como áudio, imagem e documentos", para a
  *Landing* não contradizer a frase nova. `documento` não existia no cap. 4.

**Rótulo da caixa mantido** como está: resolver no texto não custa novo render nem novo
upload no Overleaf, e o rótulo não estava errado, estava incompleto.

**Cuidado registrado:** a primeira versão da frase remetia por `\ref{cap:introducao}`, que
**não existe** - o cap. 1 não tem `\label`. Teria virado um `??` real, do tipo que o CL-30
declarou inexistente. As remissões ao cap. 1 são escritas à mão (`:45`), e é assim que ficou.

### CL-18 — Tabela 4.1, RD-1: "o que dá o suporte à 'integração'" · **B** — FEITO
Explicitar qual elemento arquitetural materializa a função integradora — a Silver,
pela conformação entre Funções de Combate. Cabe na própria célula ou por remissão.

Não era lacuna de conteúdo: a abertura da *Silver* (4_Proposta:206) já diz que ali se
dá início à materialização da função integradora, "materialização que se completa nas
visões da *Gold*". Era distância de leitura - tabela na p.50, resposta na p.63.

Fechado **por remissão**, em 4_Proposta:90, no parágrafo que glosa RD-1 a RD-5 logo
abaixo da tabela. Recusada a alternativa de escrever a solução dentro da célula: a
Tab. 4.1 é de *requisitos*, e requisito que descreve a solução deixa de sustentar o
argumento de que os requisitos foram extraídos da doutrina, não desenhados para caber
na arquitetura.

**Apoio cruzado consumido**: usa `modelo canônico`, o termo unificado no CL-25.

### CL-19 — "Alfa Bravo?", "Genesis?", "Astros?" · **D** — ENCERRADO: decisão do Silvio (05/09/2026)
Quais sistemas do EB entrariam na integração.

**Não vai por escrito.** A pergunta dela é legítima e tem resposta, mas a resposta é
**falada**, no seminário de acompanhamento - não registrada na dissertação. A PoC vai
simular fontes com o perfil dos sistemas em operação; o texto as descreve **por perfil**
(regime de chegada do dado, escalão de emprego, natureza da operação), sem dizer de qual
sistema cada uma é o análogo.

**O texto já sustenta isso**, e não é contorno improvisado: `1_Introducao:101` delimita o
escopo dizendo que "a PoC adota interfaces genéricas e padronizadas, **sem acoplamento a
sistemas finalísticos em produção**". Descrever a fonte por perfil é a leitura fiel dessa
delimitação, não um recuo diante da pergunta.

**Cuidado a manter no cap. 5:** a caracterização do cenário no cap. 1 (`:30`) **continua
nomeando** C2 em Combate, Pacificador e FAC2FTer - com citação de fonte pública aberta, e
é dela que o CL-17 tira a confirmação do Alfa/Bravo/Charlie. Nomear o cenário é uma coisa;
declarar de qual sistema a fonte simulada é o espelho é outra. **A primeira fica, a
segunda não entra.** Não escrever, no cap. 5, frase que ligue uma fonte da PoC a um
sistema nomeado.

**Encerra também o "Genesis?" e o "Astros?"** - nomes que ela anotou como candidatos: não
entram, pela mesma regra.

### CL-20 — conversão colunar nem sempre necessária · **B** — FEITO
### CL-21 — "mas se preserva, pra que a conversão?" · **B** — FEITO
Tratados juntos: são o mesmo ponto por dois lados.

**CL-21 — a contradição existia e o texto nunca a reconciliava.** Dizia que a *Bronze*
"preserva os dados tal como vieram [...] mantendo a granularidade, a nomenclatura e a
estrutura de cada fonte" e, três parágrafos antes, que os converte para colunar.
Resposta: **preservação é lógica, conversão é física**. A terceira função derivada foi
reescrita (`\saiu`/`\entrou`) e agora termina nomeando a contradição para dissolvê-la:
"A conversão altera apenas a forma de armazenamento - de orientação por linha para
orientação por coluna -, sem afetar valores, nomenclatura ou granularidade: é nesse
sentido que a *Bronze* converte sem deixar de preservar."

**CL-20 era sobre-afirmação, e sumiu ao ser removida.** O texto justificava o colunar
**pela análise** ("formato adequado à análise", "otimizada para leitura analítica"), e
contra isso ela tinha razão: nem todo consumo para decisão é analítico. Mas essa não é a
razão real — o parágrafo de fechamento da zona já declara a certa: "Atende ao requisito
técnico de paradigma *Lakehouse* com transações ACID (RT-1), ao adotar *open table
format*". O colunar está lá por ser **o formato do repositório**, não porque a decisão
exija análise. Retirada a justificativa errada, a objeção deixa de existir — sem
contra-argumento e sem parágrafo novo (que só alongaria um capítulo que ela achou longo).

Trocas sem cor: `formato analítico colunar` → `formato colunar` (3x vivas),
`formato adequado à análise` → `formato adequado à consulta`.

**Achado colateral corrigido junto** — a linha 193, na *Bronze*, tinha **palavra por
palavra** o mesmo defeito do CL-26: "expõe uma interface de consulta analítica diretamente
acessível à camada transversal de governança". Ela marcou só a da *Silver*. Corrigir uma e
deixar a outra tornaria o capítulo incoerente diante de uma leitora que já demonstrou
reparar nisso. Reescrita com cor, saindo também o "quando isso for analiticamente
relevante", redundante com os exemplos seguintes.

**Efeito no CL-33:** `analític*` no capítulo 4 caiu de **63 para 54** ocorrências vivas
(60 no arquivo, 6 dentro de `\saiu{}` e que somem na limpeza).

**Pendência para a leitura geral do Silvio:** a subseção ainda abre com "a zona de
primeira persistência **analítica** da arquitetura". Não mexi — é frase definidora do
papel da zona, e a decisão é dele ao ler o texto completo.

### CL-22 — erro de referência, p.60 · **A** — FEITO
`4_Proposta_Arquitetura.tex:189`. Era:
`discutidos na Subseção~\ref{sec:arq-zonas} do Capítulo~3,`

`sec:arq-zonas` é o label da `\section{Elementos da arquitetura}`, **no capítulo 4**
(linha 163) — renderizava "Subseção 4.3 do Capítulo 3", exatamente a frase dela.

Corrigido para `discutidos na Subseção~\ref{sec:lakehouse},` — sai o "do Capítulo~3",
redundante porque o número já começa com 3. Renderiza "Subseção 3.1.3", que é onde os
*open table formats* estão de fato (Delta Lake, Iceberg, Hudi, Paimon, Lance e a tabela
comparativa, linhas 326-361 do capítulo 3).

**Nota técnica:** `sec:lakehouse` está após `\subsubsection{Data Lakehouse}`, e a classe
herda o `report`, que numera só até `subsection` (`secnumdepth=2`). Sem número, o
`\label` não captura o `subsubsection`: pega o último contador numerado, a subseção
3.1.3. Ou seja, resolve para o alvo certo **por efeito colateral**, não por desenho.
Funciona enquanto a classe não mudar — e ela é intocável (ver `CLAUDE.md`).

Sem marcação de cor.

### CL-23 — RT-6: "Como isso se dá? Flexibilidade de schema?" · **B** — FEITO
**O texto declarava conformidade repetindo o requisito.** O fechamento da *Bronze* dizia
"ao acomodar alterações nas estruturas das fontes finalísticas ao longo do tempo sem
comprometer a integridade do repositório nem interromper a continuidade da ingestão" — e
a definição do RT-6 na tabela de requisitos diz **a mesma coisa** com outras palavras. Ela
pediu o mecanismo e recebeu o eco.

**A segunda pergunta dela era a mais afiada.** "Flexibilidade de schema?" testava se não
se tratava, na verdade, de *schemaless* — o que contradiria a própria *Bronze*, que
**aplica** *schema* e **valida** conformidade.

**Mecanismo adotado, em duas metades:** (i) o *open table format* absorve o compatível —
campo novo, campo descontinuado, tipo ampliado; o *schema* declarado evolui e os dados já
persistidos seguem legíveis sob a versão anterior, sem reescrita; (ii) a validação
estrutural, já descrita como segunda função derivada, contém o incompatível e o isola para
inspeção. Sem a metade (ii) seria exatamente a "flexibilidade" que ela desconfiou.
Com as duas, é evolução **controlada** — a palavra da própria definição do RT-6.
Ancorado no capítulo 3, linhas 326 e 361.

Parágrafo novo (~85 palavras) em `\entrou{}`.

**Duas decisões de projeto:** (a) não nomear Delta Lake nem Iceberg — o capítulo 4 é
arquitetura e a escolha de formato é instanciação (linha 374); seguido o precedente do
próprio texto, "o *open table format* adotado"; (b) posicionar o parágrafo **junto das
funções derivadas**, e não no fechamento onde ela escreveu, porque o CL-27 propõe
substituir os fechamentos por uma tabela de rastreabilidade — engordar o fechamento agora
seria escrever para jogar fora.

### CL-24 — Silver: exemplo concreto de harmonização semântica · **B** — FEITO
### CL-25 — "referência comum" × "categorias canônicas" · **A** — FEITO
Tratados juntos: a nomenclatura só fecha depois de decidir *o que* o modelo é.

**Diagnóstico do CL-25 — ela achou dois nomes, havia seis** para o alvo da conformação:
`modelo comum da brigada` (1x), `modelo unificado da brigada` (2x), `referência comum`
(1x), `categorias canônicas` (1x), `categorias de referência` (1x). Não eram seis
conceitos: eram **dois** (alvo estrutural e alvo semântico) com três nomes cada.

Unificados em dois nomes da mesma família — responde direto ao "Ex? comum? canônico?"
da margem dela, e "modelo canônico" nomeia um padrão reconhecido de integração, o que
ancora a proposta em literatura estabelecida (serve ao CL-34):

| virou | ocorrências |
|---|---|
| `modelo canônico da brigada` | 2x |
| `termos canônicos` | 3x |

**CL-24 — o que ela estava realmente testando.** *missão* e *tarefa* são doutrinariamente
distintas; ela escolheu o par para perguntar **como o esquema evita colapsar duas coisas
diferentes**. O texto afirmava que "entidades equivalentes podem ser representadas de
formas distintas" sem dizer nunca como se sabe que são equivalentes.

**O Silvio derrubou a primeira resposta**, e com razão: ela assumia que o rótulo de
origem é confiável. Se o sistema não segue a IR 14-06, um campo `tarefa` pode ser, de
fato, uma `missão` — caso que o próprio texto já admite na linha 210 ("a própria IR 14-06
admite exceções à regra de unicidade de nomes, decorrentes de sistemas legados") e nunca
fechava.

**Resposta adotada:** a norma define o espaço de **chegada**, não o de partida. No espaço
de chegada `MISSÃO` e `TAREFA` são classes distintas e nada as funde; a correspondência
a partir de fontes não aderentes não se deduz do nome — é decidida e registrada. E o
lugar onde ela é registrada é o argumento: por ser declarativa e residir na governança,
pode ser revista sem tocar nos fluxos.

**Emenda "fonte única"** (levantada pelo Silvio): sem ela, nada no texto impede que o
YAML lido pelo Spark e o glossário do catálogo divirjam. Três palavras que proíbem o
descasamento no plano da arquitetura.

Parágrafo novo (~100 palavras) inserido após a dimensão semântica, em `\entrou{}`.
Deliberadamente **não** promete linhagem em nível de coluna: o texto da governança só
promete "vinculação aos **conjuntos** de origem" (nível de tabela) + documentação das
regras, e subir a promessa aumentaria a superfície de cobrança no CL-35.

**Apoio cruzado gerado para o CL-34** — formulação mais precisa do candidato (iii) a
diferencial científico: a norma institucional entrega o **vocabulário-alvo já legitimado**
(o que quem constrói do zero não tem), mas **não entrega os mapeamentos**, que seguem
sendo trabalho de administração de dados. Afirmação defensável, diferente de "usamos uma
norma existente".

**Nota para o capítulo 5 (CL-35):** o OpenMetadata não infere linhagem de coluna a partir
de `withColumnRenamed` em PySpark — só de SQL, dbt, API ou UI. Três saídas: (i) empurrar
pela API a partir do mesmo YAML; (ii) gerar SQL a partir do YAML, e aí o catálogo deriva
sozinho; (iii) aceitar linhagem em nível de tabela + vocabulário no catálogo.
**Decisão do Silvio: (iii)**, a mais simples e a única que o texto já promete.
Não verificado na instalação dele — conferir junto ao `infra-dissertacao`.

### CL-26 — "interface de consulta analítica" (p.64) com "?" · **B** — FEITO
`4_Proposta_Arquitetura.tex:220`. A frase tinha **dois** defeitos:

**1. A palavra contradizia a própria escala do texto.** O fechamento da *Silver* diz que
ela constitui "o patamar de **dado consolidado** distinto do dado bruto e do **dado
analítico**". Chamar a interface dela de "consulta analítica" desfaz essa distinção. É a
colisão do CL-33 (`analític*`, 102 usos, 14 colocações) num lugar onde faz estrago — e
provavelmente a razão de ela pôr "?" ali e não nos outros 62 "analíticos" do capítulo.

**2. O destinatário estava errado, e o próprio texto diz isso adiante.** A frase dizia
"acessível à camada transversal de governança". A linha 275 distingue os mecanismos de
governança "da *engine* de consulta analítica, que cumpre **função de acesso, não de
governança**", e a 277 gasta um parágrafo inteiro justificando por que a *engine* aparece
naquela seção sem ferir o RT-5. A frase da *Silver* cometia exatamente o erro que esses
dois parágrafos existem para evitar.

**CL-15 encaixou aqui:** a capacidade que ela sugeriu **já estava declarada** na tabela de
camadas — o Consumo provê acesso "às visões da *Gold* - e, **exploratoriamente, às demais
zonas**". Não era capacidade nova; a prosa da *Silver* é que nomeava errado.

Redação final (escolha do Silvio: "camada funcional relacionada a consumo", para amarrar
na Vista funcional por camadas em vez de criar nome novo):

> A *Silver* é também acessível diretamente pela camada funcional relacionada a consumo,
> viabilizando que o EM interrogue a base consolidada de forma exploratória - ou a utilize
> em visualizações que não dependam das agregações da *Gold*, como a plotagem da posição
> corrente dos elementos - antes mesmo de as visões da *Gold* estarem organizadas.

Marcado com `\saiu{}` + `\entrou{}`.

**Nomenclatura conferida:** a tabela nomeia a **camada** como `Consumo`; `acesso` é a
**função** que ela exerce (linhas 275/277). "Acesso" como nome de camada inventaria uma
que a tabela não tem.

**Nota técnica:** dentro do `\saiu{}` o `\gls{EM}` foi trocado por `EM` puro — `\sout`
(ulem) tem histórico de conflito com `glossaries`, e o trecho será apagado de todo modo.
No `\entrou{}` o `\gls{EM}` está normal.

### CL-27 — tabela consolidada zonas × características × requisitos · **B (grande)** — FEITO
Substituir/complementar os parágrafos de fechamento de cada zona por uma matriz de
rastreabilidade. Resolve parte do CL-33 e demonstra que nenhum requisito ficou órfão.
**Boa ideia dela.** Decidir se substitui ou complementa a prosa.

**Achado colateral, corrigido a pedido do Silvio (01/09/2026):** `4_Proposta:375`
chamava de "Quadro" a única tabela do capítulo assim tratada, enquanto as outras quatro
são chamadas de "Tabela" - e todas usam a mesma macro `\tabela`, que gera legenda
"Tabela". A legenda diria "Tabela 4.5" e o texto "Quadro 4.5". Trocado para
"A Tabela~\ref{tab:mapeamento}". Sem marcação de cor: correção mecânica. Era a única
ocorrência de "Quadro" em todos os capítulos.

**Decisão: substitui.** Os quatro fechamentos de zona (antigas linhas 182, 201, 227 e
252 - `Landing`, `Bronze`, `Silver`, `Gold`) foram marcados em `\saiu{}`. Somavam **595
palavras**, todos abrindo com a mesma frase ("Em sua finalidade arquitetural, a zona X
responde a ... conjuntos de exigências") e repetindo treze vezes o conectivo "Atende
[...], ao [verbo]". O conteúdo factual deles era só o par zona -> requisito; as
justificativas já estavam ditas no corpo de cada subseção. O fechamento da **Governança**
ficou: é ancoragem doutrinária, não segue a fórmula.

**Onde entrou:** subseção nova **4.3.6 "Síntese da cobertura dos requisitos"**
(`sec:arq-sintese-requisitos`), no fim da Seção 4.3, antes da Vista funcional por
camadas. Padrão espelhado da 4.5.4 "Síntese do mapeamento", que já existia para hospedar
o `tab:mapeamento`.

**Desenho da tabela (`tab:cobertura`):** 3 colunas - Elemento | Patamar do dado |
Requisitos atendidos - e 6 linhas, com `\newline` separando os grupos RD / RO / RT para
permitir comparação vertical entre zonas. **Sem coluna de prosa, de propósito:** o
`tab:mapeamento` já tem as mesmas cinco linhas com descrição em prosa, e duas tabelas
paralelas piorariam justamente o CL-33.

**Achado ao montar a matriz (01/09/2026): o RD-5 era o único requisito órfão.**
De 16 requisitos (RD-1..5, RO-1..5, RT-1..6), o RD-5 aparecia só na própria linha da
tabela (85) e na glosa (90) - nenhuma zona, camada ou a governança o reivindicava.

**Descartada a fusão com o RD-4**, proposta pelo assistente e recusada pelo Silvio com
razão: os dois citam manuais diferentes (MC 3.11-10 x EB70-MC-10.205) e são
independentes - RD-4 é regime de chegada (comunicações), RD-5 é topologia (estrutura de
comando). Se o enlace fosse contínuo, RD-4 se dissolveria e RD-5 continuaria inteiro.
Fundir apagaria distinção real para fechar tabela.

**Decisão: opção (d) - manter os cinco e atribuir o RD-5 ao nível da arquitetura**, não
a uma zona. Diagnóstico: o RD-5 é restrição, não função; os fechamentos de zona listam
funções, por isso nenhum o reivindicava. O buraco era da contabilidade, não do
requisito. Mecanismo já escrito no CL-31 (4_Proposta:348).

Escrito em dois pontos, ambos marcados: a glosa da linha 90 passa a dizer que o RD-5
não se satisfaz dentro de uma zona e remete à Subseção 4.5.3; e o bloco do CL-31, em
348, passa a nomear o RD-5 explicitamente. **Consequência para a matriz: ela precisa de
dois níveis de atribuição** - o que se resolve por zona e o que se resolve pela
arquitetura como um todo.

**Apoio cruzado (vindo do CL-18)**: o amarre RD-1 -> *Silver*/*Gold* já foi escrito em
4_Proposta:90 como remissão pontual. É uma parcela adiantada desta matriz - quando ela
for construída, conferir se a remissão do CL-18 vira redundância a remover ou fica como
ponteiro para a tabela.

### CL-28 — Figura 4.5 "dispensável" · **C** — FEITO
Sua leitura: pela contundência, ela quer remoção. Três saídas: (a) remover;
(b) redesenhar com as seis Funções convergindo na Silver; (c) fundir com o CL-27.
**Depende da figura**, que falta (`diagrama5_modelo_gold_medal`).

**Decisão do Silvio (04/09/2026): saída (a) — remover.** A anotação dela é literal:
*"Acho essa figura dispensável, não acrescenta muito ao entendimento do processo"*
(`consideracoes_claudia.md:45`). Não foi preciso ver a figura para executar: a decisão
era de remoção, não de redesenho, e o que ela tocava no fonte estava todo localizável.

**Levantamento antes de mexer.** A figura era chamada uma única vez
(`4_Proposta:270`) e referenciada uma única vez (`\refFig` em `:268`). Era a **última
figura do capítulo 4**, então a remoção não renumera nenhuma outra. Nenhuma menção
manual a "Figura 4.5" no texto (`grep` em todos os `.tex`: zero).

**Aplicado:** a linha `\figura{}` foi **comentada**, não apagada — mesma convenção do
resto do capítulo para texto fora do build —, com nota do item logo acima. A frase de
`:268` que a chamava saiu em `\saiu{}`/`\entrou{}`: o conteúdo que a legenda carregava
não se perdeu, virou prosa (a entidade da Inteligência percorrendo as quatro zonas sem
deixar a Função de origem, e a convergência das demais Funções na *Silver*, "na
consolidação que materializa a função integradora do C2").

**Armadilha encontrada e evitada:** `\saiu{}` é `\textcolor{red}{\sout{#1}}` — ele
**compõe** o argumento. Deixar o `\refFig{diagrama5_modelo_gold_medal}` original dentro
do `\saiu{}` faria o PDF de revisão exibir `Figura ??` em vermelho, exatamente o sintoma
que o `CLAUDE.md` manda não produzir. O trecho tachado traz, por isso, "A Figura 4.5"
como texto literal.

**Consequência para o CL-29 — ele não morre com a figura.** A célula circulada some,
mas a circularidade que ela apontou está também em **prosa**: `4_Proposta:266` e `:345`
listam o C2 como uma das seis Funções ("Comando e Controle, Inteligência, Fogos, Manobra,
Proteção e Sustentação"), enquanto `:29`, `:90` e `:204` o tratam como função integradora
materializada pela *Silver* e completada na *Gold*. O texto já faz a distinção; o que
faltava era dizê-la. O CL-29 segue aberto e agora é **item de prosa**, com o argumento
pronto (ver o apoio cruzado vindo do CL-16).

**Inventário:** as pendências de referência sem destino caem de 13 para 12 —
`diagrama5_modelo_gold_medal` sai da lista de figuras faltantes do
`arquivos-dissertacao/CLAUDE.md`.

### CL-29 — célula "dado analítico" em C2 × Gold · **C** — FEITO
Circularidade: o C2 aparece como uma entre seis Funções, mas é a função integradora,
e os produtos da Gold (PPCOT, PITCIC, COC) são produtos de C2. Ligado ao CL-28.

**Apoio cruzado (vindo do CL-16, 04/09/2026) - aprovado pelo Silvio.** A circularidade se
desfaz pela definição da *Gold*: as visões **não são uma Função de Combate**, são os produtos
do **processo** que consome as seis. O Silvio formulou o eixo assim: até a *Silver* a
progressão é de qualidade; da *Silver* para a *Gold* o que muda é a **proximidade com o uso** -
mesma qualidade, menos esforço para quem consulta. Dois conceitos somados: a viagem por marcos
do medallion e a organização por processo doutrinário (COC, PITCIC, PPCOT, Avaliação), no lugar
que o *data mart* ocupa no DW clássico, para CMTE e EM encontrarem o dado na forma em que já
pensam. Ele mesmo já escreveu a semente disso no parágrafo novo da *Silver*
(granularidade que "pode exigir conhecimento técnico"), e a `tab:cobertura` do CL-27 diz
"Dado organizado segundo o processo de C2 que o consumirá".

**Ataca o item sem depender da Figura 4.5** - que, desde o CL-28 (04/09/2026), foi
**removida**. A célula circulada não existe mais, mas o item permanece: a circularidade
está também em prosa (`4_Proposta:266` e `:345` listam o C2 entre as seis Funções; `:29`,
`:90` e `:204` o tratam como integradora). O CL-29 é agora item de prosa pura, e a redação
cabe no mesmo parágrafo de `:268` que o CL-28 acabou de mexer.

**Correção do alvo (04/09/2026): não é `:268`, é `4_Proposta:351`.** Ao abrir o item,
a Subseção~\ref{sec:arq-map-funcoes} ("Funções de Combate e os elementos da arquitetura")
já traz **metade da resposta escrita**:

> "A arquitetura é agnóstica quanto à Função de Combate produtora: os dados de todas elas
> são tratados de forma uniforme ao longo das zonas, sendo essa uniformidade - e não um
> tratamento especializado por Função - o mecanismo de combate aos silos. **A função
> integradora cabe ao Comando e Controle**, conforme o EB70-MC-10.205, **e é materializada
> tecnicamente na consolidação e harmonização realizada pela *Silver* e na integração e
> disponibilização organizada da *Gold*.**"

Ou seja: o texto **já distingue** o C2-produtor (uma das seis, tratamento uniforme) do
C2-integrador (materializado nas zonas). O que falta é o passo seguinte, que é exatamente
o que o "?" dela pedia: dizer que as visões da *Gold* **não são o acervo de uma sétima
Função**, são os produtos do processo que consome as seis.

**O Silvio já tinha marcado esse parágrafo.** A linha `4_Proposta:349` traz
`% \revisar{Melhorar o parágrafo abaixo - }` - comentada e com a frase inacabada. O
parágrafo que o CL-29 precisa completar é o mesmo que ele próprio sinalizou para melhorar.
Vale perguntar o que ele tinha em mente antes de escrever por cima.

**Aplicado em 04/09/2026, saída (a) escolhida pelo Silvio:** acréscimo em `\entrou{}` ao fim de `4_Proposta:351`, para ele reescrever na revisão do PDF. O argumento: como **produtora**, o C2 é uma das seis Funções e ocupa uma área de negócio no catálogo como as demais; como **integradora**, não é mais uma área de negócio, e sim o processo que consome as seis. As quatro visões da *Gold* são produtos desse processo, não o acervo de uma sétima Função - por isso se organizam pelas fases doutrinárias, e não pela Função que originou o dado.

**Nada foi removido**, logo não há `\saiu{}`: o parágrafo já estava correto, faltava a conclusão. O `% \revisar{}` de `:349` **continua lá**, de propósito - a marcação é dele e o que ele queria melhorar pode ir além do que o CL-29 pedia.

**Decisão do Silvio (04/09/2026):** *não* mexer em "qualidade progressiva" (`:390`) nem na
"progressão de qualidade" (`:392`) - a imprecisão não é problemática o bastante para virar item.

### CL-30 — erros de referência, p.73, 74 e 78 · **NÃO É ERRO**
São os três `\ref{cap:poc}` do capítulo 4. Viraram `??` no PDF apenas porque o build da
qualificação não incluía o capítulo 5. **O fonte está correto.**

**Apoio cruzado** (achado ao trabalhar o CL-22) — auditoria completa das referências
cruzadas dos capítulos 1 a 4: as **23 referências numéricas escritas à mão** resolvem
todas para a seção certa, mais os `Capítulo 1/2/3/4`. Zero quebradas.

| exemplos | aponta para |
|---|---|
| `3:396` → 3.1.2 | Data Warehouse |
| `4:37` → 3.3.3 | Restrições de comunicações táticas |
| `4:51` → 3.2.3 | Qualidade, proveniência e apoio à decisão em C2 |
| `4:29` → 3.3.1 e 3.3.2 | Função de Combate / Processos formais |

A única referência errada do texto era a do CL-22 — e era justamente a que usava `\ref`,
por apontar para o label trocado. Serve para responder a ela com números: um erro
localizado, não um sintoma. `cap:poc` é o único `\ref` órfão que resta, e some quando o
capítulo 5 entrar no build.

### CL-31 — "O que garante isso?" (4.5.3, hierarquia de C2) · **B** — FEITO
Nada no modelo descreve *enforcement*; controle de acesso está fora do escopo.
Saída: dizer que a arquitetura **acomoda** o fluxo hierárquico — recebe o que os
batalhões transmitem pelos enlaces táticos — em vez de afirmar que o garante.

Fechado em 4_Proposta:348 com `\saiu{}`/`\entrou{}`. Duas mudanças: (1) "respeita a
hierarquia" -> "acomoda o fluxo vertical sem impô-lo", alinhando a 4.5.3 ao que a
linha 88 já dizia sobre o RD-5 ("permanece **compatível** com a estrutura
hierárquica"); (2) no lugar da garantia, dois mecanismos que o texto já tinha e não
articulava - a *Landing* como ponto de entrada único (linha 173) e o registro do
batalhão de origem e do momento da recepção no catálogo (linha 179). Não garante,
mas não abre caminho paralelo e deixa a origem verificável.

### CL-32 — "Como?" (preserva a cadeia de responsabilização) · **B** — FEITO
O texto diz o que o sistema **não** faz, não o mecanismo. Articular: linhagem
registrada no catálogo, ausência de automação decisória, rastreabilidade auditável.

Fechado em 4_Proposta:352 com `\saiu{}`/`\entrou{}`. Os três elementos entraram
nomeados: ausência de automação decisória (a *Gold* entrega visões, não conclusões),
linhagem no catálogo reconstituindo quais fontes sustentaram cada visão, e metadados
de proveniência da *Landing* (batalhão transmissor, momento da recepção).

**Apoio cruzado consumido**: a decisão do CL-24/CL-35 (linhagem de nível de tabela,
não de coluna) limitou a redação - o texto promete reconstituir *quais fontes*
sustentaram a visão, nunca *qual campo virou qual*.

Evitado de propósito o fecho "é nesse sentido que..." / "é desse par que decorre...",
já usado no CL-21 e no CL-23 (ver CL-33).

---

## Observações gerais

### CL-33 — "texto bem escrito mas muito repetitivo, o que o torna cansativo" · **C** — ENCERRADO: sem ação (05/09/2026)

**Decisão do Silvio (05/09/2026): não mexer.** O item fica como está; o texto segue
cansativo e isso é aceito. O que já saiu saiu como **efeito colateral** de outros itens -
sobretudo os 595 palavras dos fechamentos de zona no CL-27 - não como campanha própria.
Nada do apoio acumulado abaixo será executado.

**Apoio cruzado (vindo do CL-27) - maior mordida já dada neste item:** os quatro
fechamentos de zona saíram, **595 palavras**, sem perder conteúdo. Restam neste item: a
redução de `analític*` (58 no cap. 4, ~20 colocações) e os `Cabe [verbo]` (4 no cap. 4,
7 no cap. 3). A quarta frente - a estrutura argumentativa repetida a cada zona - o
assistente recomenda **não mexer**: paralelismo entre zonas é escolha expositiva
legítima, e a `tab:cobertura` agora torna esse paralelismo visível sem repeti-lo em
prosa.
Evidência medida no texto atual:

| | cap. 1 | cap. 2 | cap. 3 | cap. 4 | total |
|---|---:|---:|---:|---:|---:|
| `analític*` | 9 | 2 | 28 | **63** | **102** |
| `Cabe [verbo]` | 2 | 2 | 7 | 4 | 15 |

No cap. 4, `analític*` aparece em 14 colocações distintas (consulta analítica,
formato analítico, dado analítico, repositório analítico, elemento analítico,
continuidade analítica, valor analítico...). É a mesma palavra cobrindo sentidos
diferentes — a raiz provável do "?" dela no CL-26.

**Remedido em 04/09/2026**, depois do CL-27 e da revisão geral do Silvio no Overleaf
(texto vivo, linhas comentadas fora):

| | cap. 1 | cap. 2 | cap. 3 | cap. 4 | total |
|---|---:|---:|---:|---:|---:|
| `analític*` | 6 | 2 | 24 | **50** | **82** |
| `Cabe <verbo>` | 2 | 2 | 3 | **6** | 13 |

A tabela anterior (102 no total) está superada e media diferente - o cap. 1 dá 6, não 9.
No cap. 4 o `analític*` caiu de 58 para 50 na revisão geral, e o `Cabe` subiu de 4 para 6.
As colocações no cap. 4 são 18: *visões analíticas* (8), *consulta analítica* (7),
*repositório analítico* (6), *disponibilização analítica* (4), e a cauda vaga
(*continuidade*, *elemento*, *persistência*, *exploração analítica*).

**Apoio cruzado (vindo do CL-29, 04/09/2026) - registro, não reabertura.** O uso mais
confuso de `analític*` no capítulo: `4_Proposta:27` chama a saída da *Bronze* de "**dado
analítico inicial**", enquanto `:274` fixa os patamares como "(bruto, estruturado,
consolidado, **analítico**)" - nessa lista, *analítico* é a *Gold*. A mesma palavra nomeia
a *Bronze* e a *Gold* em dois pontos do mesmo capítulo. Fica registrado para o caso de a
Cláudia apontar o trecho; não vira frente ativa.

**PARADO POR DECISÃO DO SILVIO (04/09/2026).** Não mexer no `Cabe` nem no `analític*`:
*"ela nao reclamou disso de forma precisa e eu gosto de usar o 'cabe' mesmo que fique
repetitivo. isso é uma característica minha nao sua"*. O item segue aberto, mas sem frente
ativa: a mordida grande já foi dada pelo CL-27 (595 palavras) e pela revisão geral, e o
paralelismo entre zonas continua recomendado como **não mexer**. Reabrir só se ela apontar
trecho com precisão.
CL-27 resolve outra parte (os fechamentos de zona repetidos em prosa).

### CL-34 — "o diferencial científico não está claro" · **C** — ENCERRADO: PACIFICADO (04/09/2026)

**Decisão do Silvio, 04/09/2026: sem edição no texto.** O mestrado é **profissional** e o
orientador tratou o ponto diretamente com a professora no dia da qualificação (13/08/2026).
A cobrança está pacificada fora do texto; a Seção "Contribuições da Pesquisa"
(`1_Introducao:108`) permanece como está. O material abaixo fica como registro - serve à
defesa e, eventualmente, ao capítulo 5.

**Apoio cruzado (vindo do CL-07) - a revisão foi conduzida pelo método, não por
conveniência.** Verificado na evidência congelada: Fang (`fang_managing_2015`), a
referência mais citada pelo corpus (42 citações), **não é documento do corpus** - está
em `05_resultados/SCOPUS/analise_vs1/top_cited_documents_global.csv`, que lista
referências mais citadas, não documentos. Ele entrou por **cocitação**. Confirmado que
`main_info.csv` registra `Timespan: 2016-2026` para o corpus analisado, enquanto os
exports brutos contêm material anterior (97 registros pré-2016 num export de 1.522,
136 num de 1.702) - o filtro foi aplicado na consolidação.

Ou seja: a janela temporal delimita o que é **buscado e analisado**, e obras seminais
anteriores emergem pelo mecanismo previsto no próprio TEMAC. Isso é argumento contra a
leitura de que o trabalho é "só engenharia": o portfólio de leitura foi determinado por
um procedimento bibliométrico verificável, não por escolha do autor. Serve igualmente
no CL-06.

**Apoio cruzado (vindo do CL-12) - candidato forte:** materializar o dado bruto é, na
literatura civil, conveniência de projeto (evita nova extração na fonte quando uma
regra muda). No domínio militar isso vira **necessidade**: o pacote chega por janela de
oportunidade e **não pode ser pedido de novo**. O argumento já está escrito no cap. 4,
na justificativa da *Landing* (4_Proposta:35, "caráter irrepetível da transmissão"), e
agora tem o contraponto teórico no cap. 3 (3_Referencial:230). Ou seja: o regime de
chegada militar torna obrigatória uma propriedade que a literatura trata como opcional.
Isso é tese, não engenharia.
~~Aplicar um padrão consagrado a um domínio novo é engenharia, não ciência. Precisa
**elevar a tese**: o que o domínio militar impõe que a literatura não resolve.~~

**Enquadramento corrigido pelo Silvio em 04/09/2026.** A frase riscada é falsa como
absoluto - levada a sério, invalidaria a própria DSR, em que o artefato *é* a
contribuição (`dresch_design_2015` está no `.bib`, nunca citado; o cap. 2 declara
Estudo de Caso, e é assim que fica). Desenvolver a partir de revisão sistemática é
pesquisa. Não reabrir o item por essa via.

Candidatos levantados, mantidos como registro:
1. **regime de chegada intermitente** por janelas de oportunidade, que quebra a
   premissa de ingestão contínua das arquiteturas correntes (AN-02, AN-16);
2. **proveniência como requisito operacional** de confiança para decisão sob
   pressão de tempo;
3. **harmonização semântica ancorada em norma institucional preexistente**
   (IR 14-06) em vez de vocabulário construído do zero;
4. **materialização aberta e soberana** (AN-16) — o que os sistemas internacionais
   pressupõem e aqui não se pode pressupor.

Idem CL-06.

### CL-35 — "o que de fato será implementado como prova de conceito?" · **D**
Exige um trecho único e explícito: o que se implementa, com quais dados, em que
escala, sob qual critério de validação. **Depende do capítulo 5.**

### CL-36 — focar nas zonas iniciais; hierarquias militares · **D**
Saída pragmática oferecida por ela: concentrar a PoC em Landing/Bronze (talvez
Silver), sem prometer as quatro zonas, e tratar as hierarquias (retoma o
Alfa/Bravo/Charlie do CL-17). **Depende do capítulo 5.**

### CL-37 — "a visão final apenas ilustrará o provável resultado" · **D**
Autoriza tratar a Gold de forma ilustrativa na PoC. **Depende do capítulo 5.**

---

## Bloqueios

**Figuras ausentes** — travam CL-13 e CL-14 (CL-28 e CL-29 resolvidos em 04/09/2026,
com a remoção da Figura 4.5):
`diagrama1_projeto` (Fig. 4.1) e `diagrama5_modelo_gold_medal` (Fig. 4.5), além de
`triag_info_pesq`, `esquema_dw`, `esquema_dl`, `esquema_data_pond`,
`esquema_zonas_camadas_dl`.

**Capítulo 5 ausente** — trava CL-35, CL-36, CL-37 (e informa CL-05).

**Resposta dela** — CL-17 ("Alfa Bravo Charlie?") e CL-19 ("Genesis? Astros?").
CL-01 e CL-02 saíram desta lista: o primeiro foi verificado pelo Silvio, o segundo
resolvido com a data real da qualificação (13/08/2026).

**`.bib` chegou ao repo em 04/09/2026** (`bibliografia.bib`, trazido do Overleaf junto com a
revisão geral). As duas conferências de data que estavam travadas, achadas ao trabalhar o
CL-07 e nenhuma apontada pela banca, foram fechadas:

1. **Fang: 2015 ou 2016?** O Quadro do cap. 2 exibe "Fang (2016)" com a chave
   `fang_managing_2015`. A evidência congelada dá 2015 (`scopus_export_...ba78f0cf.csv`:
   `Year: 2015`, `IEEE-CYBER 2015`, DOI `10.1109/CYBER.2015.7288049`). O gerador de
   citação da IEEE devolve 2016 porque os anais saíram depois - foi daí que veio a
   divergência. **Recomendação: alinhar em 2015**, que é o que a base registrou; o
   risco é a lista de referências e a tabela discordarem no mesmo documento.
   **RESOLVIDO (04/09/2026):** o `.bib` registra `year = {2015}`. `2_Metodologia:79` alinhado
   para "Fang (2015)".
2. **Quando emergiu o Lakehouse** — os documentos discordam entre si: o `.tex` dizia "a
   partir de 2020", o relatório bibliométrico diz "2019-2020", e a citação é o paper de
   2021 (CIDR). A menção saiu do cap. 2 com o CL-07.
   **RESOLVIDO (04/09/2026):** nada a alinhar - o cap. 3 (`3_Referencial:318`) atribui o
   paradigma ao paper de 2021, coerente com o "cunhado em 2021" que o Silvio escreveu no
   cap. 2 na revisão geral. Não sobrou nenhum "a partir de 2020".

**Auditoria completa do `.bib` (04/09/2026).** 149 entradas, 95 chaves citadas no texto vivo,
todas resolvem; nenhuma chave duplicada. Registros para não se perderem:

- `fogarty_story_2002` e `inmon_building_1992` não existem no `.bib`, mas só aparecem em
  **linhas comentadas** (`3_Referencial:82,86`) - não compilam, não avisam. O vizinho vivo do
  segundo é `inmon_building_2002`.
- **Chaves do Zotero com sobrenome do editor dos anais, não do autor - estão CORRETAS, não
  "consertar":** `song_handle_2020` é Eichler et al. (HANDLE), `ordonez_leveraging_2019` e
  `laender_modeling_2019` são Giebler et al. Conferidos autor e ano de todos os rótulos
  "Autor (ano)~\cite{}" do texto: a única divergência real era o Fang.
- `apache_software_foundation_apache_2026-1` é o **Iceberg** (o sem sufixo é Hudi, o `-2` é
  Paimon). O estilo da classe é `babunsrt`, numérico, então as três entradas "Apache Software
  Foundation 2026" não colidem.
- **Siglas seguem inverificáveis aqui:** 27 chaves `\gls{}` em uso e nenhum `\sigla{}`
  definido nos arquivos presentes - as definições ficaram no Overleaf, como as figuras.


---

## Apoio cruzado — Landing (usar em AN-10 e CL-14)

O Inmon recomenda que o dado **saia** do *raw pond*: *"once raw data passes from the
raw data pond to the analog... pond, it is best to remove the source data from the raw
data pond... One useful measure of quality for the raw data pond is how small it is and
how quickly data passes out of the pond."*

Se a *Landing* retém o pacote original, há divergência num ponto em que ele é explícito.
**Não é erro** — decisão do Silvio, e justificada: proveniência para decisão militar não
era o problema de negócio dele em 2016. Mas divergência explícita é argumento e
divergência silenciosa parece descuido. Como a Cláudia pede justamente o diferencial
(CL-34), contrariar o Inmon *com motivo declarado* trabalha a favor.

Vale a distinção geral: no capítulo 3 há obrigação de fidelidade (está-se **descrevendo**
a literatura); no capítulo 4, não (está-se **projetando**).
