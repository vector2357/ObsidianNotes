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


#### Análise Merge Sort

O algoritmo de Mergesort usa a estratégia de [[Divide and Conquer]] para ordenar um dado vetor.

Nele, ordenamos o vetor de forma que dividimos ao meio toda vez até que se sobre apenas um elemento. Quando possui 1 elemento, o vetor pode ser considerado ordenado, dessa forma a única coisa que precisamos fazer com 2 lados do vetor ordenados, é mesclar de forma ordenada ambas as partes.

Faremos isso a partir de uma [[Recursão]] :

- <span style="color:rgb(146, 208, 80)">Base :</span>
  Caso o início não seja maior ou igual ao fim, ou seja, o vetor tendo apenas 1 elemento, ele estará ordenado. `if(i >= f) return;`

- <span style="color:rgb(146, 208, 80)">Hipótese :</span>
  Vamos assumir que conseguimos ordenar o vetor de tamanho $n/2$ dividindo ele em duas partes e ordenando cada metade.

- <span style="color:rgb(146, 208, 80)">Indução :</span>
  Se conseguimos ordenar metade do vetor, também conseguimos ordenar o vetor inteiro, mesclando-o.


Com essas definições para a recursão, podemos então implementar o algoritmo de ordenação por mesclagem :


```cpp
void Merge(int *V, int ini, int m, int fim) {
    int tam = fim-ini+1, i, j, k;
    int A[tam];

    for(i=ini, j=m+1, k=0; i<=m && j<=fim; k++) {
        if(V[i] <= V[j]) {
            A[k] = V[i];
            i++;
        }
        else {
            A[k] = V[j];
            j++;
        }
    }
  
    for(; i<=m; i++, k++) {
        A[k] = V[i];
    }
  
    for(; j<=fim; j++, k++) {
        A[k] = V[j];
    }
  
    for(i=0, j=ini; i<tam; i++, j++) {
        V[j] = A[i];
    }
}

void MergeSort(int *V, int i, int f) {
    if(i < f) {
        int m = (i+f)/2;
        MergeSort(V, i, m);
        MergeSort(V, m+1, f);
        Merge(V, i, m, f);
    }
}
```


**Função de Recorrência**

