# 🔍 Análise de Criminalidade e Fatores Socioeconômicos em Minas Gerais

Trabalho Final - Ciência de Dados | CEFET-MG

## 📋 Sobre o Projeto

Este projeto realiza uma análise completa e estatisticamente robusta da relação entre criminalidade e fatores socioeconômicos nos municípios de Minas Gerais. A análise combina dados de crimes violentos, indicadores socioeconômicos (PIB, IDHM, escolarização), investimentos públicos e dados carcerários para identificar padrões e correlações significativas.

## 🎯 Objetivos

- Analisar a correlação entre taxa de criminalidade e indicadores socioeconômicos
- Identificar padrões de investimento público e sua relação com segurança
- Examinar a relação entre criminalidade e encarceramento
- Agrupar municípios por perfis similares usando técnicas de clustering
- Gerar visualizações profissionais e mapas geoespaciais
- Criar modelo preditivo para taxa de crimes

## 🚀 Como Executar

### Pré-requisitos

- Python 3.8 ou superior
- Jupyter Notebook ou JupyterLab

### Instalação

1. Clone o repositório:
```bash
git clone <url-do-repositorio>
cd trabFinal
```

2. Crie um ambiente virtual (recomendado):
```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

### Execução

1. Abra o Jupyter Notebook:
```bash
jupyter notebook
```

2. Abra o arquivo `main_organizada.ipynb`

3. Execute todas as células em ordem (ou execute a função principal `executar_analise_completa()`)

### ⚠️ Arquivos de Dados Necessários

Para executar o notebook completo, você precisará dos seguintes arquivos de dados (não incluídos no repositório devido ao tamanho):

- `Banco_Crimes_Violentos_2025.csv` - Dados de crimes violentos por município
- `Dados Abertos_Pop_Pris_Sexo_Escolaridade_Jan_2017_Jun_2024.xlsx` - Dados carcerários

**Nota:** O notebook também realiza web scraping automático de dados do IBGE e Portal da Transparência, mas pode usar arquivos CSV pré-existentes se disponíveis.

## 📁 Estrutura do Projeto

### Arquivos Principais

- **`main_organizada.ipynb`** - Notebook principal com toda a análise
- **`requirements.txt`** - Dependências do projeto

### Resultados Gerados

#### Visualizações (PNG)
- **`figura_01_correlacoes_pib.png`** - Matriz de correlações e análise PIB vs Criminalidade
- **`figura_02_distribuicoes_recursos.png`** - Distribuições e análise de investimentos públicos
- **`figura_03_rankings_seguranca.png`** - Rankings dos municípios mais seguros e eficientes

#### Mapas Geoespaciais (PNG)
- **`mapa_municipios_crimes.png`** - Mapa interativo com marcadores coloridos por taxa de crimes
- **`mapa_calor_crimes.png`** - Mapa de calor (heatmap) da intensidade de criminalidade
- **`mapa_clusters_municipios.png`** - Mapa mostrando agrupamentos (clusters) de municípios

#### Relatórios
- **`relatorio_executivo.txt`** - Relatório executivo com principais achados e correlações

## 🔬 Metodologia

### 1. Coleta de Dados
- **Web Scraping:** Dados do IBGE (população, IDHM, escolarização, PIB)
- **Web Scraping:** Dados do Portal da Transparência (orçamentos e investimentos)
- **Arquivos Locais:** Dados de crimes violentos e população carcerária

### 2. Processamento e Limpeza
- Limpeza e padronização de nomes de municípios
- Conversão de formatos numéricos (brasileiro/americano)
- Tratamento de valores ausentes e outliers
- Cálculo de taxas per capita (crimes, encarceramento, recursos)

### 3. Análises Estatísticas
- **Teste de Normalidade:** Shapiro-Wilk
- **Teste de Diferenças:** Teste t de Student (comparação de grupos)
- **Correlações:** Pearson
- **Clustering:** K-Means (agrupamento de municípios)
- **Modelo Preditivo:** Regressão Linear Múltipla

### 4. Visualizações
- Gráficos de correlação (heatmaps, scatter plots)
- Distribuições (violin plots, histogramas)
- Rankings e comparações
- Mapas geoespaciais interativos

## 📊 Principais Resultados

### Correlações Identificadas

Com base na análise realizada, foram identificadas as seguintes correlações com a taxa de crimes:

- **Total de Recursos per capita:** Correlação negativa forte (r = -0.683)
  - Municípios com mais investimentos públicos tendem a ter menos crimes
  
- **IDHM (Índice de Desenvolvimento Humano Municipal):** Correlação positiva moderada (r = 0.623)
  - Municípios com maior IDHM apresentam maior taxa de crimes (paradoxo aparente)
  
- **Escolarização:** Correlação negativa moderada (r = -0.336)
  - Maior escolarização associada a menor criminalidade

### Agrupamentos (Clusters)

O algoritmo K-Means identificou 3 grupos distintos de municípios com perfis similares em relação a:
- Taxa de crimes
- PIB per capita
- Recursos públicos per capita
- Escolarização

## 🛠️ Tecnologias Utilizadas

- **Python 3.8+**
- **Pandas** - Manipulação e análise de dados
- **NumPy** - Operações matemáticas
- **Matplotlib & Seaborn** - Visualizações
- **Scipy** - Testes estatísticos
- **Scikit-learn** - Machine Learning (clustering e regressão)
- **BeautifulSoup & Requests** - Web Scraping
- **Folium** - Mapas geoespaciais interativos
- **Selenium** - Conversão de mapas HTML para PNG

## 📈 Estrutura do Notebook

O notebook `main_organizada.ipynb` está organizado em células:

1. **Cell 0** - Imports e configurações iniciais
2. **Cell 1** - Funções auxiliares de limpeza de dados
3. **Cell 2** - Web scraping IBGE (dados socioeconômicos)
4. **Cell 3** - Web scraping códigos IBGE
5. **Cell 4** - Web scraping orçamentos (Portal da Transparência)
6. **Cell 5** - Processamento de dados carcerários
7. **Cell 6** - Análises estatísticas avançadas e modelo preditivo
8. **Cell 7** - Visualizações profissionais (3 figuras)
9. **Cell 8** - Geração de relatório executivo
10. **Cell 9** - Função principal (`executar_analise_completa()`)
11. **Cell 10** - Geração de mapas geoespaciais

## 📝 Notas Importantes

- O web scraping inclui delays entre requisições para respeitar os servidores
- Os dados carcerários são filtrados apenas para o ano de 2024
- Os mapas são gerados em HTML e convertidos para PNG automaticamente
- Alguns arquivos CSV intermediários são gerados durante a execução (podem ser grandes)

## 👤 Autor

Trabalho desenvolvido para o curso de Ciência de Dados - CEFET-MG

## 📄 Licença

Este projeto é parte de um trabalho acadêmico.

---

**Última atualização:** 2025

