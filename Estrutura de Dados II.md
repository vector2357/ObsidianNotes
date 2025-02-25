-- -

### Complexidade de Algoritmos


A complexidade de um algoritmo mede a quantidade de recursos computacionais necessários para sua execução, geralmente em termos de **TEMPO** e **ESPAÇO**. Essa análise é crucial para avaliar a eficiência de um algoritmo, especialmente quando lidamos com grandes volumes de dados.

#### Tipos de Complexidade

A complexidade de um algoritmo pode ser analisada sob dois principais aspectos:

1. <span style="color:rgb(146, 208, 80)">Complexidade de Tempo</span>

   Refere-se ao número de operações que um algoritmo executa em função do tamanho da entrada. Geralmente, representamos a complexidade de tempo com a **notação Big-O**, que descreve o crescimento da quantidade de operações em relação ao tamanho da entrada.

2. <span style="color:rgb(146, 208, 80)">Complexidade de Espaço</span>

   Refere-se à quantidade de memória adicional necessária para executar um algoritmo, além do espaço usado para armazenar a entrada.


#### Análise de Algoritmos

Analisar um algoritmo significa prever os recursos de que o algoritmo necessita. Ocasionalmente, recursos como memória, largura de banda de comunicação ou hardware de computador são a principal preocupação, porém mais frequentemente é o tempo de computação que desejamos medir.

Utilizaremos um exemplo de um algoritmo de <span style="color:rgb(255, 255, 0)">Ordenação por Inserção </span> e analisaremos o **tempo de execução** dele em função de um tamanho de entrada <span style="color:rgb(255, 192, 0)">n</span>. 

O **Tempo de Execução** de um algoritmo em determinada entrada é o número de operações primitivas ou “passos” executados.
É conveniente definir a noção de passo de modo que ela seja tão independente de máquina quanto possível. Por enquanto, vamos adotar a visão a seguir.
Uma quantidade de tempo constante é exigida para executar cada linha do nosso código. Uma linha pode demorar uma quantidade de tempo diferente de outra linha, mas consideraremos que cada execução da i-ésima linha leva um tempo ci, onde ci é uma constante.

> **EXEMPLO:**

```cpp
void insertionSort(int *V, int n) {            // custo  // vezes
    int i, j;                                  //  c1    // 1

    for(i=1; i<n; i++) {                       //  c2    // n
        int aux = V[i];                        //  c3    // n-1

        for(j=i-1; j>=0 && aux<V[j]; j--) {    //  c4    // (n+2)*(n-1)/2
            arr[j+1] = V[j];                   //  c5    // n * (n-1)/2
        }
        V[j+1] = aux;                          //  c6    // n-1
    }
}
```


Para calcular <span style="color:rgb(255, 255, 0)">T(n)</span>, o tempo de execução **(no pior caso)** de Insertion-Sort de uma entrada de **n** valores, somamos os produtos das colunas custo e vezes, obtendo

$$T(n) = c_1 + c_2.n + c_3.(n-1) + c_4\sum_{2}^{n}n + c_5\sum_{1}^{n-1}n + c_6.(n-1)$$


Se desenvolvermos e arranjarmos a função de forma que se deixe em evidência a variável **n** teremos:

$$T(n) = c_1 + c_2.n + c_3.(n-1) + c_4.\frac{(n+2)(n-1)}{2} + c_5.\frac{n(n-1)}{2} + c_6.(n-1)$$
$$T(n) = c_1 + c_2.n + c_3.n - c_3 + c_4.\frac{n^2}{2} + c_4.\frac{n}{2} - c_4 + c_5.\frac{n^2}{2} - c_5.\frac{n}{2} + c_6.n - c_6$$
$$ T(n) = n^2.(\frac{c_4}{2} + \frac{c_5}{2}) + n.(c_2 + c_3 + \frac{c_4}{2} - \frac{c_5}{2} + c_6) + (c_1 - c_3 - c_4 -c_6) $$


Uma vez desenvolvida, podemos substituir o conjunto de constantes em evidência por coeficientes genéricos, de forma que possamos trabalhar apenas com as variáveis.

$$ T(n) = a.n^2 + b.n + c $$

Dessa maneira chegamos a conclusão que a nossa função é quadrática, sendo assim, o nosso algoritmo de inserção no <span style="color:rgb(255, 0, 0)">PIOR CASO</span> cresce de maneira quadrática.


