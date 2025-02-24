
 Para cada entidade, haverá um objeto responsável por fazer acesso a dados relacionado a esta **entidade**. Por exemplo:

- Cliente:  **ClienteDAO**
- Produto:  **ProdutoDAO**
- Pedido:  **PedidoDAO**

>Cada DAO será definido por uma interface.

>A injeção de dependência pode ser feita por meio do padrão de projeto Factory