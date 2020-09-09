# Trabalhando com tweets coletados a partir do Twitter Scraper
## Os tweets foram coletados a partir do seguinte comando no ambiente virtual:
## twitterscraper covid -l 100000 -bd 2020-07-14 -ed 2020-07-15 --lang pt -o covid100k.json
## O arquivo foi renomeado para "covid30k.json", tendo em vista que foram coletados apenas 30.000 tweets.

# Tratamentos.ipynb:
### Trata o arquivo, seleciona colunas úteis e transfere os tweets para um arquivo csv.
# Análises.ipynb:
### Identifica a frequência de tweets por usuário e outliers dentro desse parâmeto.
# Palavras chave.ipynb
### Identifica as palavras mais frequentes e suas frequências, bem como a frequência de palavras desejadas.