# Previsao-de-Demanda-de-Energia-com-LSTM-

📌 **Sobre o Projeto**

O objetivo deste trabalho é desenvolver e avaliar um modelo preditivo baseado em redes neurais recorrentes com arquitetura Long Short-Term Memory (LSTM) para a previsão de demanda de energia elétrica a curto prazo. Busca-se analisar a acurácia do modelo em cenários de alta variabilidade, validando sua aplicabilidade como ferramenta de suporte à decisão no planejamento e controle de sistemas elétricos contemporâneos.

📊 **Metodologia**

O desenvolvimento do modelo preditivo baseado em redes neurais artificiais foi executado utilizando a linguagem de programação Python (versão 3.13) integrada ao ambiente de desenvolvimento Visual Studio Code (VS Code). Para a manipulação de dados e construção da arquitetura de Deep Learning, foram empregadas as bibliotecas Pandas, NumPy, Scikit-Learn e PyTorch (torch), além da Matplotlib para a plotagem dos resultados gráficos.

📋 **Características do dataset e criérios de amostragem**
+ Período de coleta: Registros horários iniciando-se em 01 de janeiro de 2026;
+ Granularidade Temporal: Intervalos horários fixos (frequência de 1 em 1 hora);
+ Volume Total de Amostras: 2.400 observações horárias consecutivas;
+ Composição Estocástica: A curva de carga foi gerada a partir de uma assinatura base de 40.000 MW, acrescida de componentes harmônicos correspondentes à sazonalidade diária (5.000 MW) e semanal (2.000 MW), além de um ruído gaussiano aleatório (µ = 0, σ=800" MW" ) representativo das flutuações imprevisíveis do sistema.

📈**Estruturação da Janela Temporal (Sliding Window)**
+ Definiu-se um horizonte de retrovisor (look-back) de 24 horas para prever a carga do passo imediatamente subsequente (t+1). 
+ Descontando-se o período inicial de atraso (lag) necessário para preencher a primeira janela, obteve-se um espaço amostral efetivo de 2.376 janelas operacionais.

🧮**Divisão dos Dados e Arquitetura do Modelo**
+ Conjunto de Treinamento (80%)
+ Conjunto de Teste (20%)

**RESULTADOS**

Figura 1 – Curva de convergência do erro quadrático médio (MSE) durante o treinamento da rede LSTM.
<img width="886" height="413" alt="image" src="https://github.com/user-attachments/assets/137c74e5-f183-45f5-a03a-6267cfdb29fe" /><br/><br/>

Figura 2 – Comparativo cronológico de 168 horas entre a carga real do sistema e a previsão gerada pela rede LSTM.
<img width="886" height="397" alt="image" src="https://github.com/user-attachments/assets/d41343e1-3862-4e89-81b2-c1269db91d48" /><br/><br/>

Tabela 1 – Análise Comparativa de Desempenho: LSTM vs. Baseline de Média Móvel
<img width="717" height="212" alt="image" src="https://github.com/user-attachments/assets/2eb79fba-3fbe-46ed-a223-68ed045b6ee5" /><br/><br/>


