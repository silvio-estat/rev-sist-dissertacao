# Backlog — considerações do Prof. Andrei (qualificação, abr/2026)

Derivado de `consideracoes_banca/qualificacao/consideracoes_andrei.md`.
Âncoras localizadas por `grep` em `arquivos-dissertacao/` em 30/08/2026.

**Regra:** nenhuma edição sem item. Um commit por item, com o ID na mensagem.

**Tipos:** **A** mecânico (editar direto) · **B** esclarecimento local (propor redação)
· **C** argumentativo (decisão do Silvio) · **D** bloqueado (falta insumo).

| ID | Cap | Pedido do Andrei | Âncora no fonte | Tipo | Status |
|---|---|---|---|---|---|
| AN-01 | Resumo | Rever se as palavras em maiúscula deveriam estar assim | `resumo.tex` | B | ✔️ **feito** — `a5ead34` (resumo já conforme) |
| AN-02 | Resumo | Redação dava a entender que o projeto atacaria a restrição de *streaming* | `resumo.tex` + `abstract.tex` | B | ✔️ **feito** — `70ab91f` |
| AN-03 | Resumo | Conferir tradução de "cenário operacional comum" → *Common Operational Picture* | `abstract.tex` | B | ✔️ **resolvido sem edição** — tradução correta; Silvio confirma ao Andrei |
| AN-04 | 1 | Qual o contexto atual do Exército em arquitetura para subsidiar o C2? | `1_Introducao` | C | ⏸ depende de informação que só o Silvio tem |
| AN-05 | 1 | Verificar as palavras com iniciais maiúsculas | 4 capítulos, 26 ocorrências | B | ✔️ **feito** — `a5ead34` |
| AN-06 | 2 | Por que PRISMA **e** TEMAC? | `2_Metodologia:42, 44` | B | ✔️ **feito** — `dc40778` |
| AN-07 | 2 | Não se convenceu do descarte da IEEE Xplore (principal base de TI) | `2_Metodologia:53` | C | ✅ pronto — há material forte no repo |
| AN-08 | 3 | Ajustar "monre" → "more" na definição de Dixon | `3_Referencial_Teorico:148` | A | ⚠️ **já está "more"** — confirmar com o Andrei |
| AN-09 | 3 | *(achado novo)* citação do Dixon está incompleta | `3_Referencial_Teorico:148` | A | ✔️ **feito** — `6da3ee0` |
| AN-10 | 4 | Por que uma *Landing Zone* a mais, se a *Bronze* não bastava? | `4_Proposta:33` | **C** | ✔️ **feito** — `fea166c` |
| AN-11 | 4 | Marcou "deduplicação avançada" — por que "avançada"? | `4_Proposta:212` | B | ✔️ **feito** — `9240982` |
| AN-12 | 4 | Sugestão p/ a PoC: governança e linhagem em todas as camadas (auditoria) | cap. 5 | C | 🔒 capítulo 5 não está no repo |
| AN-14 | 4 | *(achado novo)* "nomeada como denominada" — duplicação | `4_Proposta:230` | A | ✔️ **feito** — `fb3608c` |
| AN-15 | todos | *(achado novo)* títulos de seção misturam *Title Case* e frase capitalizada | `\subsection{Governança de dados}` × `\subsubsection{Governança de Dados}` | B | ⏸ aguarda decisão |
| AN-13 | 4 | Erro de referenciação "Capítulo ??" na p.78 | `4_Proposta:280, 314, 372` | — | ❌ **não é erro** — ver abaixo |

## Notas por item

### AN-01 — maiúsculas do resumo: falta um critério, não uma correção
Termos capitalizados hoje em `resumo.tex`: Exército Brasileiro, Cenário Operacional
Comum (2×), Lakehouse, Medallion, Prova de Conceito (3×), TEMAC, Comando e Controle,
PRISMA, Funções de Combate (2×), Landing/Bronze/Silver/Gold, Estado-Maior.

A maioria se defende: nome próprio (Exército Brasileiro, Estado-Maior), designação
formal de doutrina (Cenário Operacional Comum e Funções de Combate são termos
nomeados no EB70-MC-10.205), nome de padrão ou tecnologia (Lakehouse, Medallion,
nomes das zonas) e sigla (TEMAC, PRISMA).