#### Notação Assintótica

Notação Assintótica é uma linguagem que nos permite analisar o tempo de execução de um algoritmo através da identificação de seu comportamento com o crescimento da entrada oferecida. Isso também é conhecido como taxa de crescimento do algoritmo.

##### <span style="color:rgb(146, 208, 80)">Notação O</span>

   A **notação O** limita assintoticamente uma função acima da função de Tempo de Execução do algoritmo $f(n)$.


![[Pasted image 20250217215200.png]]


Seja $f(n)$ a função de crescimento do tempo do algoritmo.

- Se existe uma função $g(n)$ e uma constante <span style="color:rgb(146, 208, 80)">c > 0</span>, tal que: 

$$0 \leq f(n) \leq c.g(n)$$

- A partir de  $n \geq n_o$ ,  então :

$$f(n) = O(g(n))$$


Se utilizarmos o exemplo do algoritmo **Insertion Sort**, cuja função de Tempo de Execução é  $T(n) = a.n^2 + b.n + c$.

Podemos considerar então que a função $g(n) = n^2$ é assintótica à $T(n)$ com **limite superior** uma vez que podemos multiplicar a função $g(n)$ de tal forma que ela seja maior do que $T(n)$ a partir de determinado ponto. Logo, $T(n) = O(g(n))$.

Podemos então definir a complexidade desse algoritmo no **pior caso**, <span style="color:rgb(146, 208, 80)">na notação O</span>, como sendo: 

$$O(n^2)$$


#### <span style="color:rgb(146, 208, 80)">Notação</span> $\Omega$ (Omega)

   A **notação $\Omega$** nos dá um limite assintótico inferior à função de crescimentos do algoritmo


![[Pasted image 20250222225237.png]]


Seja $f(n)$ a função de crescimento do **tempo** do algoritmo.

- Se existe uma função $g(n)$ e uma constante <span style="color:rgb(146, 208, 80)">c > 0</span>, tal que:

$$f(n) > c.g(n)$$

- A partir de $n \geq n_o$ , então : 

$$f(n)=\Omega(g(n))$$


Se utilizarmos o exemplo do algoritmo **Insertion Sort**, cuja função de Tempo de Execução é  $T(n) = a.n^2 + b.n + c$.

Podemos considerar então que a função $g(n) = n^2$ é assintótica à $T(n)$ com **limite inferior** uma vez que podemos multiplicar a função $g(n)$ de tal forma que ela seja menor do que $T(n)$ a partir de determinado ponto. Logo, $T(n) = \Omega(g(n))$.

Podemos então definir a complexidade desse algoritmo no **pior caso**, <span style="color:rgb(146, 208, 80)">na notação Omega</span> $(\Omega)$, como sendo: 

$$\Omega(n^2)$$


#### <span style="color:rgb(146, 208, 80)">Notação</span> $\Theta$ (Theta)

   A **notação** $\Theta$ nos dá um limite <span style="color:rgb(255, 255, 0)">inferior</span> e <span style="color:rgb(0, 176, 240)">superior</span> à função de crescimento do algoritmo


![[Pasted image 20250224205805.png]]


Seja $f(n)$ a função de crescimento de **tempo** do algoritmo.

- Se existe uma função $g(n)$ e duas constantes  $c_1, c_2 > 0$ , tal que:

$$c_1.g(n)<f(n)<c_2.g(n)$$

- A partir de $n\geq n_o$ , então :

$$f(n) = \Theta (g(n))$$


Se utilizarmos o exemplo do algoritmo **Insertion Sort**, cuja função de Tempo de Execução é  $T(n) = a.n^2 + b.n + c$.

Podemos considerar então que a função $g(n) = n^2$ é assintótica à $T(n)$ com **limite inferior** e **limite superior**, uma vez que podemos multiplicar a função $g(n)$ de tal forma que ela seja menor e também de tal forma que ela seja maior do que $T(n)$ a partir de determinado ponto. Logo, $T(n) = \Theta(g(n))$.

Podemos então definir a complexidade desse algoritmo no **pior caso**, <span style="color:rgb(146, 208, 80)">na notação Theta</span> $(\Theta)$, como sendo: 

$$\Theta(n^2)$$
