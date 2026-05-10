# Inventory Intelligence - Previsão de Demanda e Gestão de Estoque

Este projeto integra Banco de Dados (PostgreSQL), Machine Learning (XGBoost + SHAP) e Business Intelligence (Power BI) para otimizar a gestão de inventário de uma rede varejista.

## Objetivo do Projeto
O objetivo principal é prever a demanda diária de produtos para os próximos 7 dias, identificando antecipadamente riscos de ruptura de estoque e fornecendo transparência sobre os fatores que influenciam as vendas.

## Tecnologias Utilizadas
- **Banco de Dados:** PostgreSQL (SQL para agregação e limpeza).
- **Linguagem:** Python 3.x.
- **Bibliotecas ML:** XGBoost, Scikit-learn.
- **Explicabilidade:** SHAP (TreeExplainer).
- **Engenharia de Dados:** Pandas, NumPy, SQLAlchemy.
- **Visualização:** Power BI.

## Estrutura do Dashboard (Power BI)

O dashboard foi construído para facilitar a tomada de decisão gerencial, focado em três pilares:

### 1. Tendência de Demanda: Real vs. Previsão
Gráfico de linhas que compara as vendas históricas com as predições da IA. Permite validar visualmente a assertividade do modelo XGBoost.
*(Adicione aqui o print do seu gráfico de linhas)*

### 2. Análise de Impacto (SHAP Values)
Visualização dos fatores que mais influenciaram as previsões. Utiliza os valores SHAP para mostrar se variáveis como "Fim de Semana" ou "Média Móvel" puxaram a previsão para cima ou para baixo.
*(Adicione aqui o print do seu gráfico de barras do SHAP)*

### 3. Alerta de Reposição (Status de Estoque)
Tabela dinâmica que cruza a previsão de demanda com o saldo em estoque. Exibe alertas de **"Comprar Agora"** caso a demanda prevista supere o estoque disponível.

## ⚙️ Como Executar
1. **Banco de Dados:** Execute o script SQL contido na pasta `/sql` para criar e popular as tabelas.
2. **Ambiente Python:** Instale as dependências usando `pip install -r requirements.txt`.
3. **Pipeline de IA:** Execute o notebook `projeto.ipynb` para gerar o arquivo `predicoes_inventory.csv`.
4. **Power BI:** Abra o arquivo `.pbix` ou importe o CSV gerado seguindo as configurações regionais de "Inglês (Estados Unidos)".