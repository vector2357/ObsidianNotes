-- -

### Erros


> **Introdução**

A obtenção de uma solução numérica para um problema físico por meio da aplicação de métodos numéricos nem sempre fornece valores que se encaixam dentro de limites razoáveis.

Esta afirmação é verdadeira mesmo quando se aplica um método adequado e os cálculos são efetuados de uma maneira correta.

Para facilitar a apresentação das fontes de **erros**, o processo de solução de um problema físico, por meio da aplicação de métodos numéricos, é representado abaixo de uma forma geral.


![[calc-image1.png]]

Duas fases podem ser identificadas no diagrama da imagem:

1. <span style="color:rgb(146, 208, 80)">MODELAGEM:</span>  é a fase de obtenção de um modelo matemático que descreve o comportamento do sistema físico em questão.

2. <span style="color:rgb(146, 208, 80)">RESOLUÇÃO:</span>  é a fase de obtenção da solução do modelo matemático através da aplicação de métodos numéricos.


#### 1.2 - Erros na Fase de Modelagem

Ao se tentar representar um fenômeno do mundo físico por meio de um modelo matemático, raramente se tem uma descrição correta deste fenômeno. Normalmente, são necessárias várias simplificações do mundo físico para que tenha um modelo matemático com o qual se possa trabalhar.

> **Exemplo:**

	Para estudo do movimento de um corpo sujeito a uma aceleração constante, tem-se a seguinte equação:

$$d\;=\;d_0\;+\;v_0\,t\;+\;\frac{1}{2}\;at^2$$
onde:

$d\quad-\quad\text{distância percorrida}$
$d_0\quad-\quad\text{distância inicial}$
$v_0\quad-\quad\text{velocidade inicial}$
$t\quad-\quad\text{tempo}$
$a\quad-\quad\text{aceleração}$


> **Exemplo:**

Supondo-se que um engenheiro queira determinar a altura de um edifício e que para isso disponha apenas de uma bolinha de metal, um cronômetro e a fórmula acima, ele sobre então ao topo do edifício e mede o tempo que a bolinha gasta para tocar o solo, ou seja, 3 segundos.

Levando este valor à equação, obtém-se:

$$d\;=\;0\;+\;0\,.\,3\;+\frac{1}{2}\,.\,9,8\,.\,3^2$$
$$d\;=\;44,1\;\text{m}$$

Este resultado é confiável?

É bem provável que não, pois no modelo matemático não foram consideradas outras forças como, por exemplo, a resistência do ar, a velocidade do vento, etc.

Além destas, existe um outro fator que tem muita influência: a imprecisão da leitura do cronômetro, pois para um pequena variação no tempo medido existe uma grande variação na altura do edifício.