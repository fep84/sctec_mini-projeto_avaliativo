# Relatório e insights

## Objetivo e tratamento dos dados

Analisei 1.500 pedidos do arquivo `halloween_vendas.csv` para verificar a qualidade dos dados e observar sua distribuição por canal e período. Preservei os valores originais quando necessário e fiz os tratamentos no DataFrame, sem alterar o CSV.

Na coluna `categoria`, removi espaços excedentes, converti o texto para minúsculas e usei `re.sub` para retirar pontuação, mantendo letras sem acento e espaços. Categorias vazias ou que ficaram vazias após a limpeza receberam o valor “sem categoria”. No arquivo original, 18 categorias estavam vazias e 1.482 categorias não vazias foram alteradas.

Também validei os campos numéricos: 7 registros tinham problemas em `quantidade` e 12 em `preco_unitario`. Ao combinar as marcações, encontrei 19 pedidos afetados, sem contar um pedido mais de uma vez. Quatro datas de venda eram inválidas e permaneceram sem preenchimento. Não inventei valores para campos ausentes ou inválidos.

## Status e entregas

Encontrei 143 pedidos sem data de entrega: 109 estavam com status “Cancelado” e 34 com outro status. Portanto, a hipótese de que todo pedido sem data de entrega foi cancelado é falsa. Os 34 casos com outro status são contraexemplos; eles foram mantidos sem alteração de status ou preenchimento de data.

## Canais e períodos

Todos os 1.500 pedidos tinham um canal reconhecido: 666 foram feitos pela Web (44,4%), 551 em Loja física (36,7%) e 283 no Mercado (18,9%). A Web teve a maior contagem, mas isso representa quantidade de pedidos, não valor de receita.

Agrupei os pedidos por ano e mês, mantendo os anos separados. Foram consideradas 1.496 datas válidas; quatro registros foram excluídos por data ausente ou inválida. Outubro de 2025 teve a maior contagem, com 410 pedidos (27,4% dos pedidos com data válida).

## Limitações e conclusão

As contagens por canal e período incluem todos os status: 1.345 pedidos “Concluído”, 109 “Cancelado” e 46 “Devolvido”. Portanto, não representam apenas vendas concluídas nem valores de receita. Para analisar faturamento, seria necessário somar valores monetários e definir quais status considerar.

A limpeza tornou categorias e canais mais comparáveis, e as validações destacaram registros que merecem atenção. As descobertas descrevem apenas os dados analisados; não permitem afirmar as causas das diferenças entre canais ou períodos.
