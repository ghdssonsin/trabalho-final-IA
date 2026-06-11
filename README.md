# 📊 Pobreza Global e Desigualdade Econômica (2015–2024)

> **Análise com Aprendizado de Máquina — Trabalho Final de Inteligência
> Artificial**

---

## 📝 Descrição do Projeto

Este projeto investiga padrões de **pobreza global** e **desigualdade
econômica** entre 2015 e 2024 usando técnicas de **Aprendizado de Máquina**
(supervisionado e não supervisionado). A análise cruza indicadores
socioeconômicos, ambientais e de bem-estar humano de múltiplos países e regiões
do mundo.

### Objetivos

- Realizar uma **Análise Exploratória de Dados (EDA)** completa sobre
  indicadores globais de pobreza
- Identificar **tendências temporais** e **comparações regionais** de
  desigualdade
- Aplicar **K-Means Clustering** para agrupar países por perfis socioeconômicos
- Treinar **modelos preditivos de regressão** (Linear, Random Forest, Gradient
  Boosting) para prever taxas de pobreza
- Gerar **projeções exploratórias** de indicadores para 2025–2030

---

## 🗃️ Base de Dados

| Informação    | Detalhe                                                                                                            |
| ------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Nome**      | Global Poverty and Economic Inequality 2015–2024                                                                   |
| **Fonte**     | [Kaggle — hamnamunir](https://www.kaggle.com/datasets/hamnamunir/global-poverty-and-economic-inequality-2015-2024) |
| **Formato**   | CSV (`global_poverty_economic_inequality.csv`)                                                                     |
| **Volume**    | 10.000 observações × 25 variáveis                                                                                  |
| **Período**   | 2015 a 2024                                                                                                        |
| **Cobertura** | Múltiplos países de todas as regiões do mundo                                                                      |

### Variáveis do Dataset

O dataset contém **25 variáveis** organizadas em três categorias:

<details>
<summary><strong>🔹 Identificação (5 variáveis)</strong></summary>

| Variável       | Descrição                                                            |
| -------------- | -------------------------------------------------------------------- |
| `record_id`    | Identificador único do registro                                      |
| `year`         | Ano de referência (2015–2024)                                        |
| `country`      | País                                                                 |
| `region`       | Região geográfica                                                    |
| `income_group` | Grupo de renda (Low Income, Lower-Middle, Upper-Middle, High Income) |

</details>

<details>
<summary><strong>🔹 Indicadores Econômicos (7 variáveis)</strong></summary>

| Variável                  | Descrição                      |
| ------------------------- | ------------------------------ |
| `gdp_per_capita_usd`      | PIB per capita em dólares      |
| `poverty_rate_pct`        | Taxa de pobreza (%)            |
| `gini_coefficient`        | Coeficiente de Gini (0–100)    |
| `unemployment_rate_pct`   | Taxa de desemprego (%)         |
| `inflation_rate_pct`      | Taxa de inflação (%)           |
| `remittances_pct_of_gdp`  | Remessas como % do PIB         |
| `foreign_aid_million_usd` | Ajuda externa em milhões (USD) |

</details>

<details>
<summary><strong>🔹 Indicadores de Bem-Estar (13 variáveis)</strong></summary>

| Variável                         | Descrição                                  |
| -------------------------------- | ------------------------------------------ |
| `hdi_score`                      | Índice de Desenvolvimento Humano (0–1)     |
| `literacy_rate_pct`              | Taxa de alfabetização (%)                  |
| `life_expectancy_years`          | Expectativa de vida (anos)                 |
| `child_mortality_per_1000`       | Mortalidade infantil por 1.000 nascimentos |
| `electricity_access_pct`         | Acesso à eletricidade (%)                  |
| `clean_water_access_pct`         | Acesso à água limpa (%)                    |
| `internet_penetration_pct`       | Penetração da internet (%)                 |
| `female_labor_participation_pct` | Participação feminina no trabalho (%)      |
| `social_protection_coverage_pct` | Cobertura de proteção social (%)           |
| `income_share_top10_pct`         | Renda dos 10% mais ricos (%)               |
| `income_share_bottom40_pct`      | Renda dos 40% mais pobres (%)              |
| `urban_population_pct`           | População urbana (%)                       |
| `co2_per_capita_tonnes`          | CO₂ per capita (toneladas)                 |

</details>

---

## ⚙️ Pré-requisitos e Dependências

### Python

- **Python 3.8** ou superior

### Bibliotecas Necessárias

| Biblioteca     | Versão Mínima | Finalidade                      |
| -------------- | ------------- | ------------------------------- |
| `numpy`        | ≥ 1.21        | Operações numéricas vetorizadas |
| `pandas`       | ≥ 1.3         | Manipulação de dados tabulares  |
| `matplotlib`   | ≥ 3.4         | Visualização de gráficos        |
| `seaborn`      | ≥ 0.11        | Visualizações estatísticas      |
| `scikit-learn` | ≥ 1.0         | Modelos de Machine Learning     |
| `kagglehub`    | ≥ 0.1         | Download automático do dataset  |
| `openpyxl`     | ≥ 3.0         | Exportação para Excel (.xlsx)   |

### Instalação das Dependências

```bash
pip install numpy pandas matplotlib seaborn scikit-learn kagglehub openpyxl
```

Ou, se preferir instalar tudo de uma vez com um arquivo de requisitos:

```bash
pip install -r requirements.txt
```

<details>
<summary><strong>📄 Conteúdo sugerido para <code>requirements.txt</code></strong></summary>

```
numpy>=1.21
pandas>=1.3
matplotlib>=3.4
seaborn>=0.11
scikit-learn>=1.0
kagglehub>=0.1
openpyxl>=3.0
```

</details>

---

## 🚀 Como Executar o Projeto

### Opção 1: Executando Localmente (Jupyter Notebook)

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/SEU_USUARIO/trabalho-final-IA.git
   cd trabalho-final-IA
   ```

2. **Crie um ambiente virtual (recomendado):**
   ```bash
   python -m venv venv

   # Windows
   venv\Scripts\activate

   # Linux / macOS
   source venv/bin/activate
   ```

3. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure as credenciais do Kaggle** (para download automático do dataset):
   - Acesse [kaggle.com/settings](https://www.kaggle.com/settings) → seção
     **API** → **Create New Token**
   - Salve o arquivo `kaggle.json` em:
     - **Windows:** `C:\Users\<SEU_USUARIO>\.kaggle\kaggle.json`
     - **Linux/macOS:** `~/.kaggle/kaggle.json`
   - Alternativamente, baixe o CSV manualmente do
     [Kaggle](https://www.kaggle.com/datasets/hamnamunir/global-poverty-and-economic-inequality-2015-2024)
     e coloque na mesma pasta do notebook.

5. **Inicie o Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

6. **Abra o arquivo** `pobreza_global_desigualdade_2015_2024_colab.ipynb` e
   execute todas as células sequencialmente.

### Opção 2: Executando no Google Colab

1. Faça upload do arquivo `.ipynb` para o
   [Google Colab](https://colab.research.google.com/)
2. As dependências `kagglehub` e `openpyxl` serão instaladas automaticamente
   pela primeira célula do notebook
3. O dataset será baixado automaticamente via `kagglehub`
4. Execute todas as células na ordem (**Runtime → Run all**)

> **💡 Dica:** O notebook foi projetado para ser 100% compatível com o Google
> Colab sem nenhuma configuração adicional.

---

## 📁 Estrutura do Projeto

```
trabalho-final-IA/
│
├── 📓 pobreza_global_desigualdade_2015_2024_colab.ipynb   # Notebook principal
├── 📄 README.md                                           # Este arquivo
├── 📄 requirements.txt                                    # Dependências (opcional)
└── 📄 documentar_notebook.py                              # Script auxiliar de documentação
```

---

## 🧠 Metodologia e Técnicas Utilizadas

### 1. Análise Exploratória de Dados (EDA)

- Estatísticas descritivas (média, mediana, desvio padrão, quartis)
- Verificação de valores ausentes e outliers
- Distribuição de variáveis por região e grupo de renda

### 2. Visualização Estatística

- Gráficos de tendência temporal
- Boxplots comparativos por região
- Matriz de correlação (heatmap)
- Gráficos de dispersão entre indicadores-chave

### 3. Aprendizado Não Supervisionado — K-Means Clustering

- Padronização Z-score das features numéricas
- Método do Cotovelo (Elbow Method) para seleção do número ideal de clusters
- Agrupamento de países em perfis socioeconômicos

### 4. Aprendizado Supervisionado — Modelos de Regressão

| Modelo                | Descrição                                 |
| --------------------- | ----------------------------------------- |
| **Regressão Linear**  | Baseline — relação linear entre variáveis |
| **Random Forest**     | Ensemble de árvores de decisão (bagging)  |
| **Gradient Boosting** | Ensemble sequencial com correção de erros |

### 5. Avaliação dos Modelos

| Métrica  | Descrição                     |
| -------- | ----------------------------- |
| **MAE**  | Erro Médio Absoluto           |
| **RMSE** | Raiz do Erro Quadrático Médio |
| **R²**   | Coeficiente de Determinação   |

- **Validação Cruzada K-Fold** (K=5) para estimativa robusta de generalização

### 6. Projeções Exploratórias (2025–2030)

- Extrapolação de tendências lineares para cenários futuros

---

## 📊 Principais Resultados

- **10.000 registros** analisados cobrindo múltiplos países e regiões
  (2015–2024)
- Forte correlação negativa entre **PIB per capita** e **taxa de pobreza**
- O **Gradient Boosting** apresentou o melhor desempenho preditivo entre os
  modelos testados
- Clusters identificados revelam perfis distintos: países de alta renda com
  baixa pobreza vs. países de baixa renda com alta vulnerabilidade
- Indicadores como **IDH**, **acesso à eletricidade** e **taxa de
  alfabetização** são fortemente preditivos de pobreza

---

## 🛠️ Tecnologias

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="Scikit-learn"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Seaborn-444876?style=for-the-badge&logo=seaborn&logoColor=white" alt="Seaborn"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Google Colab"/>
</p>

---

## 👥 Autores

- **Guilherme Sonsin** — [GitHub](https://github.com/SEU_USUARIO)

> _Trabalho Final — Disciplina de Inteligência Artificial_

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais
detalhes.

---

## 🤝 Contribuições

Contribuições são bem-vindas! Para contribuir:

1. Faça um **fork** do projeto
2. Crie uma **branch** para sua feature
   (`git checkout -b feature/minha-feature`)
3. Faça **commit** das suas alterações
   (`git commit -m 'Adiciona minha feature'`)
4. Faça **push** para a branch (`git push origin feature/minha-feature`)
5. Abra um **Pull Request**

---

## 📚 Referências

- [Global Poverty and Economic Inequality 2015–2024 — Kaggle](https://www.kaggle.com/datasets/hamnamunir/global-poverty-and-economic-inequality-2015-2024)
- [Banco Mundial — Dados de Pobreza](https://data.worldbank.org/topic/poverty)
- [PNUD — Índice de Desenvolvimento Humano](https://hdr.undp.org/)
- [Scikit-learn — Documentação Oficial](https://scikit-learn.org/stable/)
