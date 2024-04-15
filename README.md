# Análise de Dados - Exoplanetas

<div align="justify">

### Introdução e Contextualização

A busca por exoplanetas, planetas que orbitam estrelas além do nosso sistema solar, tem sido uma das áreas mais fascinantes e dinâmicas da astronomia moderna. Desde a primeira detecção confirmada de um exoplaneta em 1992, os avanços tecnológicos e as melhorias nas técnicas de observação têm levado a uma explosão na descoberta desses mundos distantes. Essa busca não apenas amplia nossa compreensão do universo, mas também nos ajuda a explorar questões fundamentais sobre a origem e a natureza da vida no cosmos.

O conjunto de dados que explorado nesse projeto reúne informações sobre mais de 4800 exoplanetas descobertos até o momento. Cada entrada contém uma variedade de parâmetros, desde características físicas dos planetas até detalhes sobre suas estrelas hospedeiras e métodos de descoberta. Esses dados representam uma compilação abrangente do nosso conhecimento atual sobre exoplanetas e proporcionam uma base sólida para análises detalhadas e investigações científicas.

### Objetivos do projeto

- <strong>Entender a Diversidade dos Exoplanetas:</strong> Investigar a distribuição dos diferentes tipos de exoplanetas com base em suas características físicas, como massa, raio, temperatura e composição. Isso nos permitirá compreender melhor a diversidade e a complexidade dos sistemas planetários fora do nosso sistema solar.

- <strong>Identificar Padrões e Tendências:</strong> Utilizar técnicas de análise exploratória de dados para identificar padrões e tendências nos dados, como correlações entre diferentes variáveis, distribuições espaciais de exoplanetas e evolução temporal das descobertas.

### Obtenção dos dados

Os dados foram obtidos de duas fontes principais:

- <strong>Open Exoplanet Catalogue (OEC):</strong> O conjunto inicial de dados foi coletado do site Open Exoplanet Catalogue (OEC) em https://www.openexoplanetcatalogue.com/systems/. O OEC é uma fonte confiável que fornece uma extensa lista de exoplanetas confirmados, juntamente com informações detalhadas sobre suas características físicas, estrelas hospedeiras e métodos de descoberta. No entanto, vale ressaltar que o conjunto de dados obtido do OEC contém informações sobre uma parte dos exoplanetas confirmados, não representando a totalidade de exoplanetas conhecidos até o momento.
  
