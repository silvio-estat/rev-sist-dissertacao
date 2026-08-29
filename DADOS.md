# Manifesto de dados

Origem, forma de geração e status de cada conjunto de dados do repositório.

**Status possíveis:**

- **evidência congelada** — arquivo como saiu da fonte; não deve ser alterado.
- **derivado (versionado)** — gerado por um notebook/script a partir de evidência;
  mantido no git por ser o estado de registro da pesquisa.
- **merge manual** — montado à mão em planilha; não reproduzível por código.
- **regenerável (fora do git)** — pode ser recriado; mantido só em disco.

> Pendências de reconciliação estão marcadas com ⚠️ ao final.

---

## 01_protocolo/

| Arquivo | Origem | Status |
|---|---|---|
| `palavras_chave_temac.md` | Strings de busca definidas pelo autor, com a contagem de resultados de cada uma por base (consulta de 20/02/2026) | evidência congelada |
| `Projeto de Pesquisa - IA Operacional - vs3.md`, `TEMAC_artigo.md` | Documentos de referência do projeto e da metodologia | — |

## 02_dados_brutos/

| Pasta | Origem | Geração | Status |
|---|---|---|---|
| `ieee_xplore/` (17 `.csv`) | IEEE Xplore — export de cada string de busca | Download direto, 20/02/2026 (nomes `export2026.02.20-*.csv`) | evidência congelada |
| `scopus/` (13 `.csv`) | Scopus — export de cada string | Download direto, 20/02/2026 (nomes `scopus_export_Feb 20-2026_*.csv`) | evidência congelada |
| `wos/` (9 `.txt`) | Web of Science — export "Plain Text / Full Record" | Download direto (`savedrecs*.txt`) | evidência congelada |

## 03_consolidacao/

### SCOPUS_IEEE_WOS/

| Arquivo | Geração | Status |
|---|---|---|
| `base_ieee_consolidada.csv` | `ajustes_IEEE.ipynb` — concatena os 17 CSVs, dedup por `Document Title` + `DOI` | derivado (versionado) |
| `base_scopus_consolidada.csv` / `.xlsx` | `ajustes_SCOPUS.ipynb` — empilha os 13 CSVs, dedup por `Title` + `DOI` | derivado (versionado) |
| `base_wos_consolidada.txt` | `ajustes_WoS.ipynb` — parser por tags, dedup, reescrita em `.txt` compatível com R | derivado (versionado) |
| `base_ieee_adaptada_scopus.csv` | Tentativa de reformatar a IEEE no layout Scopus (o `bibliometrix` não lia IEEE à época) | derivado (versionado) — tentativa registrada |
| `base_consolidada_para_triagem.xlsx` | Base para a etapa de triagem | derivado (versionado) — ⚠️ ver pendência 1 |
| `indexacao_ieee_vs_scopus_wos.csv` | `indexacao_ieee_vs_scopus_wos.ipynb` — cruzamento de indexação entre bases | derivado (versionado) |

### bases_manuais/

| Arquivo | Origem | Status |
|---|---|---|
| `junto_mao.xlsx` | União das bases montada à mão | merge manual — ⚠️ ver pendência 2 |
| `base_completa_juntado_mao.xlsx` | União "completa" montada à mão (md5 diferente do anterior, tamanho quase idêntico) | merge manual — ⚠️ ver pendência 2 |
| `base_conjunta_scopus_wos_analise.xlsx` | Base conjunta Scopus + WoS usada na análise | merge manual |
| `base_consolidada_para_triagem.xlsx` | Cópia trazida da raiz do projeto antigo (md5 diferente da que está em `SCOPUS_IEEE_WOS/`) | merge manual — ⚠️ ver pendência 1 |

### Fontes específicas de C2

