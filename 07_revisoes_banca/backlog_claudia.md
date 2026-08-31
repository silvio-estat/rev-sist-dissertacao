# Backlog — Prof.ª Dr.ª Maria Cláudia Cavalcanti (IME)

Fonte: `consideracoes_banca/qualificacao/consideracoes_claudia.md`.
Qualificação em 21/04/2026; considerações recebidas em agosto/2026.

Mesma classificação usada no backlog do Andrei:

| | significado | conduta |
|---|---|---|
| **A** | mecânico — erro objetivo | edito direto, sem discussão |
| **B** | esclarecimento local | proponho redação, você aprova |
| **C** | argumentativo / de escopo | **não edito**; decisão é sua |
| **D** | bloqueado | falta figura, capítulo 5 ou resposta dela |

**37 itens.** 6 A · 16 B · 8 C · 7 D

---

## Capa e folha de rosto

### CL-01 — texto do objetivo na capa · **D**
> "Checar como outros colegas colocaram na qualificação."

Verificado: a classe já gera `Mestrado Profissional` e
`apresentada como requisito parcial para qualificação do` (`UnB-CIC.cls:67,627-628`).
O texto no fonte está correto. Provável não-problema — mas ela pediu comparação
com outros trabalhos. **Perguntar ao orientador.**

### CL-02 — data da capa · **D**
`monografia.tex:25` → `\diamesano{21}{abril}{2026}`, inalterado desde a tag
`qualificacao-ago2026`. Abril **é** a data da qualificação. A anotação
("abril → agosto") é ambígua. **Perguntar a ela** ou decidir qual data vai no depósito.

### CL-03 — "Prof.ª Dr.ª" ou "Profa. Dra." · **B**
`monografia.tex:27` → `\membrobanca{\prof[a] \dr[a] Maria Cláudia Cavalcanti}`.
A classe (`UnB-CIC.cls:351,355`) renderiza **`Prof.a Dr.a`** — que não é nenhuma das
duas formas pedidas. **A classe é intocável.** Saída: escrever literal no
`monografia.tex`, sem os macros. Decidir qual das duas formas.

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

### CL-09 — concordância "Giebler et al. destaca" · **A**
`3_Referencial_Teorico.tex:220` → `destaca` → `destacam`. Confirmado.

### CL-10 — "por seu formato" nos *data ponds* · **A**
`3_Referencial_Teorico.tex:220`:
> "Inmon propôs uma arquitetura que categoriza os dados **por seu formato** em
> diferentes partições, denominadas *data ponds*."

Ela tem razão e o **próprio parágrafo se contradiz** duas frases depois: "os dados
são armazenados de acordo com sua **natureza**". Os *ponds* separam por origem
(analog = sensores, application, textual, archival = retenção), não por formato.
Ela sugeriu "estrutura"; **"natureza"** é melhor — já é a palavra do texto.

### CL-11 — "silos disjuntos" / "Será? Literatura marketeira?" · **C**
`3_Referencial_Teorico.tex:224`. Sua posição registrada: não é o caso, Giebler
publicou na IEEE. Opção de baixo custo: atribuir explicitamente a crítica à autora
("na avaliação de Giebler et al., ...") em vez de afirmá-la em voz própria.

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

### CL-15 — Silver com dados prontos para consulta e visualização · **B**
Ex.: mapas com posição de elementos. Conferir se a subseção da Silver já menciona
a interface de consulta própria dela. **Cuidado: colide com CL-26.**

### CL-16 — saída da Gold "não necessariamente visão analítica" · **B**
BI, API e relatórios também consomem a Gold. Rotular a saída de forma mais ampla.

### CL-17 — "Alfa Bravo Charlie?" · **D**
Junto a "Sistemas subsidiários das Funções de Combate". Hipótese: hierarquia do
FAC2FTer (Charlie = ponta, Bravo = intermediária, Alpha = comando). **Confirmar com ela.**

### CL-18 — Tabela 4.1, RD-1: "o que dá o suporte à 'integração'" · **B**
Explicitar qual elemento arquitetural materializa a função integradora — a Silver,
pela conformação entre Funções de Combate. Cabe na própria célula ou por remissão.

### CL-19 — "Alfa Bravo?", "Genesis?", "Astros?" · **D**
Quais sistemas do EB entrariam na integração. **Perguntar novamente a ela.**

