-- -

### Max e Min Heap


- <span style="color:rgb(146, 208, 80)">Max Heap</span>

  Se P é um nó pai de C, então a chave (valor) de P é **MAIOR** ou igual a chave de C. Esta é utilizada para ordenação por Heap.

- <span style="color:rgb(146, 208, 80)">Min Heap</span>

  Se P é um nó pai de C, então a chave (valor) de P é **MENOR** ou igual a chave de C.


### Implementação HeapSort em C++


A implementação do HeapSort se baseia em trocar o elemento raiz da árvore pelo atual último elemento, de forma que o vetor vá sendo ordenado a partir da organização primeiramente dos maiores, no final do vetor. É válido destacar que para a representação do vetor como uma árvore consideramos a seguinte regra :

	i == pai
	2*i+1 == filho da esquerda
	2*i+2 == filho da direita

Para isso usaremos o conceito de [[Recursão]] que nos permitirá organizar a árvore de forma que ela sempre se torne uma heap.

Estruturando o problema em passos :

- <span style="color:rgb(146, 208, 80)">Tornando o vetor uma Heap</span>

  Inicialmente o vetor não necessariamente será uma Max Heap, ou seja, não atenderá as condições para ser considerado uma Max Heap. Dessa forma o vetor inicialmente precisará passar pelo processo que torna ele uma Heap. Para isso é necessário sempre ajustar o **nó pai** a medida que for necessário, e o filho que for trocado será por onde devemos seguir o percurso até chegar em uma folha ou aquele percurso estar "heapado". 

  Inicialmente esse processo é necessário apenas para nós pais, dessa forma devemos iniciar pelo último nó pai que é dado por  $(\frac{n}{2} - 1)$ .

- <span style="color:rgb(146, 208, 80)">Troca a raiz pelo último e reduz a Árvore</span>

  A partir do momento que ela se tornar uma Max Heap, podemos garantir que o maior elemento da Árvore estará na raiz, sendo assim, trocamos ele pelo último elemento do vetor, e reduzimos o tamanho do vetor e a posição o elemento no qual trocaremos da próxima vez.

- <span style="color:rgb(146, 208, 80)">Recursão, tornando Heap novamente</span>

  Após o segundo passo ser finalizado, a árvore será modificada na raiz, de tal forma que precisamos novamente fazer o processo do início do programa, onde tornamos a árvore uma Max Heap, porém apenas para o percurso modificado, iniciando na raiz, e após isso voltamos para o segundo passo e fazemos esse processo até que sobre apenas 1 elemento no vetor e ele esteja totalmente ordenado.


#### Método HeapSort

```cpp
void HeapSort(int *V, int N) {
	BuildHeap(V, N);
	
	for(; N>1; N--) {
		swap(V[0], V[N-1]);
		Heapify(V, 0, N);
	}
}
```

#### Método BuildHeap

```cpp
void BuildHeap(int *V, int N) {
	for(int i=N/2-1; i>=0; i--) {
		Heapify(V, i, N);
	}
}
```

#### Método Heapify

```cpp
void Heapify(int *V, int i, int N) {
	int maior = i;
	int l = 2*i+1;
	int r = 2*i+2;
	
	if(l<N && V[l]>V[maior]) {
		maior = l;
	}
	if(r<N && V[r]>V[maior]) {
		maior = r;
	}
	
	if(maior != i) {
		swap(V[maior], V[i]);
		Heapify(V, maior, N);
	}
}
```
