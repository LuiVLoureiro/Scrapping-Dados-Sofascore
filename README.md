# Scrapping-Dados-Sofascore

Este projeto é uma aplicação Python que utiliza as bibliotecas Selenium e Beautiful Soup para extrair estatísticas do site Sofascore. A principal funcionalidade é coletar dados das 10 últimas partidas de cada jogador de cada time de uma liga especificada pelo usuário.

![Fluxograma](https://github.com/LuiVLoureiro/Scrapping-Dados-Sofascore/assets/103609685/15b0d6dd-115e-4777-9fc6-d3a37ed3e981)

# Resumo para Recrutadores
### Objetivo: Criar uma aplicação Python para coletar estatísticas de jogadores e times de futebol do Sofascore.
### Tecnologias Utilizadas: Selenium, Beautiful Soup, Python.
### Funcionalidades:
Coleta de dados de jogadores de futebol, incluindo minutos jogados, chutes no gol, chutes fora do gol, chutes bloqueados e passes.
Coleta de dados de times de futebol.
Flexibilidade para escolher a liga de interesse.
Tratamento de erros e armazenamento de dados em arquivos separados.
### Fluxo de Trabalho:
O usuário insere a URL da liga desejada.
A aplicação raspa os dados dos times, jogadores e suas estatísticas das partidas.
Os dados são armazenados em arquivos separados.

# Especificações do Código
A seguir, estão as principais partes do código:

### Configurações Iniciais
# Configurações Iniciais ChromeDriver
servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service=servico)

\```python
# Caminho para a pasta onde você deseja salvar os dados
pasta_base = 'Dados'
if not os.path.exists(pasta_base):
    os.makedirs(pasta_base)
\```

