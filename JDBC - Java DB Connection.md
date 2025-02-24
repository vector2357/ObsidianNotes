---

---

Canvas - [[JDBC (canvas).canvas|JDBC (canvas)]]

---
## Classes Principais

- Connection
- Properties
- DriverManager
- Statement
- ResultSet


	Classes para gerar conexão (Connection e DriverManager), capturar propriedade (Properties), estruturar comandos SQL (Statement) e gerar resultados de queries em forma de tabela (ResultSet).

##### Métodos Statement:

```java
// Statement st
// ResultSet rs

// queries
rs = st.executeQuery("SELECT * FROM department");

// finalizar statement
st.close();
```


##### Métodos ResultSet:

```java
// ResultSet rs

// move para a posição 1, se houver
rs.first();

// move para a posição 0
rs.beforeFirst();

// move para o próximo, retorna false se já estiver no último
rs.next();

// move para a posição dada no parâmetro
rs.absolute(1);

// finalizar ResultSet
rs.close();
```

##### Métodos Connection:

```java
// Connection conn
// PreparedStatement st

// preparação de comando SQL com argumentos
st = conn.prepareStatement(
		"INSERT INTO client "
		+ "(Name, Qtd) "
		+ "VALUES "
		+ "(?, ?)",
		Statement.RETURN_GENERATED_KEYS);

// finalizar prepared statement
st.close();
```

##### Métodos PreparedStatement:

 PreparedStatement é uma classe que funciona como se fosse um Statement de maneira que permita uma estruturação de queries com parâmetros.
 
```java
// PreparedStatement st

// ids de linhas novas inseridas
rs = st.getGeneratedKeys();

// executa comando de inserção e gera linhas afetadas
int rows = st.executeUpdate();

// seta dado para argumentos
st.setString(1, "Torugo");
st.setInt(2, 10);
```

---
#### Transações

> transações são operações em banco de dados que exigem o cumprimento de 4 pilares ACID (Atomicity, Consistency, Isolation, Durability).

```java
// método que seta como automático ou não a transação
setAutoCommit(false);

// comita as operações efetuadas
commit();

// retorna ao estado anterior às operações
rollback();
```
