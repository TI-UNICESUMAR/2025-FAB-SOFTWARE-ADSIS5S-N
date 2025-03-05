Revisão do Diagrama de Classe

Entregar no Forms abaixo um descritivo sobre a Regra de Negócio/Fluxo de uso do sistema.

[Forms-Diagrama Classe](https://forms.gle/768CtWAnytDtw9DY8)

Exemplos de Descritivo:

Exemplo 01:
```
Domain:
- Produto: Classe com os atributos X, Y e Z. Onde se faz necessário uma Categoria para existencia, logo não é possível existir um Produto sem uma Categoria;
- Categoria: Classe com os atributos X, Y e Z. Uma Categoria pode existir sem um Produto.
- Pedido: Classe com os atributos X, Y e Z. Um pedido só pode existir com um Cliente o fazendo. Não é possível fazer um pedido sem Produtos. O Pedido é identificado pelo Campo X.
- Cliente: Classe com os atributos X, Y e Z. O cliente pode fazer quantos pedidos quiser...
```

Exemplo 02:
```
O Pedido contém 1 ou mais Produtos, possui um cliente obrigatoriamente. Um produto sempre terá uma categoria, porém uma categoria pode existir sem um produto. O Cliente possui os atributos...
```

Lembrando que o Descritivo é para facilitar a correção do Diagrama, não é definitivo. Então de acordo com as necessidades do Projeto, o descritivo (regra de negócio) pode mudar.
