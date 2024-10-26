# Projeto de Modelo de Dados - Esquema em Estrela ⭐

Este projeto faz parte de um desafio de criação de um modelo de dados baseado no esquema em estrela (Star Schema), utilizando dados financeiros. O objetivo é transformar uma tabela única (`Financial Sample`) em tabelas fato e dimensão para otimizar a análise dos dados e melhorar a performance nas consultas. 

## 📝 Descrição do Desafio de Projeto

O processo consiste em:

1. Criar uma tabela de backup chamada **Financials_origem** a partir da tabela original (`Financial Sample`) e ocultá-la para referência futura.
2. Criar tabelas de dimensão e fato a partir dos dados originais, conforme o esquema em estrela.

### 🗂 Tabelas Criadas

1. **D_Produtos** 
   - **Colunas**: `ID_produto`, `Produto`, `Média de Unidades Vendidas`, `Média do Valor de Vendas`, `Mediana do Valor de Vendas`, `Valor Máximo de Venda`, `Valor Mínimo de Venda`.
   - Função: Contém informações resumidas dos produtos e estatísticas de vendas.

2. **D_Produtos_Detalhes**
   - **Colunas**: `ID_produtos`, `Discount Band`, `Sale Price`, `Units Sold`, `Manufacturing Price`.
   - Função: Fornece detalhes adicionais sobre os produtos, como preço de venda, preço de fabricação e unidades vendidas.

3. **D_Descontos**
   - **Colunas**: `ID_produto`, `Discount`, `Discount Band`.
   - Função: Contém dados de descontos para cada produto.

4. **D_Detalhes**
   - Contém informações adicionais sobre vendas, não cobertas pelas demais tabelas de dimensão.

5. **D_Calendar**
   - Criada usando a função DAX `CALENDAR()`.
   - **Colunas**: `Date`, `Year`, `Month Name`, `Month Number`, `Segment`.
   - Função: Representa a dimensão de tempo para facilitar a análise temporal das vendas.

6. **F_Vendas**
   - **Colunas**: `SK_ID`, `ID_Produto`, `Produto`, `Units Sold`, `Sales Price`, `Discount Band`, `Segment`, `Country`, `Salers`, `Profit`, `Date`.
   - Função: Tabela fato que registra as transações de vendas e os valores relacionados.

## 📐 Processo de Construção do Diagrama

1. **Criação das Tabelas de Dimensão**: A partir da tabela `Financial Sample`, foram selecionadas as colunas que formariam as dimensões relevantes para o modelo. Essas tabelas foram criadas por meio de agrupamento e seleção de colunas específicas, com cálculos de métricas como médias e medianas.

2. **Criação da Tabela Fato**: A tabela fato (`F_Vendas`) foi montada com base nos dados de vendas, centralizando os valores de cada transação e relacionando-os com as chaves das dimensões.

3. **Tabela de Calendário**: A tabela `D_Calendar` foi gerada com a função DAX `CALENDAR()`, permitindo análises baseadas em datas e possibilitando a criação de métricas temporais.

## ⚙️ Funcionalidades e Funções DAX Utilizadas

- **CALENDAR()**: Utilizada para criar a tabela `D_Calendar` com as datas de interesse.
- **Métricas Agregadas**: Calcularam-se médias, medianas e máximos para as tabelas de dimensão, agregando informações relevantes para facilitar a análise.

## 📂 Arquivos do Projeto

- **Arquivo PBIX**: Inclui o modelo completo em Power BI, contendo as tabelas de dimensão e fato e o relacionamento entre elas.
- **Esquema em Estrela**: O diagrama do esquema em estrela foi salvo como imagem e incluído neste repositório.

## 🔗 Link para o Repositório do Projeto

Acesse o repositório do projeto para ver o código e o modelo completo: [GitHub - desafio2](https://github.com/b3rnardo15/desafio2.git).

---

Este projeto foi desenvolvido para aprimorar habilidades em modelagem de dados e otimização de consultas. É ideal para quem deseja aprender mais sobre análise de dados e star schema!
