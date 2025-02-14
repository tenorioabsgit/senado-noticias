# 📰 Coletor de Notícias do Senado Federal

Este projeto realiza **web scraping** de notícias publicadas no portal oficial do **Senado Federal**, permitindo a extração de **títulos, links, datas e conteúdos completos** das matérias.

## 📌 Funcionalidades

✅ Busca de notícias relacionadas a um termo específico  
✅ Extração automática de **título, conteúdo, link e data da publicação**  
✅ Coleta de múltiplas páginas para obter resultados extensivos  
✅ Organização dos dados em um **arquivo CSV**  

---

## 🛠 Tecnologias Utilizadas

- **Linguagem:** R  
- **Pacotes:** `rvest`, `tidyverse`, `stringr`, `lubridate`  
- **Fonte de dados:** [Senado Federal](https://www12.senado.leg.br/noticias/)  

---

## 📂 Estrutura do Código

```
📁 /  (Diretório Raiz)
├── noticias_senado.R       # Script principal para coleta de notícias
└── noticias_senado.csv     # Arquivo de saída com as notícias extraídas
```

---

## 🚀 Como Executar

### 1️⃣ **Instalar os pacotes necessários**

Se ainda não estiverem instalados, execute no R:

```r
install.packages(c("rvest", "tidyverse", "stringr", "lubridate"))
```

### 2️⃣ **Modificar o termo de pesquisa**

No script `noticias_senado.R`, edite a variável `termo_pesquisa` para buscar por um nome ou tema diferente:

```r
termo_pesquisa <- "Inteligência Artificial"
```

### 3️⃣ **Executar o Script**

Para rodar o script e coletar as notícias:

```r
source("noticias_senado.R")
```

Os resultados serão armazenados em um **dataframe** e podem ser salvos em um arquivo CSV.

---

## 📊 Estrutura do Arquivo de Saída (`noticias_senado.csv`)

A saída será um CSV com as seguintes colunas:

| Data | Título | Conteúdo | Link |
|------|--------|----------|------|
| 2024-02-12 | Título da Notícia | Texto completo da matéria | URL da notícia |

---

## 🛑 Possíveis Problemas e Soluções

### ⚠️ **Erro ao acessar o site do Senado**
Se a conexão for bloqueada, experimente rodar o script em um horário diferente ou verificar sua conexão de internet.

### ⏳ **A coleta parece lenta?**
Caso queira **reduzir a quantidade de notícias coletadas**, diminua o intervalo de busca:

```r
intervalo_urls <- seq(from = 0L, to = 500, by = 30)  # Busca apenas as primeiras 500 notícias
```

### 🔄 **Problemas com formatação da data**
Se houver erro ao converter datas, tente modificar a lógica de extração da data dentro do script:

```r
data <- lubridate::dmy(data_extraida)
```

---

🚀 **Agora você pode coletar notícias automaticamente!** Qualquer dúvida, me avise! 😊