$$f(n)\quad \left\{\begin{array}{l}
\;\Theta(1)\quad \quad \quad \quad \quad \quad \quad \quad n\leq1 \\
\;2\times f(n/2) + \Theta(n)\quad \quad n>1
\end{array}\right.$$


Para descobrirmos a complexidade do algoritmo Mergesort, podemos calcular a partir da função de recorrência. Dessa forma :

$$f(2) = 2.\Theta(1)\; + \; \Theta(2)\; =\; 2.\Theta(2)$$
$$f(4) = 2.\Theta(4)\; + \; \Theta(4)\; = \; 3.\Theta(4)$$
$$f(8) = 2.\Theta(12) \; + \; \Theta(8) \; = \; 4.\Theta(8)$$

Então, podemos concluir :

$$(\log_2 N) + 1 \; \times \; \Theta(N)$$
$$\Theta(N\times\log_2 N)$$


### Árvores


Árvores é um [[Tipo Abstrato de Dados - TAD]] , que é basicamente um conjunto de <span style="color:rgb(146, 208, 80)">Nós</span>, os nós são conectados por <span style="color:rgb(255, 255, 0)">Arestas</span>. Cada nó contém um valor ou dados e pode não ter um nó filho.

O primeiro **nó** da árvore é chamado de <span style="color:rgb(0, 176, 240)">Raiz</span>. Se este nó raiz é conectado por outro nó, a raiz é então um **nó pai** e o nó conectado é um **nó filho**.

As <span style="color:rgb(146, 208, 80)">Folhas</span> são os últimos nós de uma árvore. Elas são os nós **sem filhos**. Como árvores reais, temos a raiz, os ramos e, finalmente, as folhas.

Outros conceitos importantes a serem entendidos são **Altura** e **Profundidade**.
A <span style="color:rgb(255, 255, 0)">Altura</span> de uma **árvore** é o tamanho do caminho **mais longo** até uma **folha**.
A <span style="color:rgb(0, 176, 240)">Profundidade</span> de um **nó** é o tamanho do caminho percorrido do nó até a **raiz**.

**Árvores** são representadas normalmente desta forma :


![[Pasted image 20250303164558.png]]


### Árvores Binárias


Uma árvore binária é uma estrutura de dados em árvore na qual cada nó tem, no máximo, dois filhos, que são referidos como o **filho da esquerda** e o **filho da direita**.

Introduziremos o conceito de Árvore Binária a partir do entendimento de uma **Heap** e também com a implementação de uma HeapSort.

Heap é uma estrutura de dados especializada, baseada em árvore, de maneira estática (implementada em vetor), que satisfaz as propriedade de uma heap :

- <span style="color:rgb(146, 208, 80)">Max Heap</span>

  Se P é um nó pai de C, então a chave (valor) de P é **MAIOR** ou igual a chave de C.

- <span style="color:rgb(146, 208, 80)">Min Heap</span>

  Se P é um nó pai de C, então a chave (valor) de P é **MENOR** ou igual a chave de C.


O método de ordenação **HeapSort** se utiliza do conceito de **Max Heap**. Aqui é possível encontrar a implementação e análise do [[Heap Sort]].

##### Cálculo Número de Elementos Max Árvore grau K

Seja $K$ o **grau da árvore** (número de filhos máximos por nó), e  $h$  a profundidade da árvore, temos :

$$\frac{K^{h+1}-1}{K-1}$$

Ou seja, em uma árvore binária, o número máximo de elementos existentes até uma profundidade 4, por exemplo, seria de :

$$\frac{2^{4+1}-1}{2-1}\;=\;31$$

A complexidade de uma árvore genérica de grau $K$ é dado por :

$$\Theta(log_k\;N)$$


#### Árvores de Busca Binária

Árvores de Busca Binária (<span style="color:rgb(146, 208, 80)">Binary Search Tree - BST</span>), são árvores binárias, ou seja, cada nó tem no **máximo** 2 filhos, que é utilizada para efetuar buscas eficazes, de tal maneira que a busca é feita por alguma chave de um certo tipo específico.

Desta forma, cada nó da árvore possui um valor chave, outros dados à serem buscado, e uma referência para seus possíveis 2 filhos.


```cpp
struct Node {
	int key;
	Thing regs;
	Node *left;
	Node *right;
}
```

A regra a ser respeitada em uma BST, é que, além de cada nó possuir no máximo 2 filhos, a chave do **nó pai P** sempre será **maior ou igual** à chave de cada nó da subárvore esquerda de P e **menor ou igual** à chave de cada nó da subárvore direita de P.

Dessa forma podemos ter :


![[Pasted image 20250303223215.png]]


Árvores de busca binária são muito eficientes visto que qualquer operação (inserção, remoção, busca, percurso), tem complexidade no melhor caso de  $\Theta(\log_2 N)$ , isso ocorre devido à altura de uma árvore que será no melhor caso $\log_2 N$.

Porém, no pior caso, as operações de uma árvore pode ter  $\Theta(N)$ , tornando-se uma [[Lista]]. Para resolver isso, é importante que a árvore de busca binária esteja balanceada; veremos isso no futuro.

##### Classe Node

Uma árvore de busca binária é formada por vários Nós (ou Nodes). Cada Nó desse possui uma **chave**, o **objeto** pelo qual deseja-se buscar e dois [[Ponteiros]] que referenciam os **dois filhos** do Nó.

Dessa forma, podemos representar a classe "Node" com os seguintes atributos :

```cpp
class Node {
private:
	int K;
	Thing D;
	Node* Left;
	Node* Right;
};
```


Uma vez tido os atributos da classe Node, devemos definir um construtor que inicie os valores de um Nó quando for criado.

```cpp
class Node {
private:
	int K;
	Thing D;
	Node* Left;
	Node* Right;
	
public:
	Node(int K, Thing D) {
		this->K = K;
		this->D = D;
		this->Left = NULL;
		this->Right = NULL;
	}
};
```


Dessa forma, toda vez que um novo Nó for criado, será atribuído os valores da chave e objeto e os filhos são inicializados com valor `NULL`.

##### Classe BBTree

Na classe principal que define a nossa árvore terá métodos de **inserção, busca, remoção, percurso**, entre outros. Quanto ao atributo, a árvore necessita da informação apenas da raiz (root) que é uma referência para um Node.

```cpp
// INTERFACE \\

class BBTree {
	private: Node* Root;
	
	public: BBTree();
};
```


Para a implementação do construtor padrão precisamos inicializar o Node raiz como `NULL`.

```cpp
// BBTREE.CPP \\

BBTree::BBTree() {
	Root = NULL;
}
```


A seguir serão implementados vários métodos utilizados em uma **árvore de busca binária**. Começaremos com métodos de **percurso em árvore**.

##### Percurso

O percurso em árvore refere-se a percorrer a BST de dada maneira. Existem 3 principais tipos de percurso em árvore de busca binária, sendo eles:

	- InOrder   (left/root/right)
	
	- PreOrder  (root/left/right)
	
	- PosOrder  (left/right/root)


Seguiremos com as implementações de cada um desses percursos.

##### Método InOrder

O percurso InOrder é dado de maneira ordenada na árvore de busca binária, de forma que o caminho percorrido segue da seguinte forma: `left/root/right`.

Para percorrer, utilizaremos o conceito de [[Recursão]].

- <span style="color:rgb(146, 208, 80)">Base :</span>
  Se é `NULL`, faz nada.

- <span style="color:rgb(146, 208, 80)">Hipótese :</span>
  Suponha que eu saiba percorrer qualquer subárvore (esquerda e direita) se não for `NULL`.

- <span style="color:rgb(146, 208, 80)">Indução :</span>
  Se não for `NULL` percorre a subárvore esquerda, visita o nó pai e por fim, percorre a subárvore direita.


Para a implementação, faremos 2 métodos: RInOrder e InOrder. Um ficará responsável pela implementação da Recursão, enquanto o outro fará a chamada iniciando da **raiz**.

```cpp
// INTERFACE \\

class BBTree {
	private: Node* Root;
	
	public: BBTree();
	private: static void RInOrder(Node* R);
	public: void InOrder();
};
```

```cpp
// BBTREE.CPP \\

void BBTree::RInOrder(Node* R) {
	if(R) {
		BBTree::RInOrder(R->Left);
		cout << R->Key << " ";
		BBTree::RInOrder(R->Right);
	}
}

void BBTree::InOrder() {
	BBTree::RInOrder(Root);
}
```


##### Métodos PreOrder e PosOrder

Esses métodos seguem a lógica de implementação semelhante ao **InOrder** mas com regra de percurso diferente, sendo o PreOrder `(root/left/right)` e o PosOrder `(left/right/root)`.

```cpp
// INTERFACE \\

class BBTree {
	private: Node* Root;
	
	public: BBTree();
	private: static void RInOrder(Node* R);
	public: void InOrder();
	private: static void RPreOrder(Node* R);
	public: void PreOrder();
	private: static void RPosOrder(Node* R);
	public: void PosOrder();
};
```

```cpp
// BBTREE.CPP \\

void BBTree::RPreOrder(Node* R) {
	if(R) {
		cout << R->Key << " ";
		BBTree::RPreOrder(R->Left);
		BBTree::RPreOrder(R->Right);
	}
}

void BBTree::PreOrder() {
	BBTree::RPreOrder(Root);
}

void BBTree::RPosOrder(Node* R) {
	if(R) {
		BBTree::RPosOrder(R->Left);
		BBTree::RPosOrder(R->Right);
		cout << R->Key << " ";
	}
}

void BBTree::PosOrder() {
	BBTree::RPosOrder(Root);
}
```


##### Método Search

Método utilizado para buscar uma chave `K` na árvore de forma recursiva. A lógica do método consiste em buscar um nodo e retornar ao mundo externo um dado do tipo `Thing*`, ou seja, um **ponteiro** para o dado (primitivo ou não) que possui dentro do nosso nodo.

Estruturação da recursão utilizada no método:

- <span style="color:rgb(146, 208, 80)">Base :</span>
  Se a raiz da subárvore atual é `NULL` ou possui a chave igual ao `K` que estamos buscando, retornamos essa raiz.

- <span style="color:rgb(146, 208, 80)">Hipótese :</span>
  Suponha que eu saiba percorrer qualquer subárvore (esquerda e direita) se não for `NULL`.

- <span style="color:rgb(146, 208, 80)">Indução :</span>
  Percorre a subárvore esquerda caso `K < R->Key`. Percorre a subárvore direita caso contrário.


Dessa forma, nossa classe **BBTree** ficará da seguinte forma:

```cpp
// INTERFACE \\

class BBTree {
	private: Node* Root;
	
	public: BBTree();
	private: static void RInOrder(Node* R);
	public: void InOrder();
	private: static void RPreOrder(Node* R);
	public: void PreOrder();
	private: static void RPosOrder(Node* R);
	public: void PosOrder();
	private: static Node* RSearch(Node* R, int K);
	public: Thing* Search(int K);
};
```

Percebe-se que incrementamos 2 métodos, um privado (e estático, por ser recursivo) e outro público que poderá ser utilizado pelo mundo externo.
Implementação :

```cpp
// BBTREE.CPP \\

Node* BBTree::RSearch(Node* R, int K) {
	if(!R || R->Key == K) {
		return R;
	}
	// Não é nulo e não é ele
	
	if(K < R->Key) {
		return BBTree::RSearch(R->Left, K);
	}
	// Só pode estar à direita
	return BBTree::RSearch(R->Right, K);
}

Thing* BBTree::Search(int K) {
	Thing* T = NULL;
	Node* N = BBTree::RSearch(Root, K);
	
	if(N) {
		T = new Thing;
		*T = N->D;
	}
	return T;
}
```
