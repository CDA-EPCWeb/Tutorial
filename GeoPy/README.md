## Orientações GeoPy

Esta documentação foi elaborada com o intuito de facilitar o uso da biblioteca GeoPy estudos referentes ao nosso projeto. GeoPy é uma biblioteca python desenvolvida para agrupar diversos serviços web de geocodificação terceiros e outras fontes de dados para tornar simples as tarefas relacionadas à pesquisa geográfica.

A principal fonte de informação usada para a formação destas orientações foi a [documentação oficial GeoPy](https://geopy.readthedocs.io/en/latest/). 

### Considerações Iniciais

* O GeoPy não oferece nenhum serviço particular. A biblioteca apenas desempenha o papel de prover métodos de implementações de diversas API's geográficas poulares em um único pacote de desenvolvimento.
* Diferentes serviços de dados geográficos contidos na biblioteca utilizam diferentes termos de serviço, taxas de limite, pagamento e bases de dados. O Geocoder utilizado deve ser escolhido de acordo com as necessidades e limitações do projeto.


### Instalação e Importação

Para utilizar a biblioteca é necessário fazer sua instalação a partir da execução do seguinte código no terminal da máquina: 

```
pip install geopy
```

Geocoders específicos podem ser importados e utilizados no código com a execução do código

```
from geopy.geocoders import [geocoder]
```

Alguns dos Geocoders mais populares e disponibilizados pela biblitoeca são: Nominatim, BaiduV3, Bing, DataBC e GoogleV3. É importante salientar que cada Geocoder tem sua docuemntação, seu método de Autenticação e de uso. 

Para fins didáticos, vamos utilizar a API [Nominatim](https://nominatim.org/). Os processos de implementação não alteram drsticament epara cada API, mas as funções características individuais, que não serão abordadas aqui, podem facilmente ser encontradas na documentação GeoPy.

### Funcionalidades


#### Geocodificação

#### Cálculo de Distância

#### Dados Geográficos 

#### Unidades de Conversão 

#### Adaptadores de solicitação de conexão

