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

**38 itens.** 8 A · 16 B · 8 C · 4 D · 2 encerrados sem ação

15 feitos: CL-02, 03, 09, 10, 15, 18, 20, 21, 22, 23, 24, 25, 26, 31, 32. CL-01 e CL-38 encerrados sem ação. CL-30 confirmado como não-erro (falta comunicar a ela).

### Apoio cruzado

Material achado ao trabalhar um item que serve de argumento em **outro**. Antes de
abrir qualquer item, `grep -n "CL-XX\|AN-XX" backlog_claudia.md` — o apoio pode estar
registrado longe do item a que pertence.

| serve em | o quê | veio de |
|---|---|---|
| CL-11 | Inmon admite que o *application pond* é "notoriously unintegrated" | CL-10 |
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

### CL-04 — "Alguma investigação sobre os sistemas e dados reais envolvidos?" · **B**
Delimitação de escopo. **Provavelmente já resolvido** pelo AN-04 (parágrafo sobre
Pacificador, C2 em Combate e FAC2FTer). Conferir se o texto novo alcança este ponto
ou se falta remissão a partir da delimitação de escopo.

### CL-05 — "Mas como demonstrar que a solução proposta é útil?" · **C**
Sobre "Integração com sistemas legados específicos do EB". Pede critério de
validação. Amarra com CL-35 (escopo da PoC).

### CL-06 — justificativa acadêmica · **C**
> "o fato de não haver uma solução específica para o EB não chega a caracterizar
> uma contribuição acadêmica."

**Mesma crítica do CL-34.** Ela levantou no cap. 1 e repetiu no fecho: leu tudo e a
resposta não apareceu. Tratar os dois juntos.

---

## Capítulo 2 — Metodologia

### CL-07 — corte temporal de 2016 · **B**
> "Trabalhos anteriores a 2016 não contemplam as abordagens que representam o
> estado da arte atual" → ela: *"no que se refere a? melhorar a justific."*

Falta dizer **em qual disciplina** o corte vale. Candidato: a publicação do
paper do Delta Lake / consolidação dos *open table formats*.

---

## Capítulo 3 — Referencial Teórico

### CL-08 — enxugar detalhamentos · **C**
> "poderia rever c/ base no que realmente precisa p/ entender a minha proposta."

Decisão de escopo, não de redação. Ligada ao CL-33.

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

### CL-11 — "silos disjuntos" / "Será? Literatura marketeira?" · **C**
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

### CL-12 — "O que essa definição em zonas tem de diferente da ETL?" · **B**
Sobre a Figura 3.4. Pergunta legítima: zonas persistem estados intermediários e
são consultáveis; ETL move dados entre pontos sem materializar os estágios.

---

## Capítulo 4 — Proposta de Arquitetura

### CL-13 — Figura 4.1: explicitar as zonas · **D**
"Engine de processamento (orquestrado por pipelines)" esconde as zonas.
**Falta o arquivo da figura** (`diagrama1_projeto`).

### CL-14 — "Há dados que chegam direto na Bronze?" · **D**
Ambiguidade visual da Fig. 4.1. O texto já resolve (RD-4). Depende da figura.

**Apoio cruzado** (achado ao trabalhar o CL-10) — o Inmon admite explicitamente o desvio da zona de entrada —
*"It is worthy of note that **data does not have to pass through the raw data pond**,
although it almost always does. If the developer is sophisticated, it is possible to
send the data directly into the analog, application or the textual pond."*
O criador do modelo de *ponds* autoriza o bypass. Sustenta a resposta com autoridade,
não com engenharia própria.

### CL-15 — Silver com dados prontos para consulta e visualização · **B** — FEITO
Tratado junto com o CL-26: são o mesmo ponto visto por dois lados, e por isso pareciam
pedidos opostos.

### CL-16 — saída da Gold "não necessariamente visão analítica" · **B**
BI, API e relatórios também consomem a Gold. Rotular a saída de forma mais ampla.

### CL-17 — "Alfa Bravo Charlie?" · **D**
Junto a "Sistemas subsidiários das Funções de Combate". Hipótese: hierarquia do
FAC2FTer (Charlie = ponta, Bravo = intermediária, Alpha = comando). **Confirmar com ela.**

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

### CL-19 — "Alfa Bravo?", "Genesis?", "Astros?" · **D**
Quais sistemas do EB entrariam na integração. **Perguntar novamente a ela.**

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

### CL-27 — tabela consolidada zonas × características × requisitos · **B (grande)**
Substituir/complementar os parágrafos de fechamento de cada zona por uma matriz de
rastreabilidade. Resolve parte do CL-33 e demonstra que nenhum requisito ficou órfão.
**Boa ideia dela.** Decidir se substitui ou complementa a prosa.

**Apoio cruzado (vindo do CL-18)**: o amarre RD-1 -> *Silver*/*Gold* já foi escrito em
4_Proposta:90 como remissão pontual. É uma parcela adiantada desta matriz - quando ela
for construída, conferir se a remissão do CL-18 vira redundância a remover ou fica como
ponteiro para a tabela.

### CL-28 — Figura 4.5 "dispensável" · **C**
Sua leitura: pela contundência, ela quer remoção. Três saídas: (a) remover;
(b) redesenhar com as seis Funções convergindo na Silver; (c) fundir com o CL-27.
**Depende da figura**, que falta (`diagrama5_modelo_gold_medal`).

### CL-29 — célula "dado analítico" em C2 × Gold · **C**
Circularidade: o C2 aparece como uma entre seis Funções, mas é a função integradora,
e os produtos da Gold (PPCOT, PITCIC, COC) são produtos de C2. Ligado ao CL-28.

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

### CL-33 — "texto bem escrito mas muito repetitivo, o que o torna cansativo" · **C**
Evidência medida no texto atual:

| | cap. 1 | cap. 2 | cap. 3 | cap. 4 | total |
|---|---:|---:|---:|---:|---:|
| `analític*` | 9 | 2 | 28 | **63** | **102** |
| `Cabe [verbo]` | 2 | 2 | 7 | 4 | 15 |

No cap. 4, `analític*` aparece em 14 colocações distintas (consulta analítica,
formato analítico, dado analítico, repositório analítico, elemento analítico,
continuidade analítica, valor analítico...). É a mesma palavra cobrindo sentidos
diferentes — a raiz provável do "?" dela no CL-26.
CL-27 resolve outra parte (os fechamentos de zona repetidos em prosa).

### CL-34 — "o diferencial científico não está claro" · **C** — CRÍTICA MAIS SÉRIA
Aplicar um padrão consagrado a um domínio novo é engenharia, não ciência. Precisa
**elevar a tese**: o que o domínio militar impõe que a literatura não resolve.
Candidatos já no material:
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

**Figuras ausentes** — travam CL-13, CL-14, CL-28, CL-29:
`diagrama1_projeto` (Fig. 4.1) e `diagrama5_modelo_gold_medal` (Fig. 4.5), além de
`triag_info_pesq`, `esquema_dw`, `esquema_dl`, `esquema_data_pond`,
`esquema_zonas_camadas_dl`.

**Capítulo 5 ausente** — trava CL-35, CL-36, CL-37 (e informa CL-05).

**Resposta dela** — CL-17 ("Alfa Bravo Charlie?") e CL-19 ("Genesis? Astros?").
CL-01 e CL-02 saíram desta lista: o primeiro foi verificado pelo Silvio, o segundo
resolvido com a data real da qualificação (13/08/2026).


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