O caso frágil é **"Prova de Conceito"**: é método, não designação formal — minúscula
seria o padrão. Decidido o critério, aplicar aos quatro capítulos de uma vez.

### AN-02 — o resumo enquadra a restrição como problema, e é por isso que o Andrei leu assim
O resumo diz: "Esse desafio **é agravado** pelas restrições dos meios de comunicações
táticas... que condicionam a chegada dos dados em pacotes consolidados". Apresentada
como agravante do problema, a restrição naturalmente sugere que o trabalho vá atacá-la.

A introdução já resolve isso e o resumo não: `1_Introducao:18` diz "Essa realidade
inviabiliza fluxos contínuos de dados (*streaming*) entre escalões e **fundamenta a
escolha** de um modelo de ingestão em lote (*batch*), que condiciona toda a arquitetura
proposta". Falta ao resumo esse movimento — declarar que a restrição é **premissa
aceita que molda o desenho**, não obstáculo a vencer. Correção curta, de uma oração.

### AN-03 — a tradução está correta
*Common Operational Picture* (COP) é o termo consagrado na doutrina OTAN e norte-americana,
e é o equivalente estabelecido de "Cenário Operacional Comum" (COC) — o próprio
`4_Proposta:230` trata o COC como o produto previsto no EB70-MC-10.205. Traduzir
literalmente ("Common Operational Scenario") é que seria erro. Basta confirmar ao Andrei,
sem alteração no texto.

### AN-08 — o typo já não existe
A linha 148 diz "in a **more** natural state". Ou o Silvio já corrigiu depois da
qualificação, ou a versão que o Andrei leu era outra. Confirmar antes de dar por
fechado.

### AN-09 — mas a citação do Dixon está errada de outro jeito (achado novo)
O texto traz:

> "The contents of the data lake stream in **from to** fill the lake"

O original de Dixon (2010) é "stream in **from a source** to fill the lake". Falta
"a source" numa **citação direta** — erro mais grave que o typo original, porque
deturpa a fonte. Correção mecânica, mas confirmar contra o original antes.

### AN-13 — não é erro de referenciação
As três `Capítulo~\ref{cap:poc}` só viraram `??` porque os capítulos 5 e 6 ficaram
fora do build da qualificação. As referências estão corretas e resolvem-se sozinhas.
**Não tocar.**

### AN-07 — a resposta existe e está forte, só não está no texto
Hoje `2_Metodologia:53` justifica em uma frase: a IEEE "não disponibilizava a lista
de referências dos trabalhos". É pouco para quem considera a IEEE a principal base de
TI. Material disponível neste repositório para reforçar:

- `HISTORICO.md` §4: o campo `CR` ficava 100% ausente ao concatenar; a IEEE publica só
  a contagem de citações, não as referências — o que inviabiliza cocitação e
  acoplamento bibliográfico, que **são** o método TEMAC.
- Scopus e WoS já indexam a IEEE (argumento de não-perda de cobertura).
- `06_triagem/analise_completude_scopus/`: a análise de completude e sombreamento
  entre bases — evidência empírica de quanto da IEEE já estava coberto.

O ponto a decidir é de tese: o descarte não foi por conveniência, foi porque a IEEE
não fornece o insumo que o método exige. Vale checar os números da análise de
completude antes de redigir.

### AN-05 — maiúsculas do capítulo 1
Ocorrências agrupadas: "Comando e Controle" (~8), "Exército Brasileiro" (~7),
"Consciência Situacional" (2), "Funções de Combate" (1), "Data Lake" (2), "Dados" (3).
Termos doutrinários consagrados justificam maiúscula; "Dados" solto no meio da frase,
não. Decisão de padrão — depois aplicar consistentemente nos 4 capítulos.

## Placar

| Situação | Itens |
|---|---|
| ✔️ Feitos (8 de 12) | AN-01, AN-02, AN-03, AN-05, AN-06, AN-09, AN-10, AN-11, AN-14 |
| ✅ Resta trabalhar | **AN-07** (descarte da IEEE) |
| ⏸ Novo, aguarda decisão | AN-15 (títulos de seção) |
| 🔒 Bloqueados (falta arquivo) | AN-12 |
| ⏸ Depende de informação do Silvio | AN-04 |
| ⚠️ Confirmar premissa | AN-08 |
| ❌ Não é erro | AN-13 |


