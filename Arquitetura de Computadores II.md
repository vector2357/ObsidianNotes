-- -

### Organização de um Computador


Alguns dos principais componentes em uma computador são a **CPU, Memória e Barramentos.**

![[Pasted image 20250215205359.png]]


O processador é composto por outros importantes componentes:

- Unidade de Controle
- Registradores
- ULA/ALU (Unidade de Lógica e Aritmética)


O processador pode receber e entregar dados para a memória principal (RAM) e recebe as instruções que estão já armazenadas na memória.

Essas instruções mudam a depender da arquitetura do processador que pode geralmente ser **RISC (Reduced Instruction Set Computer) ou CISC (Complex Instruction Set Computer).**

Essas instruções possuem implementações que se beneficiam da técnica de **Microprogramação** que consiste na implementação de instruções a partir de outras instruções mais básicas a partir de sinais de controle que ajudam a modificar a lógica de cada instrução.

Um exemplo disso são instruções como **SUB, MUL E DIV** que podem ser realizadas a partir de diferentes sinais de controle em um conjunto de instruções **ADD.**
Sendo assim, instruções mais básicas podem ser programadas de forma que possam também realizar instruções mais complexas, o que reduz a escala de um processador.

#### Data Path

> fluxo de execução de instruções dentro de um processador
> (Fluxo) -> múltiplas instruções de modo sequencial


#### Tipos de Instruções

- <span style="color:rgb(0, 176, 80)">Aritmética e Lógica</span>                 **(ADD, SUB, DIV, OR, AND, ...)**
- <span style="color:rgb(0, 176, 240)">Acesso a Memória</span>                   **(LOAD, STORE)**
- <span style="color:rgb(255, 192, 0)">Desvios</span>                                    **(JNZ, JE, JG, JNA, ...)**


### Hierarquia de Memória


Existem diferentes níveis de memória em um computador que assumem funções diferentes e possuem capacidade, velocidade e valor de mercado diferente uma das outras. Isso tudo é definido em arquitetura por uma hierarquia de memória:

![[Pasted image 20250215212202.png]]


A medida que se vai subindo ao topo da pirâmide a capacidade de armazenamento diminui, porém a velocidade aumenta, de forma que dados processados na CPU "conversam" diretamente com memórias mais velozes como as do topo da hierarquia.

Registradores são usados para armazenar dados temporários durante a execução do programa atual do processador, Cache é utilizada para obtenção de dados frequentes, de forma que o processador possa carregar dados de maneira mais veloz do que acessando diretamente a memória principal.


### Data Path e Instruções MIPS


#### 1. <span style="color:rgb(146, 208, 80)">Aritméticas e Lógicas</span> 


Exemplos: **(ADD, SUB, MUL, DIV, AND, OR)**.


| <span style="color:rgb(0, 176, 240)">OPCODE</span> | <span style="color:rgb(255, 255, 0)">REG (dst)</span> | <span style="color:rgb(146, 208, 80)">REG (op1)</span> | <span style="color:rgb(146, 208, 80)">REG (op2)</span> |
| :------------------------------------------------: | :---------------------------------------------------: | :----------------------------------------------------: | :----------------------------------------------------: |
|                                                    |                                                       |                                                        |                                                        |
|                        ADD                         |                          R3                           |                           R1                           |                           R2                           |

Em uma linguagem de alto nível como na linguagem **C**, essa operação exemplificada anteriormente se equivaleria à:

	R3 = R1 + R2;


![[Pasted image 20250217232840.png]]


#### 2. <span style="color:rgb(0, 176, 240)">Acesso a Memória</span>

- **LOAD**  
- **STORE**

Fluxo das instruções de acesso a memória:

	LOAD  [ENDEREÇO]  ->  REG
	REG  ->  STORE  [ENDEREÇO]

**ENDEREÇO :** <span style="color:rgb(255, 255, 0)">BASE</span> + <span style="color:rgb(146, 208, 80)">OFFSET</span> 

