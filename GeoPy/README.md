## Orientações GeoPy

Esta documentação foi elaborada com o intuito de facilitar o uso da biblioteca GeoPy nos estudos referentes ao nosso projeto. GeoPy é uma biblioteca python desenvolvida para agrupar diversos serviços web de geocodificação e fontes de dados de terceiros para tornar mais simples a relização de tarefas relacionadas à pesquisa geográfica.

A principal fonte de informação usada para a formação destas orientações foi a [documentação oficial GeoPy](https://geopy.readthedocs.io/en/latest/). 

### Considerações Iniciais

* O GeoPy não oferece nenhum serviço próprio particular. A biblioteca apenas desempenha o papel de prover métodos de implementações de diversas API's geográficas populares em um único pacote de desenvolvimento.
* Diferentes serviços de dados geográficos contidos na biblioteca utilizam diferentes termos de serviço, taxas de limite, pagamento e bases de dados. O Geocoder utilizado deve ser escolhido de acordo com as necessidades e limitações do projeto.

### Instalação e Importação

Para utilizar a biblioteca é necessário fazer sua instalação a partir da execução do seguinte código no terminal da máquina: 

```
pip install geopy
```

Geocoders específicos podem ser importados e utilizados no código com:

```
from geopy.geocoders import [geocoder]
```

Alguns dos Geocoders mais populares e disponibilizados pela biblitoeca são: Nominatim, BaiduV3, Bing, DataBC e GoogleV3. É importante salientar que cada Geocoder tem sua docuemntação, seu método de autenticação e de uso. 

Para fins didáticos, vamos utilizar a API [Nominatim](https://nominatim.org/) na maioria dos exemplos. Os processos de implementação não se alteram drasticamente para cada API, mas as funções características individuais, que não serão abordadas aqui, podem facilmente ser encontradas na documentação GeoPy.

### Funcionalidades

#### Geocodificação

Geocoders são ferramentas que podem encontrar endereços, nomes comerciais, locais de interesse, etc. em um espaço geográfico real e fornecer essa informação em uma geolocalização com latitude e longitude. É possível também realizar a geocodificação inversa, que consiste na conversão de coordenadas geográficas em um endereço válido.

Sempre ao iniciar uma geocoder precisamos nomear a aplicação pelo parâmetro "user_agent".
```
geolocator = Nominatim(user_agent="tutorial_cda") 
```

Com o método ```.geocode```, podemos passar um endereço em forma de string para receber o ponto desejado.

```
universidade1 = geolocator.geocode("UFMG")
```

O método ```.reverse``` executa a geocodificação reversa da ponto geocodificado.

```
universidade2 = geolocator.reverse('-19.8733672, -43.967615129057236') 
````

#### Cálculo de Distância

O GeoPy é capaz de calcular distâncias entre dois pontos geográficos usando a [distância geodésica](https://pt.wikipedia.org/wiki/Geod%C3%A9sica) e a [distância ortodrômica](https://pt.wikipedia.org/wiki/Ortodromia). 

A função ```distance.distance``` permite que esse cálculo seja realizado de forma simples, usando como padrão a distância geodésica.

```
distance.distance(local1, local)
```

_* os locais devem ser especificados em coordenadas geográficas no formato (lat,lon)._

As funções especificas podem ser usadas com o acréscimo do parâmetro especificando o modelo de elipsoide usada:

```
distance.geodesic(local1, local2, ellipsoid=(6377., 6356., 1 / 297.))

distance.great_circle(local1, local2)
```

#### Dados Geográficos 

A biblioteca contém classes de dados geográficos de forma que podemos fazer pesquisas mais significativas acerca de localizações definidas.

A propriedade ```.adress``` retorna o enderço completo da localização de um ponto que geocodificamos.

A propriedade ```.raw``` retorna um dicionário contendo todas informações de latitude e longitude, endereço e etc. de um ponto geocodificado.

A classe ```geopy.point.Point``` permite armazenar os dados de latitude, longitude e altitude referente à localização definida em um objeto Point.


#### Unidades de Conversão 

O módulo de unidade do GeoPy fornece funções utilitárias para realizar conversões de unidades de ângulo e distância.

```
distance.great_circle(local1, local2).miles
```

Podemos converter qualquer unidade para as descritas aqui:

Função | Descrição 
:-------: | :-------: 
geopy.units.arcmin | Converte ângulo para arco minutos
geopy.units.arcsec | Converte ângulo para arco segundo
geopy.units.degrees | Converte ângulos para graus
geopy.units.m | Converte distãncia para metros
geopy.units.km | Converte distância para kilometros

Entre muitas outras.

#### Utilização com Pandas

É possível utilizar a geocodificação de informações em um DataFrame Pandas. Porém deve ser levado em conta que várias solicitações de pesquisa podem atingir a taxa de limite da API. O problema pode ser contornado usando uma função que controla o tempo de espera (min delay seconds) entre um grande número de solicitações.

```
from geopy.extra.rate_limiter import RateLimiter


df = pd.DataFrame({'name': ['paris', 'berlin', 'london']})

geolocator = Nominatim(user_agent="tutorial_cda")

geocode = RateLimiter(geolocator.geocode, min_delay_seconds=1)

df['location'] = df['name'].apply(geocode)

df['point'] = df['location'].apply(lambda loc: tuple(loc.point) if loc else None)
```

Dessa forma, é possível aplicar operações de geocodificação em DataFrames completos de forma facilitada.









