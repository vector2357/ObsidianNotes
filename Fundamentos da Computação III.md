-- -

### Matrizes e Vetores


>**<span style="color:rgb(255, 255, 0)">Introdução</span>**

   Uma matriz é um conjunto de elementos dispostos em linhas e colunas. Definida por:

   $$
   A = [a_{ij}]_{m\times n} =
   \begin{bmatrix}
   a_{11} & a_{12} & ... & a_{1n} \\
   a_{21} & a_{22} & ... & a_{2n} \\
   .. & .. &  & .. \\
   a_{m1} & a_{m2} & ... & a_{mn}
   \end{bmatrix}$$
   
   - **Exemplo :**

$$A_{2\times3}=
\begin{bmatrix}
1 & 0 & 2 \\
3 & 1 & 4 
\end{bmatrix}$$
	$a_{11} = 1$          $a_{21}=3$
	$a_{12} = 0$          $a_{22}=1$
	$a_{13}=2$          $a_{23}=4$


<span style="color:rgb(146, 208, 80)">Definição:</span>  duas matrizes $A_{m\times n} = [a_{ij}]_{m\times n}$  e  $B_{r\times s} = [b_{ij}]_{r\times s}$  são iguais, $A=B$, se elas tem o mesmo número de linhas $(m=r)$ e colunas $(n=s)$ , e todos os elementos correspondentes são iguais $(a_{ij}=b_{ij})$.


$$
   A_{3\times2} =
   \begin{bmatrix}
   \log 1 & 0 \\
   4 & 2 \\
   sen30^{\circ} & 1
   \end{bmatrix}$$
   $$
   B_{3\times2} =
   \begin{bmatrix}
   0 & 0 \\
   4 & 2 \\
   \frac{1}{2} & 1
   \end{bmatrix}$$
   Portanto,
    $[A=B]$
-- -

#### Tipos de Matrizes


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(0, 176, 240)">quadrada</span> é aquela cujo o número de linhas é igual o número de colunas $(m=n)$.

> **Exemplo:**

$$A_{2\times2} =
\begin{bmatrix}
1 & 0 \\
2 & 4
\end{bmatrix}
= A_2 = A$$
$$A = \begin{bmatrix} 1 \end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(192, 0, 0)">nula</span> é aquela em que $a_{ij}=0$, para todo $i$ e $j$ .

> **Exemplo**

$$A = \begin{bmatrix}
0 & 0 \\
0 & 0
\end{bmatrix}=O$$$$ B=\begin{bmatrix}0\end{bmatrix}=O$$


<span style="color:rgb(146, 208, 80)">Definição: </span> Matriz <span style="color:rgb(255, 255, 0)">coluna</span> é aquela que possui uma única coluna $(n=1)$.

> **Exemplo**

$$A_{3\times1} = \begin{bmatrix}
0 \\
1 \\
2
\end{bmatrix}, B=\begin{bmatrix}
x \\
y \\
z
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(0, 176, 240)">linha</span> é aquela formada por uma única linha $(m=1)$.

>**Exemplo**

$$A_{1\times3}=
\begin{bmatrix}
0 & 1 & 4
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(192, 0, 0)">diagonal</span> é uma matriz **quadrada** $(m=n)$ onde $a_{ij}=0$, para $i \neq j$, isto é, os elementos que não estão na diagonal são nulos.

> **Exemplo**

$$A=\begin{bmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 4
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(255, 255, 0)">identidade</span> quadrada é aquela em que $a_{ii}=1$ e $a_{ij}=0$, para $i \neq j$.

> **Exemplo**

$$I = \begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}$$$$I=\begin{bmatrix}1\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(0, 176, 240)">triangular superior</span> é uma matriz quadrada onde todos os elementos abaixo da diagonal são nulos, isto é, $m=n$ e $a_{ij}=0$  para  $i>j$ .

> **Exemplo**

$$A=\begin{bmatrix}
4 & 3 & 1 \\
0 & 2 & 1 \\
0 & 0 & 2
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(192, 0, 0)">triangular inferior</span> é aquela em que os elementos acima da diagonal são nulos, isto é, $m=n$ e $a_{ij}=0$  para  $i<j$ .

> **Exemplo**

$$A=\begin{bmatrix}
1 & 0 & 0 \\
2 & 4 & 0 \\
3 & 1 & 2
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  Matriz <span style="color:rgb(255, 255, 0)">simétrica</span> é aquela onde  $m=n$  e  $a_{ij}=a_{ji}$ .

> **Exemplo**

$$A=\begin{bmatrix}
1 & 0 & 1 \\
0 & 2 & 2 \\
1 & 2 & 4
\end{bmatrix}$$
$$B=\begin{bmatrix}
1 & 4 \\
4 & 2
\end{bmatrix}$$


<span style="color:rgb(146, 208, 80)">Definição:</span>  <span style="color:rgb(0, 176, 240)">Adição de matrizes</span> é uma operação que consiste em adicionar os elementos correspondentes de duas matrizes de **mesma ordem**. Dada duas matrizes $A$ e $B$  de dimensões $m\times n$ , a soma resulta em uma nova matriz $C$ , também de dimensões $m\times n$ , onde cada elemento $c_{ij}$ é obtido pela adição dos elementos correspondentes das matrizes $A$ e $B$ ($c_{ij} = a_{ij} + b_{ij}$).

> **Exemplo**

$$A=\begin{bmatrix}
1 & 3 \\
4 & 5
\end{bmatrix}, B=\begin{bmatrix}
1 & 3 \\
5 & 1
\end{bmatrix}$$
$$A+B=\begin{bmatrix}
1 & 3 \\
4 & 5
\end{bmatrix}+\begin{bmatrix}
1 & 3 \\
5 & 1
\end{bmatrix}$$
$$=\begin{bmatrix}
2 & 6 \\
9 & 6
\end{bmatrix}$$
$$A+B=[a_{ij}+b_{ij}]_{m\times n}$$

##### Propriedades Adição


Dada as matrizes $A$, $B$ e $C$ de mesma ordem $m\times n$ , temos:

1. $A+B = B+A$                               <span style="color:rgb(0, 176, 240)">( Comutativa )</span> 
2. $A+(B+C) = (A+B) + C$           <span style="color:rgb(146, 208, 80)">( Associativa )</span> 
3. $A+0=A$                                       <span style="color:rgb(192, 0, 0)">( elemento neutro da adição )</span> 


##### Multiplicação de uma Matriz por um escalar


<span style="color:rgb(146, 208, 80)">Definição:</span>  seja $A=[a_{ij}]_{m\times n}$  e  $k$  um escalar, então definimos uma nova matriz
$$k.A=[k.a_{ij}]_{m\times n}$$

> **Exemplo**

$$3.\begin{bmatrix}
2 & 4 \\
1 & 0
\end{bmatrix} = \begin{bmatrix}
6 & 12 \\
3 & 0
\end{bmatrix}$$


<span style="color:rgb(0, 176, 240)">Propriedades:</span>  Dada as matrizes $A$ e $B$ de mesma ordem $m\times n$ e escalares: $k, k_1, k_2$ , temos:

1. $k.(A+B) = k.A +k.B$
2. $(k_1+k_2).A = k_1.A + k_2.B$
3. $k_1.(k_2.A) = (k_1.k_2).A = k_2.(k_1.A)$
4. $0.A = 0$  ->  (matriz nula)