> EXEMPLO

	EBP + 4


| <span style="color:rgb(0, 176, 240)">OPCODE</span> | <span style="color:rgb(255, 255, 0)">REG (dst)</span> | <span style="color:rgb(146, 208, 80)">REG (base)</span> | <span style="color:rgb(146, 208, 80)">OFFSET/CONST</span> |
| :------------------------------------------------: | :---------------------------------------------------: | :-----------------------------------------------------: | :-------------------------------------------------------: |
|                                                    |                                                       |                                                         |                                                           |
|                        LOAD                        |                          R1                           |                           R2                            |                            16                             |
|                       STORE                        |                          R1                           |                           R2                            |                            24                             |

Em uma linguagem de alto nível como na linguagem **C**, essa operação exemplificada anteriormente poderia equivaler à:

```c
char nome[20];

char x = *(nome + 4);   // nesse caso o nome seria nossa base
                        // e o valor 4 o nosso offset para deslocamento
```


- <span style="color:rgb(146, 208, 80)">STORE :</span> 

![[Pasted image 20250218145743.png]]

- <span style="color:rgb(146, 208, 80)">LOAD :</span>

![[Pasted image 20250218150232.png]]


- **Componentes Utilizados em cada tipo de Instrução :**

1. Aritméticas/Lógicas  :  <span style="color:rgb(255, 255, 0)">REGS + ALU</span> 
2. Acesso a Memória  :  <span style="color:rgb(255, 255, 0)">REGS + ALU + MEM</span> 
3. Desvio **Condicional**  :  <span style="color:rgb(255, 255, 0)">REGS+ALU + ADD+SHIFT + END DESVIO</span> 
4. Desvio **Incondicional**  :  <span style="color:rgb(255, 255, 0)">ADD+SHIFT</span> 


> **SHIFT**

	R-Shift >>
	L-Shift <<


#### Fases da Instrução

> GHz
> GigaHertz
> Frequência
> Ciclos/segundo
> **CLOCK**


##### 1° - FETCH

   Endereço da instrução (PC) é buscado (READ) da memória e armazenado no <span style="color:rgb(255, 255, 0)">Instruction Register (IR)</span>.
   
-- -
##### 2° - DECODE + OPERANDOS

   <span style="color:rgb(146, 208, 80)">Decode:</span>  o conteúdo do **IR** é passado para a **Unidade de Controle** onde ele é decodificado nos sinais de controle para executar a instrução.

   <span style="color:rgb(146, 208, 80)">Operandos:</span>  os valores dos possíveis operandos são buscados no banco de registradores.
   
-- -
##### 3° - EXECUTION

   Operações aritméticas e lógicas da instrução são executadas **(ALU)**.
   
-- -
##### 4° - RESULTS

   Depende do tipo de instrução:

   <span style="color:rgb(146, 208, 80)">Registradores:</span>  armazenar o resultado no registrador de destino.
   `ADD R1, R2, R3` -> `R1 = R2 + R3`.

   <span style="color:rgb(146, 208, 80)">Memória:</span>  o endereço calculado de memória é acessado **(LOAD/STORE)** e dados são escritos no endereço de memória.

-- -
##### 5° - WRITE BACK

   <span style="color:rgb(146, 208, 80)">LOAD:</span>  armazenar em um registrador o conteúdo de um endereço de memória.

	LD R1, R2, OFFSET

* Os dados lidos da memória são armazenados no registrador de destino.

-- -

##### Memory

   <span style="color:rgb(146, 208, 80)">MAR:</span>  *Memory Address Register*  ->  <span style="color:rgb(112, 48, 160)">(Armazena Endereço de Dados/Instrução)</span>

   <span style="color:rgb(146, 208, 80)">MDR:</span>  *Memory Data Register*  ->  <span style="color:rgb(112, 48, 160)">(Armazena Dados)</span> 