### CL-20 — conversão colunar nem sempre necessária · **B**
`4_Proposta_Arquitetura.tex:189`. Nem todo consumo é analítico/agregado; há consulta
pontual. **Mesmo ponto do CL-21 — tratar juntos.**

### CL-21 — "mas se preserva, pra que a conversão?" · **B**
`4_Proposta_Arquitetura.tex:191`. Contradição aparente. Resposta: a preservação é de
**fidelidade lógica** (valores, nomenclatura, granularidade); a conversão é de
**representação física** (linha → coluna). Nenhuma altera conteúdo.

### CL-22 — erro de referência, p.60 · **A** — CONFIRMADO
`4_Proposta_Arquitetura.tex:189`:
> "...característica dos *open table formats* discutidos na
> Subseção~`\ref{sec:arq-zonas}` do Capítulo~3"

`sec:arq-zonas` está **no capítulo 4**. O cap. 3 tem um único label:
`sec:lakehouse` (`3_Referencial_Teorico.tex:308`), que é onde os *open table
formats* são de fato discutidos (Delta Lake, Iceberg, Hudi, Paimon, Lance — linhas
326-361). Correção: trocar por `\ref{sec:lakehouse}` e remover "do Capítulo~3"
(o `\ref` já resolve).

### CL-23 — RT-6: "Como isso se dá? Flexibilidade de schema?" · **B**
Pede o **mecanismo**, não a alegação de conformidade. Resposta: *schema evolution*
nativo do open table format — campo novo, removido ou de tipo alterado é acomodado
sem quebrar a leitura do que já foi persistido. Dizer como convive com a validação
estrutural da ingestão.

### CL-24 — Silver: exemplo concreto de harmonização semântica · **B**
Ela testa com um par real do PPCOT — **"missão" e "tarefa"** — e pede que o texto
mostre como o esquema classe/propriedade/representação da IR 14-06 reconcilia
divergências entre sistemas finalísticos. Hoje está inteiramente abstrato.

### CL-25 — "referência comum" × "categorias canônicas" · **A**
Usados como equivalentes sem definição. Uniformizar o termo.

### CL-26 — "interface de consulta analítica" (p.64) com "?" · **B**
Explicar melhor ou retirar. **Ver CL-15** — ali ela parece querer o contrário.
Provável raiz: o termo "analítica" está sobrecarregado (ver CL-33).

### CL-27 — tabela consolidada zonas × características × requisitos · **B (grande)**
Substituir/complementar os parágrafos de fechamento de cada zona por uma matriz de
rastreabilidade. Resolve parte do CL-33 e demonstra que nenhum requisito ficou órfão.
**Boa ideia dela.** Decidir se substitui ou complementa a prosa.

### CL-28 — Figura 4.5 "dispensável" · **C**
Sua leitura: pela contundência, ela quer remoção. Três saídas: (a) remover;
(b) redesenhar com as seis Funções convergindo na Silver; (c) fundir com o CL-27.
**Depende da figura**, que falta (`diagrama5_modelo_gold_medal`).

### CL-29 — célula "dado analítico" em C2 × Gold · **C**
Circularidade: o C2 aparece como uma entre seis Funções, mas é a função integradora,
e os produtos da Gold (PPCOT, PITCIC, COC) são produtos de C2. Ligado ao CL-28.

### CL-30 — erros de referência, p.73, 74 e 78 · **NÃO É ERRO**
São os três `\ref{cap:poc}` do capítulo 4. Viraram `??` no PDF apenas porque o build
da qualificação não incluía o capítulo 5. **O fonte está correto — nada a fazer.**
Confirmar isso a ela.

### CL-31 — "O que garante isso?" (4.5.3, hierarquia de C2) · **B**
Nada no modelo descreve *enforcement*; controle de acesso está fora do escopo.
Saída: dizer que a arquitetura **acomoda** o fluxo hierárquico — recebe o que os
batalhões transmitem pelos enlaces táticos — em vez de afirmar que o garante.

### CL-32 — "Como?" (preserva a cadeia de responsabilização) · **B**
O texto diz o que o sistema **não** faz, não o mecanismo. Articular: linhagem
registrada no catálogo, ausência de automação decisória, rastreabilidade auditável.

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

**Resposta dela** — CL-02, CL-17, CL-19.