| Pasta | Conteúdo | Geração | Status |
|---|---|---|---|
| `IC2I/` | Anais do ICCRTS 2016–fev/2026 | `extracao_metadados_iccrts*.ipynb` + `enriquecimento_*_v4.ipynb` — conversão para markdown e extração de metadados com LLM (Groq / `gpt-oss-120b`); ajustes manuais. `iccrts_para_convert2df.csv` e `metadados_iccrts_v4.xlsx` ainda têm imperfeições nas referências | derivado (versionado) — uso restrito a tabela de metadados |
| `C2COE/` | Documentos NATO C2COE | `Tabela_Metadata_C2COE_OTAN.xlsx` feita à mão; `info_documentos_nato_c2coe.xlsx` via `lista_documentos_c2coe_library.ipynb`; `tabela_metadados_biblioteca_*` via ferramenta de síntese | merge manual / derivado |
| `MOR/` | Military Operations Research | `fontes_MORS.xlsx` = lista baixada do site; `Tabela_Metadata_MOR.xlsx` = 4 artigos escolhidos, metadados montados à parte | merge manual |
| `JORNAL_STRATEGIC_STUDIES/` | `tabela_metadados_JEE.xlsx` — 3 artigos escolhidos após triagem | merge manual |
| `BASES_C2_JUNTAS/` | `bases_c2_juntas.xlsx` — união das tabelas de metadados de C2 | merge manual |

## 04_bibliometria/dados/

| Arquivo | Geração | Status |
|---|---|---|
| `M_scopus.rdata`, `M_wos.rdata`, `M_ieee.rdata` | `analise_bibliometrix.ipynb` — `convert2df()` sobre as bases consolidadas | derivado (versionado) |
| `M_final.rdata` | `mergeDbSources()` das bases (Scopus + WoS para a análise final) | derivado (versionado) |
| `M_iccrts.rdata`, `M_iccrts_bibliometrix.rdata` | Tentativas de levar os metadados do ICCRTS ao formato `bibliometrix` (`tentativa_ajuste_base_iccrts.ipynb`, `convert2df_iccrts.R`) — não concluídas | derivado (versionado) |
| `_rstudio_abandonado/` (`M_*_rstudio.csv`, `dadosbiblio_rstudio.csv`) | Ramo abandonado: script `bibliometrix_Rmd.Rmd` (não copiado para cá) que rodava a conversão no RStudio e exportava CSVs. Substituído pelo fluxo em notebook | **regenerável (fora do git)** |

## 05_resultados/

| Pasta | Conteúdo | Status |
|---|---|---|
| `SCOPUS/analise_vs1/` | Primeira análise da Scopus (com livros) — planilha do Biblioshiny, CSVs de apoio, figuras, relatório | derivado (versionado) |
| `SCOPUS/analise_vs2/` | Segunda análise da Scopus (sem livros) + gráficos padronizados (`graficos_bibliometrix.ipynb`); relatório em várias versões (vale a mais recente) | derivado (versionado) |
| `WoS/analise_vs1/` | Análise única da WoS | derivado (versionado) |
| `REL_FINAL/` | Relatório bibliométrico consolidado (Scopus + WoS), gráficos combinados; versões `vs1`–`vs3` são correções sucessivas | derivado (versionado) |

## 06_triagem/

| Pasta | Conteúdo | Status |
|---|---|---|
| `escolha_artigos_C2/` | Scoring PRISMA (`prisma_scoring.py`), planilha de auditoria, `selecao_artigos_C2*.md` (versões) | derivado / notas |
| `analise_amostra_artigos/` | `ajustes_iniciais.ipynb` sobre a amostra | derivado |
| `artigos_dl_dlh_md/` | `ranking_artigos.xlsx`, `todos_artigos_md.md` — artigos de Data Lake / Lakehouse / Data Mesh | notas |
| `analise_completude_scopus/` | `completude_ieee_scopus.ipynb` + `ext_list_Jul_2026.xlsx` — sombreamento IEEE × Scopus × WoS | derivado (versionado) |

---

## Pendências de reconciliação ⚠️

1. **`base_consolidada_para_triagem.xlsx` em dois lugares com conteúdo diferente:**
   `03_consolidacao/SCOPUS_IEEE_WOS/` (md5 `e2147d7e…`) e
   `03_consolidacao/bases_manuais/` (md5 `e498cc0e…`). Definir qual é a boa e remover
   a outra, ou renomear para deixar claro o que cada uma é.
2. **`junto_mao.xlsx` vs `base_completa_juntado_mao.xlsx`:** tamanhos quase idênticos
   (14 176 349 vs 14 176 391 bytes) mas md5 diferentes. Provavelmente uma é revisão da
   outra — confirmar e manter só uma, ou documentar a diferença.
