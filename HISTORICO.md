# Histórico da pesquisa

Narrativa de como esta revisão sistemática foi conduzida, do protocolo aos resultados.
Consolida o relato de trabalho original (preservado em `_local/historico_original.md`),
a linha do tempo do versionamento e o levantamento de fontes de Comando e Controle.

---

## 1. Linha do tempo

| Período | Etapa |
|---|---|
| **fev/2026** | Definição das strings de busca; extração das três bases (IEEE, Scopus, WoS) em 20/02; primeira consolidação e primeiros objetos `M_*.rdata` |
| **fev–mar/2026** | Tentativa de rodar a análise via RStudio (ramo abandonado — ver §4); migração para o fluxo Python (`uv`) + kernel R no Jupyter |
| **mar/2026** | Análise no Biblioshiny; relatórios por base (Scopus com e sem livros; WoS); gráficos padronizados; primeira rodada de ajustes pedidos pela revisão |
| **mar/2026** | Extração de metadados dos anais do ICCRTS (IC2I) com apoio de LLM; tabelas de metadados de C2COE, MOR e Journal of Strategic Studies |
| **mar–abr/2026** | Revisão dos Estágios 1 e 2 do TEMAC; triagem e seleção dos artigos de C2 (scoring PRISMA); ranking dos artigos de DL/DLH |
| **ago/2026** | Análise de completude e sombreamento entre IEEE, WoS e Scopus; incorporação das considerações da banca de qualificação (profs. Andrei e Cláudia) |

---

## 2. Protocolo (Estágio 1 do TEMAC)

1. **Strings de busca** definidas por base — texto integral em
   `01_protocolo/palavras_chave_temac.md` (Apêndice A da dissertação). Eixos
   combinados: arquitetura de dados (`data lake` / `data lakehouse` / `data
   architecture`) × natureza dos dados (`unstructured` / `heterogeneous` / `big
   data`) × decisão (`decision making` / `decision support`) × domínio militar
   (`military` / `defense` / `command and control` / `battlefield`).
2. **Campo espaço-tempo:** publicações a partir de **2016**.
3. **Bases:** IEEE Xplore, Scopus, Web of Science.
4. Exports salvos **como baixados** em `02_dados_brutos/{ieee_xplore,scopus,wos}/`.

---

## 3. Consolidação (Estágio 2)

Um notebook por base, em `03_consolidacao/SCOPUS_IEEE_WOS/`:

| Base | Notebook | Formato | Desduplicação |
|---|---|---|---|
| IEEE Xplore | `ajustes_IEEE.ipynb` | `.csv` | chaves `Document Title` + `DOI` |
| Scopus | `ajustes_SCOPUS.ipynb` | `.csv` | colunas `Title` + `DOI` |
| WoS | `ajustes_WoS.ipynb` | `.txt` (tags) | parser próprio por tags (`TI`, `DI`, `UT`), reescrito em `.txt` compatível com R |

Saídas: `base_ieee_consolidada.csv`, `base_scopus_consolidada.csv`,
`base_wos_consolidada.txt`. `base_ieee_adaptada_scopus.csv` foi uma tentativa de
adaptar a IEEE ao formato Scopus (o `bibliometrix` não lia IEEE diretamente à época).
Merges feitos manualmente estão em `03_consolidacao/bases_manuais/` — ver `DADOS.md`.

---

## 4. Decisões metodológicas

- **IEEE Xplore descartada da análise bibliométrica.** Ao concatenar as bases havia
  perda de dados (o campo `CR`, referências citadas, ficava 100% ausente). A IEEE não
  publica as referências de cada artigo (só a contagem), e Scopus e WoS já a indexam.
  Decidiu-se manter **apenas Scopus e WoS** para os temas de tecnologia. A IEEE
  permanece no repositório como evidência e é usada nas análises de completude/
  sombreamento entre bases (`06_triagem/analise_completude_scopus/`).
- **Recorte temporal:** toda a análise no Biblioshiny considerou trabalhos de **2016
  em diante**.
- **Scopus sem livros:** a primeira análise da Scopus incluiu livros, mas alguns eram
  citados de forma desproporcional (obras com muitos autores), o que mascarava autores
  de impacto. A segunda análise (`analise_vs2`) removeu os livros — eram poucos.
- **Gráficos padronizados:** parte das figuras foi refeita fora do Biblioshiny
  (`05_resultados/.../graficos_bibliometrix.ipynb`) para uniformizar cores; algumas
  saíram direto do Biblioshiny por ele não expor os dados subjacentes.

---

## 5. Fontes específicas de Comando e Controle

Além das três bases de indexação, um levantamento à parte identificou as fontes de
maior impacto em C2 no mundo. Tratamento dado a cada uma (em `03_consolidacao/`):

| Fonte | Situação |
|---|---|
| **NATO C2COE** | Todos os documentos dos dois *annals* baixados; tabela de metadados feita à mão (`C2COE/Tabela_Metadata_C2COE_OTAN.xlsx`). Documentos dispersos da biblioteca do site: tabela de metadados montada com apoio de ferramenta de síntese |
| **ICCRTS / IC2I** | Anais de 2016 a fev/2026 disponibilizados por colaboradores; convertidos para markdown e submetidos a extração de metadados com LLM (Groq / `gpt-oss-120b`) — ver `IC2I/`. O resultado ainda tem imperfeições nas referências; uso restrito a tabela de metadados |
| **Military Operations Research (MOR)** | Lista de trabalhos até 2016 (`MOR/fontes_MORS.xlsx`); triagem por título; 4 artigos selecionados com metadados montados à parte |
| **Journal of Strategic Studies** | Busca por `command and control` / `C2` / `C4ISR` (2016–2026), 145 trabalhos; triagem por título e resumo; 3 artigos selecionados |
| **NATO STO** | Fonte fechada (parceiros OTAN) — sem acesso |
| **Journal of Information Warfare** | Sem acesso aos documentos |
| **IEEE Trans. SMC; Systems Engineering (Wiley); JAMS** | Já indexados por Scopus/WoS |
| **Contemporary Security Policy** | Busca por `command and control` (2016–2026), 41 trabalhos; nenhum com relação à dissertação após leitura de título e resumo |

O relatório completo do levantamento está em
`_local/Fontes de Pesquisa em Comando e Controle.md`.

---

## 6. Triagem e seleção (Estágio 3)

Em `06_triagem/`: scoring PRISMA dos artigos de C2 (`escolha_artigos_C2/`,
`prisma_scoring.py`), análise da amostra de artigos, ranking dos artigos de
DL/DLH/MD (`artigos_dl_dlh_md/`) e a análise de completude / sombreamento entre bases
(`analise_completude_scopus/`). As considerações da banca de qualificação e os ajustes
de texto solicitados estão em `07_revisoes_banca/`.
