#### **"Dados sintéticos, gerados para simular uma rede varejista. Validação temporal: MAE 3,68 e RMSE 5,22, sem comparação com baseline."**

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
<img width="673" height="441" alt="Captura de tela 2026-05-10 182302" src="https://github.com/user-attachments/assets/7cbd45af-871b-4630-9286-222005edbecd" />

### 2. Análise de Impacto (SHAP Values)
Visualização dos fatores que mais influenciaram as previsões. Utiliza os valores SHAP para mostrar se variáveis como "Fim de Semana" ou "Média Móvel" puxaram a previsão para cima ou para baixo.
<img width="661" height="431" alt="Captura de tela 2026-05-10 182612" src="https://github.com/user-attachments/assets/72c007cb-d962-486b-883d-1e982d52b24e" />

### 3. Alerta de Reposição (Status de Estoque)
Tabela dinâmica que cruza a previsão de demanda com o saldo em estoque. Exibe alertas de **"Comprar Agora"** caso a demanda prevista supere o estoque disponível.
<img width="668" height="298" alt="Captura de tela 2026-05-10 182551" src="https://github.com/user-attachments/assets/cdc0003b-2f89-4230-bf4a-4486d06a883f" />

**"O arquivo do Power BI e a base de dados não estão incluídos neste repositório; o notebook mostra o pipeline, mas não roda sem eles."**

## ⚙️ Como Executar
1. **Ambiente Python:** Instale as dependências usando `pip install -r requirements.txt`.
2. **Pipeline de IA:** Execute o notebook `projeto.ipynb` para gerar o arquivo `predicoes_inventory.csv`.
3. **Power BI:** Abra o arquivo `.pbix` ou importe o CSV gerado seguindo as configurações regionais de "Inglês (Estados Unidos)".
