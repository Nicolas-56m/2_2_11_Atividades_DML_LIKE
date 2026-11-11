# Atividades_DML_LIKE (o arquivo da atividade está na pasta logo acima!)

## Instrução 1
```SQL
USE vendas_informatica;

SELECT * FROM produto WHERE nome_produto LIKE "D%";
```

## Instrução 2
```SQL
USE vendas_informatica;

SELECT nome_produto, marca, estoque FROM produto WHERE nome_produto LIKE "%E";
```

## Instrução 3
```SQL
USE vendas_informatica;

SELECT nome_produto, marca, estoque, preco_unitario FROM produto WHERE nome_produto LIKE "%Gamer%";
```

## Instrução 4
```SQL
USE vendas_informatica;

SELECT * FROM cliente WHERE nome_cliente LIKE "%Barbosa%";
```

## Instrução 5
```SQL
USE vendas_informatica;

SELECT 
    cliente.nome_cliente, 
    venda.data_venda, 
    produto.preco_unitario, 
    venda.forma_pagamento 
FROM cliente 
INNER JOIN venda ON cliente.id_cliente = venda.id_cliente 
INNER JOIN produto ON venda.id_produto = produto.id_produto 
WHERE cliente.nome_cliente LIKE "C%";
```

## Instrução 6
```SQL
USE vendas_informatica;

SELECT 
    produto.nome_produto, 
    produto.preco_unitario, 
    venda.id_venda, 
    venda.forma_pagamento 
FROM produto
INNER JOIN venda ON produto.id_produto = venda.id_produto 
WHERE venda.forma_pagamento IN ("PIX", "Boleto")
  AND produto.nome_produto LIKE '%Polegada%';
```

## Instrução 7
```SQL
USE vendas_informatica;

SELECT 
    produto.nome_produto,
    cliente.nome_cliente,
    venda.desconto_percentual,
    venda.forma_pagamento
FROM venda
INNER JOIN produto ON venda.id_produto = produto.id_produto
INNER JOIN cliente ON venda.id_cliente = cliente.id_cliente
WHERE produto.nome_produto LIKE "%Placa%"
   OR produto.nome_produto LIKE "%Notebook%"
   OR cliente.nome_cliente LIKE "%Ana%"
ORDER BY venda.status_venda ASC;
```