- <strong>NASA Exoplanet Archive e Web Scraping com Selenium:</strong> Para complementar os dados do OEC e adicionar a coluna "Tipo de Planeta", foi necessário realizar uma busca individual para cada exoplaneta na NASA Exoplanet Archive (https://exoplanets.nasa.gov/discovery/exoplanet-catalog/). Utilizando a biblioteca Selenium com Python, foi possível automatizar esse processo de pesquisa, obtendo assim informações sobre o tipo de planeta associado a cada exoplaneta. Essa abordagem permitiu a inclusão de informações adicionais para os exoplanetas presentes no conjunto de dados, aumentando assim a sua completude e utilidade para análise.

Dessa forma, mesmo que o conjunto de dados contenha informações sobre uma parcela dos exoplanetas confirmados, os dados coletados e agregados permitem uma análise abrangente e representativa dos exoplanetas conhecidos até o momento.

### Limpeza e Pré-processamento de Dados

Durante a fase de limpeza e pré-processamento de dados, várias etapas foram realizadas para garantir a qualidade e a consistência dos dados antes da análise:

- <strong>Remoção de Valores Ausentes na Coluna "Tipo de Planeta":</strong> Devido à importância crítica da coluna "Tipo de Planeta" para a análise que será realizada, as linhas com valores ausentes nessa coluna foram removidas do conjunto de dados. Isso garante que tenhamos informações sobre o tipo de cada exoplaneta, um aspecto fundamental para muitas das análises planejadas.
- <strong>Pré-processamento de Colunas Numéricas:</strong> Várias colunas numéricas tinham caracteres indesejados e inconsistências que precisavam ser corrigidas. Para isso, as seguintes etapas foram realizadas para cada coluna que necessitava de pré-processamento:
    - Remoção de caracteres indesejados, como sinais de mais (+), menos (-), ou ±, para manter apenas o primeiro número presente na coluna.
    - Remoção do caractere "<" para manter apenas o valor numérico subsequente, quando aplicável.
    - Remoção do caractere ">" para manter apenas o valor numérico subsequente, quando aplicável.
    - Remoção do caractere "(" para manter apenas o valor numérico subsequente, quando aplicável.
É importante destacar que, mesmo com valores ausentes em certas colunas numéricas, optou-se por manter essas linhas nos dados. Essa decisão foi tomada para garantir a integridade do conjunto de dados, evitando a perda de informações relevantes em outras variáveis que podem ser úteis para a análise. No entanto, a ausência de valores na coluna "Tipo de Planeta" foi tratada de forma diferente, devido à sua importância crítica para a análise planejada.

O resultado dessas etapas é um conjunto de dados mais limpo, consistente e adequado para análise posterior. Isso nos permite explorar os dados com confiança e extrair insights significativos sobre os exoplanetas e seus sistemas hospedeiros.

### Exploração e visualização dos dados

Durante a etapa de exploração e visualização de dados, foram realizadas diversas análises para compreender melhor as características do conjunto de dados de exoplanetas e identificar padrões ou insights valiosos. Tais análises foram:

#### Distribuição dos Tipos de Planetas por Ano de Descoberta

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/tipo_planeta_ano_descoberta.png)

O gráfico utilizado para essa análise é um gráfico de barras empilhadas, que mostra a distribuição dos diferentes tipos de planetas descobertos ao longo dos anos. Cada barra no gráfico representa um ano específico de descoberta e é dividida em segmentos, cada um representando um tipo específico de planeta (Gigante gasoso, Super Terra, Terrestre e Tipo Netuno). A altura total de cada barra corresponde ao número total de exoplanetas descobertos naquele ano.

Ao analisar esses dados, pode-se fazer algumas observações sobre a distribuição dos exoplanetas por ano e por tipo de planeta:

- Crescimento ao longo do tempo: Há uma tendência geral de aumento no número total de exoplanetas descobertos a cada ano, especialmente a partir de 2014. Isso sugere um progresso significativo na capacidade de descoberta de exoplanetas.

- Predominância de tipos de planetas: Os Gigantes gasosos foram a categoria de planetas mais frequentemente descoberta até cerca de 2013. No entanto, a partir de 2014, há uma mudança significativa com um aumento notável no número de descobertas de Super Terras e planetas do tipo Netuno.

- Variação na descoberta de planetas terrestres: O número de planetas terrestres descobertos por ano é relativamente baixo em comparação com outros tipos de planetas, o que pode ser devido à dificuldade de detectar planetas menores e rochosos em comparação com os maiores planetas gasosos.

- Maior diversidade a partir de 2014: Desde 2014, há uma maior diversidade nos tipos de planetas descobertos a cada ano, com mais descobertas de Super Terras, planetas terrestres e planetas do tipo Netuno em comparação com os anos anteriores.

- Os anos com maior diversidade: Os anos mais recentes (como 2021 e 2022) mostram uma distribuição mais equilibrada entre os diferentes tipos de planetas, com números significativos de Gigantes gasosos, Super Terras, planetas terrestres e planetas do tipo Netuno descobertos.

Essa interpretação sugere uma evolução nas técnicas e capacidades de descoberta de exoplanetas ao longo dos anos, permitindo uma melhor exploração e compreensão da diversidade dos exoplanetas em nossa galáxia.

#### Distribuição dos Métodos de Descoberta por Ano de Descoberta

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/metodo_ano_descoberta.png)

