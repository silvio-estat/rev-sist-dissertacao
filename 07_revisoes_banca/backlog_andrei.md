# Backlog — considerações do Prof. Andrei (qualificação, abr/2026)

Derivado de `consideracoes_banca/qualificacao/consideracoes_andrei.md`.
Âncoras localizadas por `grep` em `arquivos-dissertacao/` em 30/08/2026.

**Regra:** nenhuma edição sem item. Um commit por item, com o ID na mensagem.

**Tipos:** **A** mecânico (editar direto) · **B** esclarecimento local (propor redação)
· **C** argumentativo (decisão do Silvio) · **D** bloqueado (falta insumo).

| ID | Cap | Pedido do Andrei | Âncora no fonte | Tipo | Status |
|---|---|---|---|---|---|
| AN-01 | Resumo | Rever se as palavras em maiúscula deveriam estar assim | `resumo.tex` | B | ✅ pronto |
| AN-02 | Resumo | Redação dava a entender que o projeto atacaria a restrição de *streaming* | `resumo.tex` (+ `1_Introducao:18, 101`) | B | ✅ pronto |
| AN-03 | Resumo | Conferir tradução de "cenário operacional comum" → *Common Operational Picture* | `abstract.tex` | B | ✅ tradução está certa — só confirmar |
| AN-04 | 1 | Qual o contexto atual do Exército em arquitetura para subsidiar o C2? | `1_Introducao` | C | ⏸ depende de informação que só o Silvio tem |
| AN-05 | 1 | Verificar as palavras com iniciais maiúsculas | `1_Introducao`, ~20 ocorrências | B | ✅ pronto para decidir |
| AN-06 | 2 | Por que PRISMA **e** TEMAC? | `2_Metodologia:42, 44, 51` | B | ✅ pronto |
| AN-07 | 2 | Não se convenceu do descarte da IEEE Xplore (principal base de TI) | `2_Metodologia:53` | C | ✅ pronto — há material forte no repo |
| AN-08 | 3 | Ajustar "monre" → "more" na definição de Dixon | `3_Referencial_Teorico:148` | A | ⚠️ **já está "more"** — confirmar com o Andrei |
| AN-09 | 3 | *(achado novo)* citação do Dixon está incompleta | `3_Referencial_Teorico:148` | A | ✔️ **feito** — `6da3ee0` |
| AN-10 | 4 | Por que uma *Landing Zone* a mais, se a *Bronze* não bastava? | `4_Proposta:8, 33, 35` | B | ✅ pronto |
| AN-11 | 4 | Marcou "deduplicação avançada" — por que "avançada"? | `4_Proposta:212` | B | ✔️ **feito** — `9240982` |
| AN-12 | 4 | Sugestão p/ a PoC: governança e linhagem em todas as camadas (auditoria) | cap. 5 | C | 🔒 capítulo 5 não está no repo |
| AN-14 | 4 | *(achado novo)* "nomeada como denominada" — duplicação | `4_Proposta:230` | A | ✔️ **feito** — `fb3608c` |
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
| ✔️ Feitos | AN-09, AN-11, AN-14 |
| ✅ Prontos para trabalhar | AN-01, AN-02, AN-03, AN-05, AN-06, AN-07, AN-10 |
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
