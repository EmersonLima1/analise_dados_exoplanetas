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

#### Distribuição de Planetas por Tipo

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/tipos_de_planeta.png)

O gráfico utilizando para essa análise é um gráfico de barras simples, mostrando a distribuição de planetas por tipo. Cada barra representa um tipo específico de planeta (Gigante gasoso, Super Terra, Terrestre ou Tipo Netuno) e sua altura indica a contagem de exoplanetas desse tipo no conjunto de dados.

Analisando os dados do gráfico, pode-se observar as seguintes conclusões sobre a distribuição de planetas por tipo:

- Tipo de planeta mais comum: O tipo de planeta mais comum no conjunto de dados é o Tipo Netuno. Isso sugere que planetas semelhantes a Netuno são frequentemente encontrados em sistemas estelares.

- Distribuição relativamente equilibrada entre Gigante gasoso e Super Terra: Gigante gasoso e Super Terra têm contagens semelhantes, sugerindo uma distribuição relativamente equilibrada entre esses dois tipos de planetas no conjunto de dados.

- Menor quantidade de planetas terrestres: Terrestre é o tipo de planeta menos comum no conjunto de dados, com uma contagem de apenas 168 planetas. Isso sugere que planetas terrestres (semelhantes à Terra) são mais difíceis de detectar ou são menos comuns em sistemas estelares.

- Equilíbrio entre os diferentes tipos de planetas: Embora o Tipo Netuno seja o mais comum, a diferença em relação aos outros tipos de planetas não é muito grande, exceto para planetas terrestres, que são significativamente menos comuns. Isso sugere uma certa diversidade na distribuição dos tipos de planetas descobertos.

Esta análise mostra uma distribuição diversificada dos tipos de planetas descobertos, com o Tipo Netuno sendo o mais comum, seguido de perto por Gigante gasoso e Super Terra. Planetas terrestres são os menos comuns, indicando um possível desafio na detecção ou uma menor presença natural em sistemas estelares.

#### Distribuição de planetas por método de descoberta

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/metodo_descoberta.png)

O gráfico utilizando nessa análise é um gráfico de barras simples, mostrando a distribuição de planetas por método de descoberta. Cada barra representa um método específico de descoberta (Astrometria, Imagem direta, Microlente gravitacional, Trânsito ou Velocidade radial) e sua altura indica a contagem de exoplanetas descobertos por meio daquele método.

Analisando os dados do gráfico, pode-se tirar as seguintes conclusões sobre a distribuição de planetas por método de descoberta:

- Método de descoberta mais comum: O método de Trânsito é, de longe, o mais comum, com uma contagem de mais de 3500 planetas descobertos usando essa técnica. Isso sugere que o método de Trânsito é altamente eficaz para a descoberta de exoplanetas e tem sido amplamente utilizado nos últimos anos.

- Velocidade radial em segundo lugar: O método de Velocidade radial é o segundo mais comum, com quase 1000 planetas descobertos. Embora seja menos comum que o método de Trânsito, ainda é uma técnica significativa na descoberta de exoplanetas.

- Método de Microlente gravitacional: O método de Microlente gravitacional descobriu mais de 100 planetas, o que indica que, embora não seja um método tão comum quanto Trânsito ou Velocidade radial, ainda é uma técnica útil para a descoberta de exoplanetas.

- Imagem direta: O método de Imagem direta descobriu menos de 100 planetas, o que sugere que essa técnica é menos comum na descoberta de exoplanetas. No entanto, pode ser eficaz em casos específicos.

- Astrometria: Astrometria é o método menos comum para a descoberta de exoplanetas. Isso sugere que Astrometria não é uma técnica amplamente utilizada para a descoberta de exoplanetas atualmente.

Esta análise mostra que o método de Trânsito é de longe o método mais eficaz e amplamente utilizado para a descoberta de exoplanetas. Velocidade radial é o segundo método mais comum, enquanto Microlente gravitacional, Imagem direta e Astrometria são usados com menos frequência para a descoberta de exoplanetas.

#### Distribuição da Temperatura da Estrela-mãe dos Exoplanetas

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/temperatura_estrela_mae.png)

Ao analisar o histograma da temperatura da estrela-mãe dos exoplanetas, pode-se observar uma distribuição distinta:

- 0 a 2000 K: A contagem de temperaturas das estrelas-mães nesta faixa é muito baixa, isso sugere que poucas estrelas-mães dos exoplanetas têm temperaturas muito baixas, indicando que a maioria das estrelas-mães não são muito frias.

- 2000 a 4000 K: Assim como a faixa anterior, esta também apresenta uma baixa contagem de temperaturas, isso indica que poucas estrelas-mães possuem temperaturas nessa faixa intermediária mais baixa.

- 4000 a 6000 K: Este é o intervalo de temperatura com a maior concentração de estrelas-mães. As contagens nesta faixa são substanciais, indicando que a maioria das estrelas-mães dos exoplanetas tem temperaturas moderadas, centradas em torno de 5000 K.

- 6000 a 8000 K: As contagens diminuem à medida que as temperaturas aumentam, com pouco mais de 400 ocorrências até faixas menores, indicando uma menor quantidade de estrelas-mães com temperaturas mais altas.

Em geral, o histograma sugere que a maioria das estrelas-mães dos exoplanetas está concentrada na faixa de temperatura entre 4000 K e 6000 K, com poucos casos nas faixas mais extremas.

#### Distribuição do Número de Planetas no Sistema

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/numero_planeta_sistema.png)

Ao analisar o histograma, pode-se observar:

- Uma grande concentração de sistemas com apenas um planeta, com quase 3000 ocorrências. À medida que o número de planetas por sistema aumenta para dois, três, ou quatro, a contagem de sistemas diminui progressivamente, com pouco mais de 1000 ocorrências para sistemas com dois planetas, quase 500 sistemas com três planetas, e menos de 250 sistemas com quatro planetas.

- Nos intervalos subsequentes, que correspondem a sistemas com cinco planetas ou mais, a contagem de sistemas continua diminuindo. Isso sugere que sistemas com um grande número de planetas são muito menos comuns.

Essa distribuição indica que a maioria dos sistemas estelares tende a ter apenas um planeta, sendo cada vez menos comum encontrar sistemas com um número maior de planetas.

#### Relação entre Metalicidade e Presença de Exoplanetas

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/metalicidade_presenca_planeta.png)

Nessa análise foi utilizado um gráfico de barras empilhadas que mostra a relação entre a metalicidade (Fe/H) das estrelas e a proporção de diferentes tipos de exoplanetas que orbitam essas estrelas. As barras estão organizadas por intervalos de metalicidade, indo de (-1.5, -1.0] a (1.0, 1.5].

Os dados do gráfico mostram algumas tendências interessantes:

- Os intervalos de metalicidade mais negativos (-1.5 a -0.5) não têm dados disponíveis sobre a presença de exoplanetas, indicando que a observação pode ser limitada ou esses intervalos podem não ser propícios para a formação de planetas.

- No intervalo de metalicidade de (-0.5, 0.0], há uma distribuição relativamente equilibrada entre os tipos de exoplanetas, com uma leve predominância de exoplanetas tipo Netuno e gigantes gasosos.

- No intervalo de metalicidade de (0.0, 0.5], há uma maior proporção de gigantes gasosos, seguidos por exoplanetas tipo Netuno e superterras. A proporção de planetas terrestres é significativamente menor.

- No intervalo de metalicidade de (0.5, 1.0], há uma alta proporção de gigantes gasosos, sugerindo que as estrelas com metalicidade mais alta são mais propensas a hospedar gigantes gasosos.

- Nos intervalos de metalicidade mais altos (1.0, 1.5], não há dados disponíveis sobre a presença de exoplanetas, semelhante aos intervalos de metalicidade mais baixos.

Em geral, o gráfico sugere uma tendência de que estrelas com maior metalicidade tenham uma maior proporção de gigantes gasosos. Os outros tipos de planetas também aparecem, mas com proporções menores ou mais equilibradas em intervalos de metalicidade mais baixos.

#### Mapa de Calor das Correlações entre as Características dos Exoplanetas

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/correlacoes_caracteristicas.png)

Analisando o heatmap de correlações dos dados dos exoplanetas, podemos observar algumas correlações interessantes (lembre-se correlação não indica causalidade):

- Raio (Jup) <-> Metalicidade (Fe/H): 0.34: Esta correlação positiva indica que exoplanetas com raios maiores tendem a estar em sistemas com maior metalicidade (conteúdo de elementos mais pesados que o hélio). Isso pode sugerir que sistemas com maior metalicidade têm uma maior probabilidade de formar exoplanetas maiores.

- Raio (Jup) <-> Temperatura de equilíbrio planetário: 0.54: Há uma correlação positiva entre o raio do exoplaneta em relação a Júpiter e a temperatura de equilíbrio planetário. Isso sugere que exoplanetas maiores podem ter temperaturas de equilíbrio mais altas, possivelmente devido à maior absorção de energia de suas estrelas hospedeiras.

- Idade (Gyr) <-> Temperatura (K): -0.30: Esta correlação negativa sugere que estrelas mais antigas tendem a ter temperaturas efetivas mais baixas. Isso é esperado, pois estrelas mais jovens geralmente têm temperaturas mais altas devido a processos de fusão nuclear mais intensos, enquanto estrelas mais antigas tendem a esfriar com o tempo.

#### Correlação entre Período Orbital e Distância Orbital

![](https://github.com/EmersonLima1/analise_dados_exoplanetas/blob/main/Gr%C3%A1ficos%20das%20an%C3%A1lises/correlacao_periodo_orbital_distancia_orbital.png)

Para demonstrar esta correlação foi usado um scatterplot e nele é mostrado a relação entre o semieixo maior (AU) e o período orbital (dias) com uma correlação positiva muito forte de 0.80 indica uma tendência clara entre essas duas variáveis. Analisando esse gráfico, pode-se observar:

- Correlação positiva muito forte: A correlação positiva de 0.80 indica uma relação direta e forte entre o semieixo maior e o período orbital. Ou seja, conforme o semieixo maior aumenta, o período orbital também tende a aumentar de forma significativa.

- Distribuição dos pontos: No scatterplot, você pode observar que os pontos tendem a se alinhar em uma linha diagonal ascendendo do canto inferior esquerdo (0, 0) para o canto superior direito. Isso indica que exoplanetas com órbitas mais amplas (semieixos maiores) tendem a ter períodos orbitais mais longos.

- Conformidade com a Lei de Kepler: Essa relação entre o semieixo maior e o período orbital está de acordo com a terceira lei de Kepler, que estabelece que o quadrado do período orbital é proporcional ao cubo do semieixo maior da órbita. Isso significa que, à medida que a órbita de um exoplaneta se estende, o tempo necessário para completar uma órbita ao redor de sua estrela hospedeira também aumenta.

Em resumo, o scatterplot mostra uma relação clara entre o semieixo maior e o período orbital dos exoplanetas, confirmando a teoria de que exoplanetas em órbitas mais amplas levam mais tempo para completar uma órbita.