O gráfico utilizado para essa análise é um gráfico de barras empilhadas, que mostra a distribuição dos métodos de descoberta por ano de descoberta. Cada barra representa um ano específico, e cada segmento dentro da barra representa um método de descoberta diferente (Astrometria, Imagem direta, Microlente gravitacional, Trânsito ou Velocidade radial). A altura total da barra corresponde ao número total de exoplanetas descobertos naquele ano.

Analisando o gráfico, é possível observar:

- Método de descoberta predominante: O método de descoberta por Trânsito é o mais utilizado em quase todos os anos, especialmente a partir de 2014. Isso sugere que essa técnica é altamente eficaz para a descoberta de exoplanetas e se tornou a principal abordagem ao longo do tempo.

- Aumento na descoberta de exoplanetas a partir de 2014: A partir de 2014, houve um aumento significativo no número total de exoplanetas descobertos. Isso é principalmente devido ao método de Trânsito, que se tornou a técnica dominante para a descoberta de exoplanetas nesses anos.

- Outros métodos de descoberta: Métodos alternativos como Imagem direta, Microlente gravitacional e Astrometria são usados com menos frequência em comparação com Trânsito e Velocidade radial. No entanto, eles contribuem para a descoberta de exoplanetas em alguns anos.

- Método de Velocidade radial: O método de Velocidade radial é utilizado em vários anos, especialmente em anos anteriores a 2014. Embora seu uso seja menor em anos mais recentes, ele continua a ser um método importante para a descoberta de exoplanetas.

- Mudança nos métodos ao longo do tempo: Observa-se uma clara mudança nos métodos de descoberta ao longo do tempo. Antes de 2014, Velocidade radial era um método bastante comum, enquanto depois de 2014, Trânsito se tornou a técnica dominante, sendo responsável pela maior parte das descobertas.

Essa análise mostra uma mudança clara nos métodos de descoberta de exoplanetas ao longo do tempo, com Trânsito se tornando a técnica dominante a partir de 2014. Velocidade radial também foi amplamente utilizado em anos anteriores, enquanto métodos alternativos como Imagem direta e Microlente gravitacional têm menor impacto geral, mas ainda contribuem para as descobertas em certos anos.

#### Relação entre Método de Descoberta e Tipo de Planeta

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/metodo_descoberta_tipo_planeta.png)

O gráfico utilizado para essa análise é um heatmap ou mapa de calor, que mostra a relação entre o método de descoberta e o tipo de planeta descoberto. Cada célula no gráfico representa a quantidade de exoplanetas descobertos usando um determinado método de descoberta (Astrometria, Imagem direta, Microlente gravitacional, Trânsito ou Velocidade radial) para um determinado tipo de planeta (Gigante gasoso, Super Terra, Terrestre ou Tipo Netuno).

Analisando o heatmap, pode-se observar:

- Método de descoberta mais comum: O método de Trânsito é o mais utilizado para descobrir exoplanetas em diferentes categorias, especialmente para planetas do tipo Netuno e Super Terras. O método de Trânsito tem uma forte presença em todas as categorias de planetas, indicando sua eficiência na descoberta de vários tipos de exoplanetas.

- Velocidade radial para gigantes gasosos: O método de Velocidade radial também é comumente usado, principalmente para descobrir Gigantes gasosos. Isso sugere que este método é particularmente eficaz para detectar grandes planetas gasosos em sistemas estelares.

- Métodos alternativos: Outros métodos de descoberta, como Astrometria, Imagem direta e Microlente gravitacional, são usados em menor escala em comparação com Trânsito e Velocidade radial. Esses métodos parecem ser eficazes para descobrir planetas específicos, mas não são amplamente utilizados.

Essa análise destaca que método de Trânsito é o mais utilizado para descobrir exoplanetas em diversas categorias, enquanto a Velocidade radial é especialmente eficaz para detectar Gigantes gasosos. Outros métodos têm suas próprias especializações, mas são usados em menor escala.

#### 