## Pendência aberta pelo Silvio (30/08/2026) — escopo real da PoC

Ao decidir o AN-11, o Silvio levantou: *"eu explico essa diferença? vou conseguir fazer
isso realmente?"* — porque pretende trazer a modelagem de dados do **FAC2FTER** e do
**Pacificador** para refazer os dados sintéticos da Prova de Conceito.

A dúvida não bloqueou o AN-11 (a opção adotada não promete técnica alguma), mas é a
questão de fundo que a Cláudia levanta de frente: *"O que de fato será implementado
como prova de conceito?"*. Tratar com os modelos reais em mãos, junto do AN-12.

**Observação:** os modelos reais tendem a *ajudar*. Duas fontes que representam a mesma
entidade com chaves e convenções distintas são, ao mesmo tempo:
- o caso concreto de deduplicação entre fontes (AN-11);
- o exemplo de harmonização semântica que a Cláudia pediu ("missão" × "tarefa");
- a resposta ao "o que dá suporte à integração" da linha RD-1 (Cláudia, Tabela 4.1).


## Correção de análise (30/08/2026)

Uma varredura anterior deu 6 referências a tabelas como quebradas. **Estava errado.**
A classe UnB-CIC define rótulos por macro — `\tabela{legenda}{rotulo}{...}` e
`\figura[pos]{legenda}{rotulo}{...}` — e referencia por `\refTab{}` / `\refFig{}`.
Procurar só `\label{}` produz falso positivo. **As tabelas estão todas resolvidas.**

O que de fato falta são **7 figuras**, sem nenhuma chamada `\figura{}` nos arquivos
presentes: `triag_info_pesq`, `esquema_dw`, `esquema_dl`, `esquema_data_pond`,
`esquema_zonas_camadas_dl`, `diagrama1_projeto` (Figura 4.1) e
`diagrama5_modelo_gold_medal` (Figura 4.5).

As duas últimas são justamente as que a Cláudia comenta — a 4.1 ("explicitar melhor o
processo, sem esconder as zonas") e a 4.5 ("acho essa figura dispensável"). **Sem elas,
os itens dela sobre figuras ficam bloqueados.**


## AN-10 — por que virou tipo C

A resposta que existia ("a Landing materializa a fronteira entre comunicações táticas e
repositório analítico") não resistia: o Silvio observou que **a Bronze também poderia ser
essa fronteira**. Não era caso de tornar visível uma resposta pronta, e sim de construí-la.

O argumento adotado, centrado no que o domínio impõe:

1. **A janela de oportunidade é irrepetível.** Pacote que chega por enlace HF/VHF não
   se pede de novo. Logo a aplicação de *schema* não pode ser destrutiva: se a Bronze
   for o primeiro pouso, parser errado ou tipo inesperado significa perda definitiva.
2. **Reconstrutibilidade.** Preservado o original, a Bronze é regerável quantas vezes
   for preciso.
3. **Nem tudo vira tabela.** Áudio e imagem não admitem *schema*; a Bronze recebe
   metadados extraídos, o artefato fica na Landing. Isso acomoda o caso sem obrigar o
   Silvio a decidir agora o fluxo desses formatos.
4. **A Bronze só é útil se tiver garantia única:** tudo o que está nela é estruturado e
   consultável. A Landing é o que impede a Bronze de virar depósito.

Respaldo já citado no próprio texto (`4_Proposta:8`): Giebler, Sharma e Zhao acrescentam
a zona de aterrissagem antes da Bronze. O Medallion de três zonas é a simplificação de um
fornecedor; os modelos de referência acadêmicos usam quatro.

**Descartado como argumento:** "mais zonas dão flexibilidade para decidir depois".
Intuição correta do Silvio, mas indefensável em banca — soa como indecisão.

## Pendência de fechamento — marcações de cor

Reescritas de parágrafo são marcadas com `\entrou{}` (azul) e `\saiu{}` (vermelho
tachado), macros da própria classe UnB-CIC, para o Silvio fazer a revisão geral lendo o
PDF. **Precisam ser retiradas antes da versão final.** Localizar com
`grep -n "entrou{\|saiu{" *.tex`. Hoje: 1 ocorrência em `4_Proposta_Arquitetura.tex`.
