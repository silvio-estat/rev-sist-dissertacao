# CONSIDERAÇÕES DO SEMINÁRIO I DO PROFESSOR ANDREI

Seminário I, 18/11/2026. Fonte: `seminario_I/transcricao/video_falantes_turnos.md`
(os tempos entre colchetes remetem à transcrição).

## PEDIDOS DE ALTERAÇÃO NO TEXTO / PARA O SEMINÁRIO II

### 1. Materializar a governança, a linhagem e o catálogo [00:41:00 – 00:41:39; 00:45:33 – 00:46:00]
- Lembrou que o Silvio citou a ligação do dado bruto ao dado final, mas **não chegou a falar da camada Gold**.
- Para o **Seminário II**, pediu para trazer a governança de forma **materializada**: linhagem, catálogo de dados e a demonstração de que há **domínio sobre o dado em todas as fases**, da camada crua (*Landing*) até a final (*Gold*).
- Ligação com o item AN-12 da qualificação (governança e linhagem na PoC).

### 2. Demonstrar na PoC, e não só afirmar [00:44:01 – 00:44:21]
- Diante da afirmação de que é possível "confirmar os dados um por um" até o arquivo de origem, perguntou se isso já foi testado ou se vai ser feito na PoC.
- Na prática, a rastreabilidade (Gold → Silver → Bronze → *Landing*, por *hash*) precisa aparecer **demonstrada** na prova de conceito.

### 3. Mostrar que a arquitetura se estende a outros contextos [00:46:25 – 00:48:14]
- Pediu para **ajustar a resposta** dada à professora Maria Cláudia: o trabalho parece resolver só um problema do Exército.
- Sugeriu que, **em algum ponto do texto**, o Silvio mostre que a arquitetura, ou pelo menos parte dela, é **extensível** a outros usos: **Marinha, Aeronáutica e até o Governo Federal**.
- O motivo: dar mais **volume e importância** ao trabalho.
- Lugar sugerido (decisão do Silvio): discussão ou conclusão, ou trabalhos futuros.

## SUGESTÃO PARALELA (fora da dissertação)
- **Publicação** [00:46:25]: escrever um artigo sobre a **parte técnica de transformação** dos dados heterogêneos até a camada prata ou ouro, com o ferramental usado (LLM, Docling, faster-whisper).

## PONTOS QUE ELE CONSIDEROU ATENDIDOS
- Contextualização numa situação real (Operação Perseu 2024 como moldura), que deixou mais claro como o sistema seria usado.
- Integração de dados heterogêneos (JSON, PDF, foto, áudio), que justifica a escolha de uma arquitetura de *Data Lake*.
- Especificação da camada *Landing*: "faz mais sentido agora para quem vai ler".
- Disse que a camada Gold é o dado pronto para relatório ou *dashboard* e que o trabalho principal está no processamento entre as camadas.
