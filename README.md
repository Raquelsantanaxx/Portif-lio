# Visão geral 📈
## Contexto 
Painel para auxiliar na tomada de decisões dentro da organização, "Toman Bike Share”, uma empresa Ficticia. 

## Tecnologias utilizadas 
*SQL:* manipulção e consultas no banco de dados

*POWER BI:* painel de visualização dos resultados. 

## Solicitação do cliente 

“ Solicitação de Desenvolvimento de Painel de Compartilhamento de Bicicletas Toman”

Caro Analista de Dados,
Precisamos da sua expertise para desenvolver um painel para o "Toman Bike Share" que exiba nossas principais métricas de desempenho, possibilitando uma tomada de decisão informada.
Requisitos:<br>
    •	Análise de Receita por Hora <br>
    •	Tendências de Lucro e Receita <br>
    •	Receita Sazonal<br>
    •	Demografia dos Usuários<br><br>
Design e Estética: Utilize as cores da nossa empresa e garanta que o painel seja fácil de navegar.<br>
Fonte de Dados: O acesso aos nossos bancos de dados será fornecido. Caso não exista um banco de dados, por favor, crie um.
Prazo: Precisamos de uma versão preliminar o mais rápido possível.<br>
Por favor, forneça um cronograma estimado para a conclusão e uma recomendação sobre o aumento de preços no próximo ano.<br>


## Fluxo de trabalho utilizado 
1.	Crie um Banco de Dados
2.	Desenvolva Consultas SQL
3.	Conecte o Power BI ao Banco de Dados
4.	Construa um Painel no Power BI
5.	Responda à Pergunta de Análise


## Codigo utilizado 
 o codigo foi gerado dentro do SQL server 
```sql 
WITH cte AS (
    SELECT * FROM bike_share_yr_0
    UNION ALL
    SELECT * FROM bike_share_yr_1
)
SELECT 
    dteday,
    season,
    A.yr,
    weekday,
    hr,
    rider_type,
    riders,
    price / 100 AS price,
    COGS / 100 AS COGS,
    (riders * price) / 100 AS revenue,
    (riders * price - COGS) / 100 AS profit
FROM cte A
LEFT JOIN cost_table B
ON A.yr = B.yr;
```
## Painel de visualização 



