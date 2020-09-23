# Análise dos dados de mobilidade e índices de isolamento

[Base de dados de mobilidade do Google para o Brasil](https://www.google.com/covid19/mobility/index.html?hl=pt-BR)

[Documentação](https://www.google.com/covid19/mobility/data_documentation.html?hl=pt-BR)

--------

Se você publicar resultados com base neste conjunto de dados, inclua a seguinte referência:

Google LLC "Google COVID-19 Community Mobility Reports". https://www.google.com/covid19/mobility/ Accessed: 'data de acesso'.

-----

- country_region_code: código do país
- country_region: nome do país
- sub_region_1: UF ou estado
- sub_region_2: município
- metro_area:
- iso_3166_2_code: código para os nomes das principais subdivisões do país, no caso do Brasil, estados.Ex: BR-MG(Minas Gerais)
- census_fips_code:código exclusivo para os Estados Unidos e certas areas associadas. Codifica estados, counties e equivalentes e algumas areas marítimas
- date: data (no formato aaaa-mm-dd)
- retail_and_recreation_percent_change_from_baseline: mudança - percentual de mobilidade em varejo e lazer
- grocery_and_pharmacy_percent_change_from_baseline: mudança percentual de mobilidade em mercados e farmácias
- parks_percent_change_from_baseline: mudança percentual de mobilidade em parques
- transit_stations_percent_change_from_baseline: mudança percentual de mobilidade em estações de transporte público
- workplaces_percent_change_from_baseline: mudança percentual de mobilidade em locais de trabalho
- residential_percent_change_from_baseline: mudança percentual de mobilidade em áreas residenciais

As categorias de locais dessas variáveis estão detalhadas na próxima seção.



## Descrição dos dados

Os dados disponíveis são indicadores relativos de mobilidade, e não números absolutos. Eles mostram como a quantidade de visitas e o tempo de permanência em diferentes locais estão mudando em cada região geográfica, em comparação com um valor base. As mudanças de cada dia são comparadas com um valor base correspondente ao mesmo dia da semana, que consiste na mediana do dia da semana correspondente entre 3 de janeiro e 6 de fevereiro de 2020 (intervalo de 5 semanas). Essas alterações são calculadas com o mesmo tipo de dados, agregados e anônimos, que é utilizado para mostrar os horários de pico do Google Maps. As categorias de locais incluídas foram escolhidas por serem úteis para as ações de distanciamento social e para o acesso a serviços essenciais.


### Categorias de locais:

#### Mercados e farmácias
Tendências de mobilidade de lugares como mercados, armazéns de alimentos, feiras, lojas especializadas em alimentos, drogarias e farmácias.

#### Parques
Tendências de mobilidade de lugares como parques locais e nacionais, praias públicas, marinas, parques para cães, praças e jardins públicos.

#### Estações de transporte público
Tendências de mobilidade de lugares como terminais de transporte público, tipo estações de metrô, ônibus e trem.

#### Varejo e lazer
Tendências de mobilidade de lugares como restaurantes, cafés, shopping centers, parques temáticos, museus, bibliotecas e cinemas.

#### Residencial
Tendências de mobilidade de áreas residenciais.

#### Locais de trabalho
Tendências de mobilidade de locais de trabalho.

### Algumas limitações

A precisão da localização e a identificação dos locais categorizados variam entre as regiões. Portanto, o uso destes dados para comparar alterações entre países ou entre regiões com características diferentes (por exemplo, áreas rurais e urbanas) não é recomendado. O conjunto de dados não inclui regiões ou categorias que não tem dados suficientes para serem estatisticamente relevantes.
