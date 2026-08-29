# rev-sist-dissertacao

Revisão sistemática da literatura conduzida pela **Metodologia TEMAC** (Teoria do
Enfoque Meta-Analítico Consolidado) para a dissertação de mestrado **ARQ_TEMAC**.

**Tema:** arquiteturas de dados **Data Lake / Data Lakehouse** e sua aplicação ao
domínio de **Comando e Controle (C2)** / planejamento militar.

Este repositório é o **registro de pesquisa**: guarda as strings de busca, os arquivos
brutos exportados das bases, o processo de consolidação, a análise bibliométrica e os
resultados — no estado em que foram produzidos. Para a linha do tempo e as decisões
metodológicas, ver [`HISTORICO.md`](HISTORICO.md); para a origem de cada arquivo de
dados, ver [`DADOS.md`](DADOS.md).

---

## Ambiente (híbrido Python + R)

A engenharia de dados é feita em Python; a análise bibliométrica, em R (`bibliometrix`
/ Biblioshiny).

| Ferramenta | Uso |
|---|---|
| Python (gestão com [`uv`](https://github.com/astral-sh/uv)) | Leitura, limpeza, desduplicação e parsing dos exports brutos (`pandas`, parsers próprios) |
| R + `bibliometrix` (kernel Jupyter) | Mapeamento científico, estatísticas e grafos a partir da base consolidada |

### Reprodução

Pré-requisitos: `uv` instalado e R no sistema (`sudo apt install r-base r-base-dev`).

```bash
uv sync                                   # dependências Python
uv run Rscript config_R/setup_r.R         # kernel R + pacotes (demora; pode exigir libs do SO)
```

- `03_consolidacao/` — notebooks `ajustes_*.ipynb` regeneram as bases consolidadas.
- `04_bibliometria/analise_bibliometrix.ipynb` — selecionar o **kernel R** e iniciar o
  Biblioshiny. Se o kernel não aparecer: `uv run jupyter notebook --no-browser`.

> **Nota:** vários notebooks têm caminhos de arquivo absolutos embutidos, próprios da
> máquina onde a pesquisa foi feita. Estão preservados como **registro** e podem
> exigir ajuste de caminho para reexecução.

---

## Estrutura

| Pasta | Conteúdo |
|---|---|
| `01_protocolo/` | Protocolo da revisão: strings de busca por base (`palavras_chave_temac.md`), projeto de pesquisa, referência da metodologia TEMAC |
| `02_dados_brutos/` | Exports **como baixados** das bases — `ieee_xplore/`, `scopus/`, `wos/` (evidência congelada) |
| `03_consolidacao/` | Notebooks e parsers de concatenação/desduplicação + bases consolidadas. Subpastas por fonte: `SCOPUS_IEEE_WOS/`, `IC2I/`, `C2COE/`, `MOR/`, `JORNAL_STRATEGIC_STUDIES/`, `BASES_C2_JUNTAS/`. `bases_manuais/` guarda os merges feitos à mão |
| `04_bibliometria/` | Análise com `bibliometrix`, scripts R e `dados/` com os objetos `M_*.rdata` que alimentam o Biblioshiny |
| `05_resultados/` | Saídas do Biblioshiny por base (`SCOPUS/`, `WoS/`), gráficos padronizados e relatórios bibliométricos (`REL_FINAL/`) |
| `06_triagem/` | Seleção dos artigos de C2 (scoring PRISMA), análise da amostra, ranking dos artigos de DL/DLH e análise de completude/sombreamento entre bases |
| `07_revisoes_banca/` | Considerações da banca de qualificação e ajustes de texto solicitados |
| `assets/estilo_markdown/` | CSS para exportação dos relatórios |
| `config_R/` | Script de setup do ambiente R |

---

## Bases consultadas

- **IEEE Xplore**, **Scopus** e **Web of Science** — buscas com as strings do
  `01_protocolo/`, exportadas em 20/02/2026. A análise bibliométrica final considerou
  **Scopus + WoS** (a partir de 2016); a IEEE foi descartada da análise por não
  fornecer as referências citadas (`CR`) e por já ser indexada pelas outras duas.
- **Fontes específicas de C2** identificadas por levantamento à parte (NATO C2COE,
  ICCRTS, Military Operations Research, Journal of Strategic Studies) — tratadas em
  `03_consolidacao/` como tabelas de metadados.

Detalhes e justificativas em [`HISTORICO.md`](HISTORICO.md).
