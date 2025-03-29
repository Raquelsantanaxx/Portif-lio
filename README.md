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
    -	Análise de Receita por Hora <br>
    -	Tendências de Lucro e Receita <br>
    -	Receita Sazonal<br>
    -	Demografia dos Usuários<br><br>
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


![Captura de tela 2025-03-29 115410](https://github.com/user-attachments/assets/d6e7d0b2-3fb8-41ed-9121-70137952e585)



# Respondendo as perguntas 
## Receita por Hora 
1.  Horários mais movimentados: O período entre **10h e 15h** é o mais lucrativo, com receitas variando entre $1.200 e $1.500, principalmente ao meio-dia. <br> 
2.  Dias de maior receita: Terça-feira e quarta-feira são os mais lucrativos, com picos às 12h e 17h. Sexta-feira também traz resultados bons, mas menos certos. <br>
3. Tendências gerais: A alta demanda ocorre no meio do dia e início da noite em quase todos os dias. <b>


# Tendência de lucro e receita <br>
1.	O lucro e a receita apresentam um crescimento ao longo do tempo. De **janeiro de 2021 até setembro de 2022** , tanto a média de lucro quanto a média de receita aumentaram significativamente, atingindo o pico em setembro de 2022. <b> <br>
2.	A receita total acumulada é de $15 milhões e o lucro total é de $10,45 milhões, representando uma margem de lucro de 45%.


# Razonalidade <br>

Os ganhos variam conforme a temporada: <br>
1.	Temporada 1: $4,9 milhões <br>
2.	Temporada 2: $4,2 milhões<br>
3.	Temporada 3: $2,2 milhões<br>
4.	Temporada 4: $3,7 milhões<br>
 Isso mostram que a Temporada 1 é a mais lucrativa, enquanto a Temporada 3 apresenta o menor desempenho<br>


# Demografia 

- Os maiores usuarios, são **Registrados**, sendo 81,17%
- Os usuarios casuais são 18,83% 


## Sugestão de melhorias 

- foque nos horarios mais movimentados: deixe mais bicicletas disponiveis.
- faça um teste de ajuste de preço entre 10% a 15%, para ver a reação dos clientes.
- no caso da receita total, se houve um aumento de 10% a receita aumentará, isso se não houve comprometimento dos clientes.
- Usuarios registrados podem agir de forma mais positiva, em relação a mudança de preço, devido a frenquencia de uso, o que gera um estabilidade.
- Já os usuarios casuais, tente oferecer promoções para amenizar o aumento de preço.

  ## Dica para justificar o aumento
  
  Garanta que os usuários percebam o valor adicional, como melhorias no serviço (bicicletas novas, manutenção melhor, etc.).

