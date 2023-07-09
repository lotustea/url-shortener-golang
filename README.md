# url-shortener-golang

# Simples encurtardor de links utilizando Golang + Fiber e Redis.

# Principais Recursos:
## Cota de 10 links por IP no tempo de 30 minutos
## URL Curta customizável ou aleatoria 
## Expiracao da URL curta

# 1 - docker-compose up -d
# 2 - Rota principal
  ``POST http://127.0.0.1:3434/api/v1``
  ## request body:
  ``
  {
    "url":"https://github.com/lotustea/url-shortener-golang/", //obrigatorio
    "short": "shortenerRepo" //opcional
  }
  ``
  ## response exemplo:
  ``
    {
      "url": "https://github.com/lotustea/url-shortener-golang/",
      "short": "localhost:3434/f614ce", //se houver short na request -> localhost:3434/shortenerRepo
      "expiry": 24,
      "rate_limit": 9,
      "rate_limit_reset": 30
    }
  ``
