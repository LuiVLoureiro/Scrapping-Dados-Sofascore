# Scrapping-Dados-Sofascore

Este projeto é uma aplicação Python que utiliza as bibliotecas Selenium e Beautiful Soup para extrair estatísticas do site Sofascore. A principal funcionalidade é coletar dados das 10 últimas partidas de cada jogador de cada time de uma liga especificada pelo usuário.

![Fluxograma](https://github.com/LuiVLoureiro/Scrapping-Dados-Sofascore/assets/103609685/15b0d6dd-115e-4777-9fc6-d3a37ed3e981)

# Resumo
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
### Configurações Iniciais ChromeDriver
servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service=servico)

```python
# Configurações Iniciais ChromeDriver
servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service=servico)

# Caminho para a pasta onde você deseja salvar os dados
pasta_base = 'Dados'
if not os.path.exists(pasta_base):
    os.makedirs(pasta_base)
```

### Coleta de Dados dos Times

```python
# Coleta de dados dos times
elementos_href = soup.find_all('a', href=lambda href: href and '/team/football/' in href)
links_times = set()

for elemento in elementos_href:
    links_times.add(elemento['href'])
```

### Coleta de Dados dos Jogadores
```python
# Coleta de dados dos jogadores
elementos_jogadores = soup.find_all('a', href=lambda href: href and '/player/' in href)
nomes_jogadores = []
links_jogadores = set()

for elemento in elementos_jogadores:
    links_jogadores.add(elemento['href'])
```

###Coleta de Dados das Partidas
```python
# Coleta de dados das partidas
for jogador in links_jogadores:
    # ...
    for links_partidas in partidas:
        # ...
        try:
            estatisticas = soup.select_one("#__next > main > div.sc-fqkvVR.sc-dcJsrY.RLTNV.hjYsRn > div > div > div > div.sc-fqkvVR.sc-dLMFU.fLrHMT.gVgUiK.ps.ps--active-y > div:nth-child(1) > div > div:nth-child(3)").get_text()
            # ...
        except:
            # Tratamento de erros
            # ...
```

Este projeto demonstra habilidades em raspagem de dados, manipulação de páginas web e tratamento de erros. Mostrando a capacidade de desenvolver soluções de automação para coletar informações da web de maneira eficiente e organizada.

