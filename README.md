# 📊 Python Insights - Analyzing Data with Python

## 📝 Case - Customer Churn Analysis

You have been hired by a company with over **800,000 customers** for a data analysis project. The company has identified that most of its customers have already canceled the service and wants to understand the main reasons behind these cancellations, aiming to implement effective actions to reduce this rate.

📂 **Database and Files:** [Click here to access](https://github.com/ludiemert/Data_analysis_PY)

---

## 🚀 Project Step-by-Step

### 🔹 Step 1: Import the Database
```python
import pandas as pd

dataset = pd.read_csv("cancelamentos_sample.csv")
```

### 🔹 Step 2: View the Database
```python
dataset = dataset.drop(columns="CustomerID")
display(dataset)
```
*We removed unnecessary columns to facilitate analysis.*

### 🔹 Step 3: Data Cleaning and Preparation
```python
display(dataset.info())
# Removing empty values
dataset = dataset.dropna()
display(dataset.info())
```
*We adjusted missing values to ensure accurate analysis.*

### 🔹 Step 4: Initial Analysis of Cancellations
```python
display(dataset["canceled"].value_counts())
display(dataset["canceled"].value_counts(normalize=True))
```
*We identified the proportion of active and canceled customers.*

### 🔹 Step 5: Analyzing the Causes of Cancellations

🔍 **How do the database columns impact cancellations?**

```python
import plotly.express as px

for column in dataset.columns:
    chart = px.histogram(dataset, x=column, color="canceled")
    chart.show()
```

📌 **Key Insights:**
1. **Customers with monthly contracts** have a high cancellation rate ➝ 📢 Offer discounts on annual and quarterly plans.
2. **Customers who call the call center more than 4 times** are more likely to cancel ➝ 📞 Implement processes to resolve issues within 3 calls.
3. **Customers who are more than 20 days late on payments** have a high chance of canceling ➝ 💳 Implement a policy to resolve delays within 10 days.

### 🔹 Step 6: Applying Improvements and Measuring Impact
```python
dataset = dataset[dataset["contract_duration"] != "Monthly"]
dataset = dataset[dataset["call_center_calls"] <= 4]
dataset = dataset[dataset["days_late"] <= 20]

display(dataset["canceled"].value_counts())
display(dataset["canceled"].value_counts(normalize=True))
```
*We applied filters based on insights and checked for improvements in the cancellation rate.*

---

## 🛠 Technologies Used
- **Language:** Python 🐍
- **Libraries:** Pandas, NumPy, OpenPyXL, Plotly

## 📌 Installing Dependencies
```sh
pip install pandas numpy openpyxl nbformat ipykernel plotly
```

## 📢 Contribution
Feel free to contribute! If you have suggestions, open a **Pull Request** or an **Issue**. 🚀

---

### Portugues

# 📊 Python Insights - Analisando Dados com Python

## 📝 Case - Cancelamento de Clientes

Você foi contratado por uma empresa com mais de **800 mil clientes** para um projeto de análise de dados. A empresa identificou que a maioria de seus clientes já cancelaram o serviço e deseja entender os principais motivos desses cancelamentos, buscando ações eficazes para reduzir essa taxa.

📂 **Base de Dados e Arquivos:**  [Click here to access](https://github.com/ludiemert/Data_analysis_PY)

---

## 🚀 Passo a Passo do Projeto

### 🔹 Passo 1: Importar a Base de Dados
```python
import pandas as pd

tabela = pd.read_csv("cancelamentos_sample.csv")
```

### 🔹 Passo 2: Visualizar a Base de Dados
```python
tabela = tabela.drop(columns="CustomerID")
display(tabela)
```
*Removemos colunas desnecessárias para facilitar a análise.*

### 🔹 Passo 3: Limpeza e Preparação dos Dados
```python
display(tabela.info())
# Removendo valores vazios
tabela = tabela.dropna()
display(tabela.info())
```
*Ajustamos valores ausentes para garantir uma análise precisa.*

### 🔹 Passo 4: Análise Inicial dos Cancelamentos
```python
display(tabela["cancelou"].value_counts())
display(tabela["cancelou"].value_counts(normalize=True))
```
*Identificamos a proporção de clientes ativos e cancelados.*

### 🔹 Passo 5: Análise das Causas dos Cancelamentos

🔍 **Como as colunas da base impactam no cancelamento?**

```python
import plotly.express as px

for coluna in tabela.columns:
    grafico = px.histogram(tabela, x=coluna, color="cancelou")
    grafico.show()
```

📌 **Insights Obtidos:**
1. **Clientes com contrato mensal** têm alta taxa de cancelamento ➝ 📢 Oferecer descontos em planos anuais e trimestrais.
2. **Clientes que ligam mais de 4 vezes para o call center** têm maior probabilidade de cancelar ➝ 📞 Criar processos para resolver problemas em até 3 ligações.
3. **Clientes que atrasam mais de 20 dias** têm alta chance de cancelamento ➝ 💳 Implementar uma política para resolver atrasos em até 10 dias.

### 🔹 Passo 6: Aplicando Melhorias e Medindo Impacto
```python
tabela = tabela[tabela["duracao_contrato"] != "Monthly"]
tabela = tabela[tabela["ligacoes_callcenter"] <= 4]
tabela = tabela[tabela["dias_atraso"] <= 20]

display(tabela["cancelou"].value_counts())
display(tabela["cancelou"].value_counts(normalize=True))
```
*Aplicamos filtros com base nos insights e verificamos a melhoria na taxa de cancelamento.*

---

## 🛠 Tecnologias Utilizadas
- **Linguagem:** Python 🐍
- **Bibliotecas:** Pandas, NumPy, OpenPyXL, Plotly

## 📌 Instalação das Dependências
```sh
pip install pandas numpy openpyxl nbformat ipykernel plotly
```

## 📢 Contribuição
Sinta-se à vontade para contribuir! Caso tenha sugestões, abra um **Pull Request** ou uma **Issue**. 🚀

---

---
## License
- This project is licensed under the MIT License.
---


### 📦 Contribution

 - Feel free to contribute by submitting pull requests or reporting issues.

- #### My LinkedIn - [![Linkedin Badge](https://img.shields.io/badge/-LucianaDiemert-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/lucianadiemert/)](https://www.linkedin.com/in/lucianadiemert/)

## 🌐 **Contact**
<img align="left" src="https://www.github.com/ludiemert.png?size=150">

#### [**Luciana Diemert**](https://github.com/ludiemert)

🛠 Full-Stack Developer <br>
🖥️ Python Enthusiast | Computer Vision | AI Integrations <br>
📍 São Jose dos Campos – SP, Brazil

<a href="https://www.linkedin.com/in/lucianadiemert" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn Badge" height="25"></a>&nbsp;
<a href="mailto:lucianadiemert@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=flat&logo=gmail&logoColor=white" alt="Gmail Badge" height="25"></a>&nbsp;
<a href="#"><img src="https://img.shields.io/badge/Discord-%237289DA.svg?logo=discord&logoColor=white" title="LuDiem#0654" alt="Discord Badge" height="25"></a>&nbsp;
<a href="https://www.github.com/ludiemert" target="_blank"><img src="https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white" alt="GitHub Badge" height="25"></a>&nbsp;

<br clear="left"/>

---
Developed with ❤ by [ludiemert](https://github.com/ludiemert).

