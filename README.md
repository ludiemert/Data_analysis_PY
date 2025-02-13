Portugues

# 📊 Python Insights - Analisando Dados com Python

## 📝 Case - Cancelamento de Clientes

Você foi contratado por uma empresa com mais de **800 mil clientes** para um projeto de análise de dados. A empresa identificou que a maioria de seus clientes já cancelaram o serviço e deseja entender os principais motivos desses cancelamentos, buscando ações eficazes para reduzir essa taxa.

📂 **Base de Dados e Arquivos:** [Clique aqui para acessar](https://drive.google.com/drive/folders/1uDesZePdkhiraJmiyeZ-w5tfc8XsNYFZ?usp=drive_link)

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
