-- -

### Introdução


Um **Sistema Operacional** é um programa que gerencia o *hardware* de um computador. Ele também fornece uma base para os programas aplicativos e atua como <span style="color:rgb(255, 255, 0)">intermediário</span>entre o **usuário** e o **hardware** do computador.

Os sistemas operacionais assumem diferentes abordagens ao cumprir essas tarefas, como por exemplo:

- SO's de mainframes são projetados para otimizar a utilização do hardware.
- SO's de computadores pessoais (PCs) suportam jogos complexos, aplicações comerciais e tudo mais entre estes.
- SO's de computadores móveis fornecem um ambiente no qual o usuário pode interagir facilmente com o computador para executar programas.

Assim, alguns sistemas operacionais são projetados para serem <span style="color:rgb(146, 208, 80)">convenientes</span> enquanto outros são projetados para serem <span style="color:rgb(146, 208, 80)">eficientes</span>.


> **OBJETIVOS DO CAPÍTULO**

- Descrever a organização básica dos sistemas de computação.
- Oferecer um giro completo pelos principais componentes dos sistemas operacionais.
- Fornecer uma visão geral dos vários tipos de ambientes de computação.
- Examinar diversos sistemas operacionais de fonte aberta.


#### 1.1 - O que Fazem os Sistemas Operacionais

Um sistema de computação pode ser grosseiramente dividido em 4 componentes:

1. ***hardware***
2. ***sistema operacional***
3. ***programas aplicativos***
4. ***usuários***

O ***hardware***  —  a unidade central de processamento (<span style="color:rgb(255, 255, 0)">CPU</span> — Central Processing Unit), a <span style="color:rgb(255, 255, 0)">memória</span> e os dispositivos de entrada/saída (<span style="color:rgb(255, 255, 0)">I/O</span> — input/output)  —  fornece os recursos básicos de computação do sistema.

Os ***programas aplicativos***  —  como <span style="color:rgb(255, 255, 0)">processadores de texto</span>, <span style="color:rgb(255, 255, 0)">planilhas</span>, <span style="color:rgb(255, 255, 0)">compiladores</span> e <span style="color:rgb(255, 255, 0)">navegadores da web</span>  —  definem as formas pelas quais esses recursos são utilizados para resolver os problemas computacionais dos usuários.

O ***sistema operacional*** controla o **hardware** e coordena seu uso pelos diversos programas aplicativos de vários ***usuários***.

> Também podemos considerar um sistema de computação como composto de *hardware*, *software* e *dados*. O sistema operacional fornece os meios para a utilização apropriada desses recursos durante a operação do sistema de computação.

###### Analogia :

	Um sistema operacional é semelhante ao governo. Tal como o governo, ele não desempenha funções úteis para si mesmo. Ele simplesmente proporciona um AMBIENTE no qual outros programas possam desempenhar tarefas úteis.

![[_- visual selection.png]]


##### 1.1.1 - O Ponto de Vista do Usuário

Do ponto de vista do usuário, faz mais sentido um único usuário utilizando os recursos do sistema. Nesse caso o sistema operacional é projetado principalmente para <span style="color:rgb(146, 208, 80)">facilidade de uso</span>, com alguma atenção dada ao *desempenho* e nenhuma à <span style="color:rgb(146, 208, 80)">utilização dos recursos</span>.

É claro que o desempenho é importante para o usuário, mas esses sistemas são otimizados para a experiência de um único usuário e não para atender vários usuários.

Em outros casos, o usuário senta-se diante de um terminal conectado a um <span style="color:rgb(146, 208, 80)">mainframe</span> ou a um <span style="color:rgb(146, 208, 80)">minicomputador</span>. Outros usuários acessam o mesmo computador por intermédio de outros terminais. Esses usuários compartilham recursos e podem trocar informações.

Em tais casos, o sistema operacional é projetado para maximizar a <span style="color:rgb(146, 208, 80)">utilização dos recursos</span>  —  assegurando que todo o tempo de CPU, memória e I/O disponíveis, seja utilizado eficientemente e que nenhum usuário individual ocupe mais do que sua cota.

Há ainda outros casos em que os usuários ocupam <span style="color:rgb(146, 208, 80)">estações de trabalho</span> conectadas a redes de outras estações de trabalho e <span style="color:rgb(146, 208, 80)">servidores</span>. Esses usuários possuem recursos dedicados à sua disposição, mas também compartilham recursos, tais como a rede e os servidores, incluindo servidores de arquivo, de computação e de impressão. Portanto, seu sistema operacional é projetado para estabelecer um compromisso entre usabilidade individual e utilização dos recursos.

Alguns computadores são pouco ou nada visíveis ao usuário. Por exemplo, computadores embutidos em dispositivos domésticos e em automóveis podem ter um mostrador numérico e podem acender ou apagar luzes indicativas para mostrar um estado, mas basicamente eles e seus sistemas operacionais são projetados para operar sem intervenção do usuário.


##### 1.1.2 - O Ponto de Vista do Sistema

Do ponto de vista do computador, o sistema operacional é o programa mais intimamente envolvido com o hardware. Nesse contexto, podemos considerar um sistema operacional como um <span style="color:rgb(146, 208, 80)">alocador de recursos</span>.

Um sistema de computação tem muitos recursos que podem ser necessários à resolução de um problema:

- tempo de CPU
- espaço de memória 
- espaço de armazenamento em arquivo
- dispositivos de I/O

O sistema operacional atua como o **gerenciador** desses recursos.

Uma visão ligeiramente diferente de um sistema operacional enfatiza a necessidade de controle dos diversos dispositivos de I/O e programas de usuário. Um sistema operacional é um <span style="color:rgb(146, 208, 80)">programa de controle</span>.

Um programa de controle gerencia a execução de programas de usuário para evitar erros e o uso impróprio do computador. Ele se preocupa principalmente com a operação e o controle de dispositivos de I/O.


##### 1.1.3 - Definindo Sistemas Operacionais

Sistemas operacionais existem porque oferecem uma forma razoável de resolver o problema de criar um sistema de computação utilizável. O objetivo fundamental dos sistemas de computação é executar os programas dos usuários e facilitar a resolução dos seus problemas.

Os programas aplicativos são desenvolvidos, tendo em vista que o hardware puro, sozinho, não é particularmente fácil de ser utilizado. Esses programas requerem determinadas operações comuns, como as que controlam os dispositivos de I/O.

As funções comuns de controle e alocação de recursos são, então, reunidas em um único software: o ***sistema operacional***.

Uma definição mais comum, que é a que costumamos seguir, é que o sistema operacional é o único programa que permanece em execução no computador durante todo o tempo  —  chamado, em geral, de <span style="color:rgb(146, 208, 80)">kernel</span>. (Além do kernel, há dois outros tipos de programas: os <span style="color:rgb(255, 255, 0)">programas do sistema</span> que estão associados ao sistema operacional, mas não necessariamente fazem parte do kernel, e os <span style="color:rgb(255, 255, 0)">programas aplicativos</span> que incluem todos os programas não associados à operação do sistema.)

Com frequência, os sistemas operacionais de dispositivos móveis incluem não só um kernel básico, mas também <span style="color:rgb(146, 208, 80)">middleware</span>  —  um conjunto de estruturas de software que fornece serviços adicionais para desenvolvedores de aplicativos. Por exemplo, os dois sistemas operacionais de dispositivos móveis predominantes  —  o iOS da Apple e o Android da Google  —  têm um **kernel básico** e o **middleware** que suporta bancos de dados, ambientes multimídia e elementos gráficos (para citar apenas alguns recursos).


#### 1.2 - Organização do Sistema de Computação

Antes que possamos explorar os detalhes de como os sistemas de computação funcionam, precisamos de um conhecimento geral da estrutura de um sistema de computação.

##### 1.2.1 - Operação do Sistema de Computação

Um moderno sistema de computação de uso geral é composto por uma ou mais CPUs e vários controladores de dispositivos conectados por intermédio de um bus comum que dá acesso à memória compartilhada. Cada controlador de dispositivos é responsável por um tipo específico de dispositivo (por exemplo, drives de disco, dispositivos de áudio ou exibidores de vídeo).

A CPU e os controladores de dispositivos podem operar concorrentemente, competindo por ciclos de memória. Um controlador de memória sincroniza o acesso à memória compartilhada para assegurar um acesso ordenado.

Para que um computador comece a operar  —  por exemplo, quando é ligado ou reiniciado  —  ele precisa ter um programa inicial para executar. Esse programa inicial, ou programa <span style="color:rgb(146, 208, 80)">bootstrap</span>, tende a ser simples.

Normalmente, ele é armazenado dentro do hardware do computador em memória somente de leitura <span style="color:rgb(255, 255, 0)">(ROM)</span> ou em memória somente de leitura eletricamente apagável e programável (<span style="color:rgb(255, 255, 0)">EEPROM</span> — electrically erasable programmable read-only memory), conhecida pelo termo geral <span style="color:rgb(146, 208, 80)">firmware</span>.

Assim que o kernel é carregado e está em execução, ele pode começar a fornecer serviços para o sistema e seus usuários. Alguns serviços são fornecidos fora do kernel por programas do sistema que são carregados na memória em tempo de inicialização para se tornarem <span style="color:rgb(146, 208, 80)">processos do sistema</span>, ou <span style="color:rgb(146, 208, 80)">daemons do sistema</span>, que são executados durante todo o tempo em que o kernel é executado. No UNIX, o primeiro processo do sistema é **“init”**, e ele inicia muitos outros ***daemons***.

O software pode disparar uma interrupção executando uma operação especial denominada <span style="color:rgb(146, 208, 80)">chamada de sistema</span> (também conhecida como <span style="color:rgb(146, 208, 80)">chamada de monitor</span>).

> **OBS:**  uma *interrupção* é disparada na ocorrência de um evento.


##### 1.2.2 - Estrutura de Armazenamento

A CPU só pode carregar instruções a partir da memória; portanto, para serem executados, os programas devem estar armazenados na memória.

O projeto de um sistema de memória completo deve balancear todos os fatores envolvidos, como **custo e desempenho**:

	Só deve usar memória cara quando necessário e fornecer o máximo possível de memória barata e não volátil.
	Caches podem ser instalados para melhorar o desempenho quando existir grande disparidade no tempo de acesso ou na taxa de transferência entre dois componentes.


##### 1.2.3 - Estrutura de I/O

O armazenamento é apenas um dos muitos tipos de dispositivos de I/O de um computador. Grande parte do código do sistema operacional é dedicada ao gerenciamento de I/O, tanto por causa de sua importância para a <span style="color:rgb(146, 208, 80)">confiabilidade</span> e o <span style="color:rgb(146, 208, 80)">desempenho</span> de um sistema quanto em razão da <span style="color:rgb(146, 208, 80)">natureza variada dos dispositivos</span>. A seguir, fornecemos uma visão geral do I/O.

Dependendo do controlador, pode haver mais de um dispositivo conectado. Por exemplo, sete ou mais dispositivos podem ser conectados ao controlador da ***interface de pequenos sistemas de computação*** (<span style="color:rgb(255, 255, 0)">SCSI — small computer-systems interface</span>).

Um controlador de dispositivos mantém algum armazenamento em <span style="color:rgb(146, 208, 80)">buffer local</span> e um conjunto de registradores de uso específico. O controlador de dispositivos é responsável por movimentar os dados entre os dispositivos periféricos que controla e seu buffer de armazenamento local.

Normalmente, os sistemas operacionais têm um <span style="color:rgb(146, 208, 80)">driver de dispositivo</span> para cada **controlador de dispositivos**. Esse driver entende o controlador de dispositivos e fornece uma interface uniforme entre o dispositivo e o resto do sistema operacional.

> **I/O dirigido por interrupções :**

1. Driver de dispositivos carrega os registradores apropriados

2. Examina o conteúdo dos registradores para determinar que ação tomar (ex: ler uma letra do teclado)

3. Inicia a transferência dos dados do dispositivo para seu buffer local

4. Informa ao driver de dispositivo a finalização da operação através de uma interrupção

5. O driver retorna o controle ao Sistema Operacional

6. <span style="color:rgb(255, 255, 0)">Problema:</span>  produz grande **Overhead** em movimentação de grande volume de dados
7. <span style="color:rgb(146, 208, 80)">Solução:</span>  ***DMA:***  Acesso Direto à Memória


> **DMA - Direct Memory Access :**

1. Acesso direto à memória

2. Após posicionar buffers, ponteiros e contadores associados ao dispositivo I/O, o controlador de dispositivo transfere o bloco inteiro de dados diretamente da memória para o seu próprio buffer ou a partir dele para a memória, sem intervenção da CPU

3. Interrupções geradas por blocos ao invés de interrupções por bytes

4. Enquanto o controlador de dispositivo executa essas operações, a CPU está disponível para executar outras tarefas


#### 1.3 - Arquitetura dos Sistemas de Computação

Um sistema de computação pode ser organizado de várias maneiras diferentes que, grosso modo, podemos categorizar de acordo com o **número de processadores** de uso geral utilizados.

> **Tipos de Sistemas Operacionais**

1. Sistemas <span style="color:rgb(146, 208, 80)">Monoprogramáveis/Monotarefa</span>
2. Sistemas <span style="color:rgb(146, 208, 80)">Multiprogramáveis/Multitarefa</span>
3. Sistemas com <span style="color:rgb(146, 208, 80)">Múltiplos Processadores</span> 


##### 1.3.1 - Sistemas Uniprocessadores

Em <span style="color:rgb(255, 255, 0)">sistemas monoprogramáveis</span>, um único programa/tarefa é capaz de utilizar a CPU, Memória Principal e dispositivos de I/O.

Em sistemas <span style="color:rgb(255, 255, 0)">multiprogramáveis</span>, mais de um programa/tarefa consegue fazer uso do processador.

-  ***SISTEMAS vs USUÁRIOS***

|           Sistema            |     |  1 usuário  | 2 ou mais usuários |
| :--------------------------: | --- | :---------: | :----------------: |
|                              |     |             |                    |
|  Monoprogramação/Monotarefa  |     | Monousuário |        N/A         |
| Multiprogramação/Multitarefa |     | Monousuário |    Multiusuário    |


##### 1.3.2 - Sistemas Multiprocessadores

Nos últimos anos, os **sistemas multiprocessadores** (também conhecidos como <span style="color:rgb(146, 208, 80)">sistemas paralelos</span> ou <span style="color:rgb(146, 208, 80)">sistemas multicore</span>) começaram a dominar o cenário da computação. Tais sistemas possuem dois ou mais processadores em estreita comunicação, compartilhando bus do computador e algumas vezes o relógio, a memória e os dispositivos periféricos.

Os sistemas multiprocessadores aparecem pela primeira vez e principalmente em servidores e, desde então, migraram para sistemas desktop e laptop. Recentemente, múltiplos processadores têm aparecido em dispositivos móveis como os smartphones e tablets.

Os sistemas multiprocessadores têm três vantagens principais:

1. <span style="color:rgb(146, 208, 80)">Aumento do throughput.</span>  Com o aumento do número de processadores, espera-se que mais trabalho seja executado em menos tempo. No entanto, a taxa de aumento de velocidade com N processadores não é N; é menor do que N. Quando vários processadores cooperam em uma tarefa, observa-se algum overhead para manter todas as partes trabalhando corretamente. Esse overhead, mais a concorrência por recursos compartilhados, diminui o ganho esperado do processadores adicionais. Do mesmo modo, N programadores trabalhando em cooperação não produzem N vezes o montante de trabalho que um único programador produziria.
2. <span style="color:rgb(146, 208, 80)">Economia de escala.</span>  Sistemas multiprocessadores podem custar menos do que múltiplos sistemas equivalentes de processador único, já que eles podem compartilhar periféricos, memória de massa e suprimentos de energia. Quando vários programas trabalham sobre o mesmo conjunto de dados, é mais barato armazenar esses dados em um disco, compartilhando-os com todos os processadores, do que usar muitos computadores com discos locais e muitas cópias dos dados.
3. <span style="color:rgb(146, 208, 80)">Aumento de confiabilidade.</span>  Se as funções puderem ser distribuídas apropriadamente entre vários processadores, a falha de um processador não interromperá o sistema, tornando-o apenas mais lento. Se tivermos dez processadores e um falhar, cada um dos nove processadores remanescentes poderá ficar com uma parcela do trabalho do processador que falhou. Assim, o sistema inteiro operará somente 10% mais devagar, em vez de falhar completamente.
![[os-image2.png]]
O aumento da <span style="color:rgb(146, 208, 80)">confiabilidade</span> de um sistema de computação é crucial em muitas aplicações. A capacidade de continuar fornecendo serviço proporcionalmente ao nível do hardware remanescente é chamada de <span style="color:rgb(255, 255, 0)">degradação limpa</span>.

Alguns sistemas vão além da degradação limpa e são chamados de <span style="color:rgb(255, 255, 0)">tolerantes a falhas</span>, porque podem sofrer falha em qualquer um dos componentes e continuar a operar. A tolerância a falhas requer um mecanismo para permitir que a falha seja detectada, diagnosticada e, se possível, corrigida.


> **Multiprocessamento Assimétrico**

- É designado uma tarefa específica a cada processador
- Um <span style="color:rgb(255, 255, 0)">processador mestre</span> controla o sistema
- Demais processadores se dirigem ao mestre para instruções ou possuem tarefas predefinidas 
- Relacionamento <span style="color:rgb(255, 255, 0)">mestre-escravo</span> 

> **Multiprocessamento Simétrico (SMP)**

- Cada processador executa todas as tarefas do sistema operacional
- Cada processador tem o seu próprio conjunto de registradores e cache, mas compartilham a memória física
- Vantagem: muitos processos podem ser executados ao mesmo tempo, sem prejuízo no desempenho


	O multiprocessamento adiciona CPU's para aumentar o poder de computação. Se a CPU tem um <span style="color:rgb(146, 208, 80)">controlador de memória</span> integrado, o acréscimo de CPU's também pode aumentar o montante de memória endereçável no sistema.

De qualquer forma, o **multiprocessamento** pode fazer com que um sistema altere seu modelo de acesso à memória, do ***acesso uniforme*** (<span style="color:rgb(146, 208, 80)">UMA - uniform memory access</span>) ao ***acesso não uniforme*** (<span style="color:rgb(146, 208, 80)">NUMA - non-uniform memory access</span>).

- ***UMA*** :  é definido como a situação em que o acesso a qualquer RAM a partir de qualquer CPU leva o mesmo período de tempo

- ***NUMA*** :  algumas partes da memória podem demorar mais para serem acessadas do que outras


##### Sistemas Agrupados (Clusters)

Outro tipo de sistema multiprocessador é o **sistema em cluster** que reúne várias CPUs. Esses sistemas diferem dos sistemas multiprocessadores descritos na seção 1.3.2 por serem compostos de dois ou mais sistemas individuais  -- ou nós --  acoplados. Tais sistemas são considerados <span style="color:rgb(146, 208, 80)">fracamente acoplados</span>. Cada nó pode ser um sistema ***uniprocessador*** ou um sistema ***multicore***.

-- -
> **Características:**

-  Reúnem várias CPUs para desenvolver trabalho computacional

-  Compostos por 2 ou mais sistemas individuais 

-  Computadores em Cluster compartilham memória e são conectados através de uma rede local (LAN)

-  Objetivo:
	-  alta disponibilidade, através do uso de redundância no sistema

-  Uma camada de software de cluster opera sobre os nós do cluster 

-  Cada Nó pode monitorar um ou mais nós do cluster

-  Se uma das máquinas falhar, outra se apropria da sua memória e reinicia a aplicação
-- -

Um cluster pode ser estruturado <span style="color:rgb(146, 208, 80)">assimétrica</span> ou <span style="color:rgb(146, 208, 80)">simetricamente</span>.

-   ***Assimétrico***
		uma das máquinas permanece em <span style="color:rgb(255, 255, 0)">modalidade alerta máximo</span>, enquanto a outra executa as aplicações. A máquina **hospedeira** em alerta nada faz além de monitorar o servidor ativo.

-  ***Simétrico***
		dois ou mais hospedeiros executam aplicações e se monitoram uns aos outros. Essa estrutura é **mais eficiente**, pois usa todo o hardware disponível. No entanto, isso requer que mais de uma aplicação esteja disponível para execução.


Já que um cluster é composto por vários sistemas de computação conectados por uma rede, os clusters também podem ser usados para fornecer ambientes de <span style="color:rgb(146, 208, 80)">computação de alto desempenho</span>.

Esses sistemas podem fornecer um poder de computação significativamente maior do que sistemas de um único processador , ou até mesmo sistemas SMP, porque podem executar uma aplicação **concorrentemente** em todos os computadores do cluster.

No entanto, a aplicação deve ter sido escrita especificamente para se beneficiar do cluster. Isso envolve um técnica conhecida como <span style="color:rgb(146, 208, 80)">paralelização</span> que divide um programa em componentes separados executados em paralelo em computadores individuais do cluster.

Normalmente, essas aplicações são projetadas para que, após cada nó de computação do cluster ter resolvido sua parte do problema, os resultados de todos os nós sejam combinados em uma solução final.


#### 1.4 - Estrutura do Sistema Operacional

Um dos aspectos mais importantes dos sistemas operacionais é sua capacidade de multiprogramar. Geralmente, um único programa não pode manter a CPU ou os dispositivos de I/O ocupados o tempo todo. Usuários individuais costumam ter vários programas em execução (<span style="color:rgb(146, 208, 80)">processo</span>).

A multiprogramação aumenta a utilização da CPU organizando os jobs (código e dados) de modo que a CPU tenha sempre um para executar.

A ideia é a seguinte: O sistema operacional mantém vários jobs na memória simultaneamente. Já que a memória principal costuma ser muito pequena para acomodar todos os jobs, inicialmente eles são mantidos em disco no <span style="color:rgb(146, 208, 80)">pool de jobs</span>. Esse ***pool*** é composto de todos os processos residentes em disco aguardando alocação da memória principal.

##### Sistemas de Tempo Compartilhado

-  Também conhecido como <span style="color:rgb(255, 255, 0)">sistemas multitarefa</span> 
-  É uma extensão dos sistemas **multiprocessados**
-  A *CPU* executa múltiplos jobs alternando-se entre eles
-  Mudança entre jobs ocorrem com grande frequência, usuários podem interagir com vários aplicativos
-  O tempo compartilhado requer um <span style="color:rgb(255, 255, 0)">sistema de computação interativo</span> 
	- comunicação direta entre o usuário e o sistema
	- tempo de resposta deve ser curto

-  Uso de multiprogramação e <span style="color:rgb(255, 255, 0)">escalonamento da CPU</span> 

![[os-image3.png]]

##### Conceitos

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Processo :</span>

	 É um programa carregado na memória que está em execução

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Escalonamento de Jobs :</span>

	 Se vários jobs estão prontos para serem trazidos para a memória principal e não há espaço para todos, o **Sistema Operacional** deve escolher um deles
	 obs.:  denominados também ***scheduling de jobs***.

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Escalonamento da CPU :</span>

	 Se vários jobs estão prontos para serem executados ao mesmo tempo, o **Sistema Operacional** deve escolher um deles
	 obs.:  denominados também ***scheduling da CPU***.

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Gerenciamento de memória :</span>

	 Requerido quando existem vários programas na memória ao mesmo tempo

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Swapping :</span>

	 Em um sistema de tempo compartilhado, o Sistema Operacional deve assegurar um tempo de resposta razoável

	 Para isso, os processos são alternados entre a memória principal e o disco

-  <span style="color:rgb(146, 208, 80);font-weight:700;font-style:italic;">Memória Virtual :</span>

	 Técnica que permite a execução de um processo que não se encontra totalmente na memória principal

	 Permitem que usuário executem programas além da capacidade de memória física


#### 1.5 - Operações do Sistema Operacional

Os Sistemas Operacionais modernos são dirigidos por <span style="color:rgb(0, 176, 240)">interrupções</span>. Se não existem processos para executar, dispositivos de I/O para servir e usuários a quem responder, então um sistema operacional permanece inativo esperando que algo aconteça. Os eventos são quase sempre sinalizados pela ocorrência de uma **interrupção** ou de uma <span style="color:rgb(146, 208, 80)">exceção (<span style="font-weight:600;font-style:italic;text-decoration:underline">trap</span>)</span>.

> ***Exceção :*** 
> 	 é uma interrupção <span style="text-decoration:underline">gerada por software</span> causada por um erro (por exemplo, divisão por zero ou acesso inválido à memória) ou por uma solicitação específica proveniente de um programa de usuário para que um serviço do sistema operacional seja executado.

É fornecida uma ***rotina de serviço*** de interrupções para lidar com a interrupção.


##### 1.5.1 - Operação em Modalidade Dual e Multimodalidade

Para garantir a execução apropriada do sistema operacional, temos que ser capazes de distinguir entre a execução de código do **sistema operacional** e de código definido pelo **usuário**.

A abordagem adotada pela maioria dos sistemas de computação é o fornecimento de suporte de hardware que permite diferenciar as diversas modalidades de execução.

Precisamos de, pelo menos, duas <span style="color:rgb(146, 208, 80)">modalidades</span> de operação separadas: a <span style="color:rgb(255, 255, 0)">modalidade de usuário</span> e a <span style="color:rgb(255, 255, 0)">modalidade de kernel</span> (também chamada de modalidade de supervisor, modalidade de sistema ou modalidade privilegiada).

-  ***Modalidade de Usuário :***
	 Tarefa que é executada em nome do **usuário**

-  ***Modalidade de Kernel ou privilegiado :***
	 Tarefa que é executada em nome do **Sistema Operacional**

Um ***bit***, chamado <span style="color:rgb(146, 208, 80)">bit de modalidade</span>, é adicionado ao hardware do computador para indicar a modalidade corrente: kernel (0) ou usuário (1).

> **Exemplo:**
> 
> 	quando a aplicação de usuário solicita um serviço do sistema operacional (por meio de chamada de sistema), o sistema deve passar da modalidade de **usuário** para a de **kernel** de modo a atender a solicitação.


![[os-image4.png]]

Em tempo de inicialização do sistema, o hardware começa a operar em modalidade de ***kernel***.

###### Instruções Privilegiadas :

	instruções que só podem ser executadas pelo hardware em modalidade de kernel. Se é feita alguma tentativa de executar uma instrução privilegiada em modalidade de usuário, o hardware não executa a instrução, tratando-a como ilegal e interceptando-a (por uma exceção) para o sistema operacional.

***Exemplos:*** 
- instrução de passagem para a modalidade de kernel
- controle de I/O
- gerenciamento do timer
- gerenciamento de interrupções


O conceito de modalidades pode ser estendido para além de duas modalidades (caso em que a CPU utiliza mais de um bit para estabelecer e testar a modalidade). Com frequência, CPUs que suportam virtualização têm uma modalidade separada para indicar quando o <span style="color:rgb(146, 208, 80)">gerenciador de máquinas virtuais (VMM)</span> e o software de gerenciamento de virtualização estão no controle do sistema.


##### 1.5.2 - Timer

-  ***Objetivo :***
	 não permitir que um programa de usuário fique preso em um loop infinito ou não chame os serviços do sistema e nunca retorne o controle ao sistema operacional

O *Timer* pode ser configurado para interromper o computador após um período especificado, podendo ser <span style="color:rgb(146, 208, 80)">fixo</span> ou <span style="color:rgb(146, 208, 80)">variável</span>.

-  <span style="color:rgb(146, 208, 80);font-weight:500">Timer variável</span> 

	- implementado através de um relógio de marcação fixa e um contador
	
	- cada vez que o relógio marca, o contador é decrementado
	
	- quando o contador atingir o valor zero, ocorre uma interrupção
	
	- antes de retornar o controle ao usuário, o sistema operacional assegura que o timer seja configurado de forma a causar interrupção
	
	- quando o timer interrompe, o controle se transfere automaticamente para o sistema operacional que pode tratar a interrupção como um erro fatal ou dar mais tempo ao programa


#### 1.6 - Gerenciamento de Processos

> *Um processo é um programa em execução.*

Um processo é a unidade de trabalho de um sistema. Um **sistema** consiste em um conjunto de **processos**, alguns dos quais são <span style="color:rgb(146, 208, 80)">processos do sistema operacional</span> (os que executam código do sistema), e o resto são <span style="color:rgb(146, 208, 80)">processos de usuário</span> (aqueles que executam código de usuário).

Todos esse processos podem ser executados **concorrentemente**.

-  ***Diferença entre Programa e Processo :***

	Programa é uma entidade <span style="color:rgb(255, 255, 0)">passiva</span>
	Processo é uma entidade <span style="color:rgb(146, 208, 80)">ativa</span> 

O **processo** necessita de recursos para realizar sua tarefa, como:
1. *CPU, memória, I/O, arquivos*
2. Dados de inicialização


-  <span style="color:rgb(146, 208, 80);font-weight:600">Processo Single-threaded:</span> 

	1. possui um **contador de programa** especificando o local da próxima instrução a executar
	2. processo executa as instruções sequencialmente, uma de cada vez

-  <span style="color:rgb(146, 208, 80);font-weight:600">Processo Multi-threaded:</span> 

	1. processo tem um **contador de programa** pro thread


Tipicamente, o sistema tem muitos processos, alguns usuários, algum sistema operacional rodando concorrentemente em uma ou mais CPUs.

Simultaneidade exige a multiplexação das CPUs entre os processos / threads.


> **O sistema operacional é responsável pelas seguintes atividades relacionadas com gestão de processos:**

1.  <span style="color:rgb(255, 255, 0)">Criar e Deletar</span> usuários e processos do sistema
2.  <span style="color:rgb(255, 255, 0)">Suspender e retomar</span> processos
3.  Fornecer mecanismos para <span style="color:rgb(255, 255, 0)">sincronização</span> de processos
4.  Fornecer mecanismos para <span style="color:rgb(255, 255, 0)">comunicação</span> entre processos
5.  Fornecer mecanismos para <span style="color:rgb(255, 255, 0)">tratamento de deadlocks</span> 
6.  Executar o <span style="color:rgb(255, 255, 0)">scheduling de processos</span> e <span style="color:rgb(255, 255, 0)">threads</span> nas CPUs

![[os-image7.png]]


#### 1.7 - Gerenciamento de Memória

A memória principal costuma ser o único grande dispositivo de armazenamento que a CPU consegue endereçar e acessar diretamente.

Por exemplo, para a CPU processar dados do disco, primeiro esses dados devem ser transferidos para a memória principal por chamadas de I/O geradas pela CPU.

Para melhorar tanto a utilização da CPU quanto a velocidade de resposta do computador para seus usuários, computadores de uso geral devem **manter vários programas na memória**, criando a necessidade de ***gerenciamento da memória***.

-  **Gerenciamento**
	Todos os <span style="color:rgb(146, 208, 80)">dados na memória antes e após o processamento</span>
	Todas as <span style="color:rgb(146, 208, 80)">instruções na memória</span>, a fim de serem executadas


> **O gerenciamento de memória determina o que e quando dados e instruções são armazenados na memória, a fim de otimizar a utilização da CPU e da resposta do computador aos usuários**


O sistema operacional é responsável pelas seguintes atividades relacionadas com o gerenciamento da memória :

1.  <span style="color:rgb(255, 255, 0)">Controlar quais partes da memória</span> estão sendo <span style="color:rgb(255, 255, 0)">concorrentemente utilizadas</span> e por <span style="color:rgb(255, 255, 0)">quem</span>
2.  <span style="color:rgb(255, 255, 0)">Decidir quais processos</span> (ou partes de processos) <span style="color:rgb(255, 255, 0)">e dados</span> devem ser <span style="color:rgb(255, 255, 0)">transferidos </span>para dentro e para fora da memória
3.  <span style="color:rgb(255, 255, 0)">Alocar e desaloca</span><span style="color:rgb(255, 255, 0)">r espaço de memória</span> conforme necessário


#### 1.8 - Gerenciamento do Armazenamento

O *SO* fornece uma visão lógica e uniforme do armazenamento de informações.

O sistema operacional abstrai, das propriedades físicas dos seus dispositivos de armazenamento, a definição de uma <span style="color:rgb(255, 255, 0)">unidade lógica de armazenamento</span>, o <span style="color:rgb(146, 208, 80);font-weight:700">arquivo</span>.

O sistema operacional mapeia arquivos para a mídia física e acessa esses arquivos por meio de dispositivos de armazenamento.

##### 1.8.1 - Gerenciamento do Sistema de Arquivos

Os computadores podem **armazenar** informações em vários tipos diferentes de mídia física, como por exemplo :

-  Disco magnético
-  Disco ótico
-  Fita magnética


Cada mídia é controlada por um dispositivo, tal como um **drive** de disco ou de fita. Algumas propriedades que envolvem esses diferentes dispositivos são :

-  Velocidade de acesso
-  Capacidade
-  Taxa de transferência de dados
-  Método de acesso (sequencial ou randômico)

![[os-image5.png]]

Um **arquivo** é um conjunto de informações relacionadas definido por seu criador.

Arquivos de dados podem ser numéricos, alfabéticos, alfanuméricos ou binários. Os arquivos podem ter formato livre (por exemplo, arquivos de texto) ou podem ser formatados rigidamente (no caso de campos fixos).

O sistema operacional implementa o conceito abstrato de arquivo gerenciando mídias de armazenamento de massa, como fitas e discos, e os dispositivos que as controlam. 

Normalmente, os **arquivos** são organizados em <span style="color:rgb(146, 208, 80)">diretórios</span> para facilitar seu uso.

Quando vários **usuários** têm acesso aos arquivos, pode ser desejável controlar que usuários pode acessar um arquivo e como esse usuário pode acessá-lo (por exemplo, para ler, gravar, anexar).


> **O sistema operacional é responsável pelas seguintes atividades relacionadas com o gerenciamento de arquivos :**

1.  <span style="color:rgb(255, 255, 0)">Criar</span> e <span style="color:rgb(255, 255, 0)">apagar</span> arquivos
2.  <span style="color:rgb(255, 255, 0)">Criar</span> e <span style="color:rgb(255, 255, 0)">apagar diretórios</span> para organizar arquivos
3.  <span style="color:rgb(255, 255, 0)">Suportar primitivos</span> para a <span style="color:rgb(255, 255, 0)">manipulação de arquivos e diretórios</span>
4.  <span style="color:rgb(255, 255, 0)">Mapear arquivos</span> em <span style="color:rgb(255, 255, 0)">memória secundária</span>
5. <span style="color:rgb(255, 255, 0)"> Fazer backup de arquivos</span> em <span style="color:rgb(255, 255, 0)">mídias de armazenamento estáveis</span> (não voláteis)


##### 1.8.2 - Gerenciamento de Armazenamento de Massa

Normalmente os discos usados para armazenar dados que não cabem na memória principal ou dados que devem ser mantidos por um "longo" período de tempo.

O sistema de computação deve fornecer **memória secundária** como backup da **memória principal**.

Grande parte dos programas é armazenada em um disco até ser carregada na memória, programas como :

-  Compiladores
-  Montadores 
-  Processadores de texto
-  Editores
-  Formatadores


> **O sistema operacional é responsável por atividades relacionadas com o gerenciamento de disco, como por exemplo :**

1.  <span style="color:rgb(255, 255, 0)">Gerenciar</span> o <span style="color:rgb(255, 255, 0)">espaço livre</span>
2.  <span style="color:rgb(255, 255, 0)">Alocar espaço</span> de armazenamento
3.  Fazer <span style="color:rgb(255, 255, 0)">scheduling de disco</span> (escalonamento)


	***Obs.:***  <span style="color:rgb(146, 208, 80);font-weight:600">escalonamento de disco</span> é a técnica usada pelo SO para decidir a ordem em que as requisições de leitura e escrita serão atendidas.


A velocidade total de operação de um computador pode depender das **velocidades do subsistema de disco e dos algoritmos que manipulam esse subsistema.**

Existe algumas utilidades para memórias mais lentas e mais baratas (às vezes de maior capacidade) do que a **memória secundária**, como por exemplo :

-  Backups de dados de disco
-  Armazenamento de dados pouco usados
-  Armazenamento de longo prazo


Essas funções podem ser adotadas por dispositivos de <span style="color:rgb(146, 208, 80);font-weight:700">Memória Terciária</span>, sendo eles:

- <span style="color:rgb(255, 255, 0)"> Drives de fita magnética</span> e suas fitas
-  <span style="color:rgb(255, 255, 0)">Drives de CD e DVD</span> e discos

Essas mídias variam entre os formatos <span style="color:rgb(146, 208, 80)">WORM</span> (grava uma vez, lê várias vezes) e <span style="color:rgb(146, 208, 80)">RW</span> (lê e grava).


A **memória terciária** não é crucial para o desempenho do sistema, mas mesmo assim deve ser gerenciada. Alguns sistemas operacionais assumem essa tarefa, enquanto outros deixam o gerenciamento da memória terciária para programas aplicativos.


##### 1.8.3 - Armazenamento em Cache (Caching)

Na medida em que informações são utilizadas, elas são copiadas temporariamente em um sistema de armazenamento mais veloz -- <span style="color:rgb(146, 208, 80)">o cache</span>.

Quando precisamos de informações específicas, primeiro verificamos se ela está no cache. Se estiver, usamos a informação diretamente a partir do cache. Se não estiver, usamos a informação a partir da fonte, inserindo uma cópia no cache supondo que, em breve, ela possa ser necessária novamente.

Como os caches têm tamanho limitado, o<span style="color:rgb(146, 208, 80)"> gerenciamento do cache</span> é um importante problema de projeto. A seleção cuidadosa do tamanho do cache e de uma política de realocação pode resultar em um desempenho muito melhor.


|             Nível             |     |                           1                           |                 2                 |          3           |              4               |           5            |
| :---------------------------: | :-- | :---------------------------------------------------: | :-------------------------------: | :------------------: | :--------------------------: | :--------------------: |
|                               |     |                                                       |                                   |                      |                              |                        |
|             Nome              |     |                     registradores                     |               cache               | memória<br>principal | disco de estado sólido (SSD) |    disco magnético     |
|        Tamanho típico         |     |                        < 1 KB                         |              < 16 MB              |       < 64 GB        |            < 1 TB            |        < 10 TB         |
|  Tecnologia de implementação  |     | memória<br>personalizada<br>com várias<br>portas CMOS | CMOS SRAM em chip ou fora do chip |      CMOS SRAM       |        memória flash         |    disco magnético     |
|    Tempo de acesso<br>(ns)    |     |                      0,25 - 0,5                       |             0,5 - 25              |       80 - 250       |       25.000 - 50.000        |       5.000.000        |
| Taxa de transmissão<br>(MB/s) |     |                   20.000 - 100.000                    |          5.000 - 10.000           |    1.000 - 5.000     |             500              |        20 - 150        |
|        Gerenciado por         |     |                      compilador                       |             hardware              | sistema operacional  |    sistema<br>operacional    | sistema<br>operacional |
|        Coadjuvado por         |     |                         cache                         |       memória<br>principal        |        disco         |            disco             |         disco          |


A transferência de dados entre diferentes níveis de um hierarquia de armazenamento pode ser **explícita ou implícita**.

Por exemplo, a transferência de dados do ***cache para a CPU e os registradores***, é geralmente, uma função do hardware, sem intervenção do sistema operacional.

A transferência de dados de ***disco para a memória*** costuma ser controlada pelo sistema operacional.

###### Migração do Inteiro A do Disco para o Registrador

Em uma estrutura de armazenamento hierárquica, os mesmos dados podem aparecer em diferentes níveis do sistema de armazenamento.

> **Por exemplo :**
>  
	suponha que um inteiro $A$ que tenha que ser incrementado de 1 esteja localizado no arquivo $B$ e o arquivo $B$ resida em **disco magnético**. A operação de incremento é efetuada, sendo emitida, em primeiro lugar, uma operação de I/O para copiar, na **memória principal**, o bloco de disco no qual $A$ reside. 
	Essa operação é seguida pela cópia de $A$ no cache e em um registrador interno.
	Assim, a cópia de $A$ aparece em vários locais. Uma vez que o incremento tenha lugar no registrador interno, o valor de $A$ será diferente nos diversos sistemas de armazenamento. O valor de $A$ será o mesmo somente depois que o novo valor de $A$ seja copiado do registrador interno para o disco magnético.

Em um ambiente de computação em que só um processo é executado de cada vez (**monotarefa**), esse esquema não cria dificuldades. No entanto, em um ambiente **multitarefa**, deve-se ter extremo cuidado para garantir que, se muitos processos quiserem acessar $A$, todos eles obtenham o valor **mais recente** de $A$.

A situação torna-se ainda mais complicada em um ambiente multiprocessador em que, além de manter registradores internos, cada uma das CPUs também contém um cache local.

A tarefa de refletir uma atualização de um valor $A$ em todas as caches quando o valor é atualizado é chamado de <span style="color:rgb(146, 208, 80)">coerência do cache</span>, e, em geral, é um problema do hardware (manipulado abaixo do nível do SO).

Em um ambiente distribuído, a situação torna-se ainda mais complexa (cópias em diferentes computadores).


##### 1.8.4 - Sistemas de I/O

Um dos objetivos de um sistema operacional é ocultar, dos usuários, as peculiaridades de dispositivos de hardware específicos.

Por exemplo, no ***UNIX***, as peculiaridades dos dispositivos de I/O são ocultas de grande parte do próprio sistema operacional pelo <span style="color:rgb(146, 208, 80)">subsistema de I/O</span>, que conta com alguns componentes :

-  Componente de <span style="color:rgb(255, 255, 0)">gerenciamento de memória</span>, que inclui o <span style="color:rgb(255, 255, 0)">uso de buffer, de cache e spooling.</span>
-  Uma <span style="color:rgb(255, 255, 0)">interface genérica</span> para <span style="color:rgb(255, 255, 0)">drivers de dispositivos</span>
-  Drivers para dispositivos de hardware específicos

> ***Spooling :***  Simultaneous Peripheral Operation On Line. É uma técnica usada pelos SOs para gerenciar a entrada e saída (E/S) de dados entre processos e dispositivos periféricos.

Apenas o driver conhece as peculiaridades do dispositivo específico ao qual é atribuído.


#### 1.9 - Proteção e Segurança

Se um sistema de computação tem múltiplos usuários e permite a execução de múltiplos processos, então o acesso aos dados deve ser regulado.

Mecanismos asseguram que **arquivos, segmentos de memória, CPU e outros recursos** possam ser operados apenas pelos processos que receberam autorização apropriada do sistema operacional.

> ***Proteção*** é, portanto, qualquer mecanismo que controle o acesso de processos ou usuários aos recursos definidos por um sistema de computação.

Um sistema **orientado à proteção** fornece meios para a distinção entre o uso autorizado e não autorizado.


Um sistema pode ter proteção adequada e, mesmo assim, estar propenso a falhas e permitir acesso inapropriado.

É responsabilidade da <span style="color:rgb(146, 208, 80)">segurança</span> a defesa de um sistema contra ataques externos e internos.

A prevenção contra alguns desses ataques é considerada uma função do sistema operacional em determinados sistemas, enquanto outros sistemas a deixam para a política adotada ou para um software adicional.

Sistemas geralmente primeiro identifica os usuários, para determinar quem pode fazer o que.

-  Identidades de usuários (<span style="color:rgb(255, 255, 0)">user IDs, IDs de segurança</span>) incluir o nome e número de associados, um por usuário
-  <span style="color:rgb(255, 255, 0)">ID de usuário associado com todos os arquivos</span>, os processos desse usuário para determinar o controle de acesso
-  <span style="color:rgb(255, 255, 0)">Grupo identificador (group ID)</span> permite conjunto de usuários a serem definidos e controles gerenciados, em seguida, também associados a cada processo e arquivo
-  <span style="color:rgb(255, 255, 0)">Escalação de privilégios</span> permite ao usuário mudar a ID com mais direitos


#### 1.10 - Estruturas de Dados do Kernel

Inclui estruturas como:

1.  Listas, Pilhas e Filas
2.  Árvores
3.  Funções e Mapas Hash
4.  Mapas de Bits


# <span style="color:rgb(192, 0, 0)">⚠️ANOTAÇÕES DESSE CAP EM ANDAMENTO⚠️
</span> 
#### 1.11 - Ambientes de Computação

Aqui será abordado uma discussão de como os sistemas operacionais são usados em vários ambientes de computação.

##### 1.11.1 - Computação Tradicional

Antigamente, o ambiente tradicional, ou "ambiente de escritório típico", era composto por PCs conectados a uma rede, com servidores fornecendo serviços de arquivo e impressão. O acesso remoto era complicado e a portabilidade era obtida com o uso de computadores *laptop*. Terminais conectados a mainframes eram predominantes em muitas empresas.

Agora, tecnologias web e a crescente largura de banda da WAN estão estendendo os limites da computação tradicional.

As empresas estabelecem **portais** que fornecem acessibilidade da web aos seus servidores internos. <span style="color:rgb(146, 208, 80)">Computadores em rede (ou clientes magros)</span> -- que, essencialmente, são terminais que entendem a computação baseada na web -- são usados no lugar das estações de trabalho tradicionais, em que mais segurança ou manutenção mais fácil é desejada.

###### Redes domésticas

-  Usado para ser um sistema isolado
-  Modems
-  <span style="color:rgb(255, 255, 0)">Firewall</span> (utilizado para garantir a segurança na rede)
-  Rede


##### 1.11.2 - Computação Cliente-Servidor

Conforme os PCs ficavam mais velozes, poderosos e baratos, os projetistas iam abandonando a arquitetura de sistemas centralizado. Atualmente os terminais conectados a sistemas centralizados estão sendo substituídos por PCs e dispositivos móveis.

Como resultado, muitos dos sistemas atuais agem como <span style="color:rgb(146, 208, 80)">sistemas servidores</span> para atender solicitações geradas por <span style="color:rgb(146, 208, 80)">sistemas clientes</span>. Esse tipo de **sistema distribuído** especializado, é chamado de sistema <span style="color:rgb(146, 208, 80)">cliente-servidor</span>.


Os ***sistemas servidores*** podem ser amplamente categorizados como ***servidores de computação*** e ***servidores de arquivo*** :

-  <span style="color:rgb(146, 208, 80);font-weight:700">Sistema Servidor de Computação</span>

	fornece uma interface para a qual um cliente pode enviar uma solicitação para executar uma ação (por exemplo, ler dados). Em resposta, o servidor executa a ação e envia os resultados ao cliente.

-  <span style="color:rgb(146, 208, 80);font-weight:700">Sistema Servidor de Arquivos</span>

	fornece uma interface com o sistema de arquivos em que os clientes podem criar, atualizar, ler e excluir arquivos.


![[os-image8.png]]


##### 1.11.3 - Computação entre Pares (Peer-To-Peer)

Outra estrutura para um sistema distribuído é o modelo de <span style="color:rgb(146, 208, 80)">sistema entre pares</span> (*P2P*). Nesse modelo, clientes e servidores mão são diferentes um dos outros. Em vez disso, todos os nós do sistema são considerados pares, e <span style="color:rgb(146, 208, 80)">cada um pode atuar como cliente ou servidor</span>, dependendo de estar <span style="color:rgb(255, 255, 0)">solicitando ou fornecendo um serviço</span>.

Em um sistema **cliente-servidor**, o servidor é um <span style="color:rgb(255, 255, 0)">gargalo</span>; mas em um sistema entre **pares**, os serviços podem ser fornecidos por vários nós distribuídos ao longo da rede.

Para participar de um **sistema entre pares**, um nó deve primeiro conectar-se à rede de pares. Uma vez que o nó tenha se conectado à rede, pode começar a fornecer serviços para  -- e solicitar serviços de --  outros nós da rede.


> **A determinação dos serviços que estão disponíveis é feita de uma entre duas formas gerais :**

1.  Quando um nó se conecta a uma rede, ele registra seu serviço em um <span style="color:rgb(146, 208, 80)">serviço de pesquisa centralizado</span> da rede. O resto da comunicação ocorre entre o cliente e o fornecedor do serviço.

2.  Um sistema alternativo não usa serviço de pesquisa centralizado. Em vez disso, um par atuando como cliente deve descobrir qual nó fornece o serviço desejado transmitindo a solicitação do serviço para todos os outros nós da rede. Para suportar essa abordagem, um <span style="color:rgb(146, 208, 80)">protocolo de descoberta</span> deve ser fornecido para permitir que os pares descubram os serviços oferecidos por outros pares da rede.


***Exemplos :***  Torrent, Skype, Napster, Gnutella.

![[os-image9.png]]


##### 1.11.4 - Computação baseada na WEB


> **Características :**

-  Web tornou-se onipresente.
-  PCs dispositivos mais prevalentes.
-  Tornando-se mais dispositivos de rede para permitir acesso à web.
-  Nova categoria de dispositivos para gerenciar o tráfego entre os servidores web similar: <span style="color:rgb(146, 208, 80)">balanceadores de carga</span>.
-  Uso de sistemas operacionais que trabalham somente como clientes, têm evoluído outros que podem ser <span style="color:rgb(146, 208, 80)">clientes e servidores.</span> 


#### 1.12 - Sistemas Operacionais de Código-Fonte Aberto (open-source)

O estudo de ***sistemas operacionais*** foi facilitado pela disponibilidade de uma vasta quantidade de versões de código-fonte aberto.

Os <span style="color:rgb(146, 208, 80)">sistemas operacionais open-source</span> são aqueles disponíveis em formato de <span style="color:rgb(255, 255, 0)">código-fonte</span> e não como <span style="color:rgb(255, 255, 0)">código binário compilado</span>.


> **Exemplos :**

-  GNU / Linux
-  BSD UNIX
-  Sun Solaris

-- -
### Estruturas do Sistema Operacional


Um sistema operacional fornece o ambiente dentro do qual os programas são executados. Internamente, os sistemas operacionais variam muito em sua composição.

Podemos considerar um sistema operacional segundo vários critérios :

1.  Os <span style="color:rgb(255, 255, 0)">serviços</span> que o sistema fornece
2.  A <span style="color:rgb(255, 255, 0)">interface</span> que ele torna disponível para usuários e programadores
3.  Seus <span style="color:rgb(255, 255, 0)">componentes e suas interconexões</span> 


Neste capítulo, será explorado todos os 3 aspectos dos sistemas operacionais, mostrando os pontos de vista de: <span style="color:rgb(146, 208, 80)">usuários, programadores e projetistas</span> de sistemas operacionais.

Consideramos os <span style="color:rgb(255, 255, 0)">serviços que um SO fornece</span>, <span style="color:rgb(255, 255, 0)">como eles são fornecidos</span>, <span style="color:rgb(255, 255, 0)">como são depurados</span> e que <span style="color:rgb(255, 255, 0)">metodologias existem para o projeto desses sistemas</span>. Como os <span style="color:rgb(255, 255, 0)">sistemas operacionais são criados</span> e como um <span style="color:rgb(255, 255, 0)">computador inicia seus sistema operacional.</span> 


###### Objetivos do Capítulo

-  Descrever <span style="color:rgb(146, 208, 80)">os serviços</span> que um SO fornece para <span style="color:rgb(146, 208, 80)">usuários</span>, <span style="color:rgb(146, 208, 80)">processos</span> e <span style="color:rgb(146, 208, 80)">outros sistemas.</span>
-  Discutir diversas formas de <span style="color:rgb(146, 208, 80)">estruturação</span> de um SO.
-  Explicar como os SOs são<span style="color:rgb(146, 208, 80)"> instalados</span> e <span style="color:rgb(146, 208, 80)">personalizados</span> e como são <span style="color:rgb(146, 208, 80)">inicializados</span>.


#### 2.1 - Serviços do Sistema Operacional

Um SO fornece certos serviços para programas e para os usuários desses programas. Os serviços específicos fornecidos diferem, obviamente, de um SO para outro, mas podemos identificar classes comuns.

Esses serviços são fornecidos visando à conveniência do programador, para tornar mais fácil a tarefa de programar.


*A imagem a seguir mostra uma representação dos diversos serviços do sistema operacional e como eles estão relacionados*

![[os-image10.png]]

> **Alguns dos principais serviços do sistema operacional são descritos a seguir :**


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Interface de usuário</span>

	 Quase todos os sistemas operacionais possuem uma interface de usuário (UI - *user interface*). Essa interface pode assumir várias formas.
	 
	 Uma delas é a <span style="color:rgb(255, 255, 0)">interface de linha de comando</span> (CLI - *command-line interface*) que usa comandos de texto e um método para sua entrada.
	 
	 Outra é a <span style="color:rgb(255, 255, 0)">interface batch</span> em que os comandos e suas diretivas de controle são inseridos em arquivos, e esses arquivos são executados.
	 
	 O mais comum é o uso de uma <span style="color:rgb(255, 255, 0)">interface gráfica de usuário</span> (GUI - *graphical user interface*). Nesse caso, a interface é um sistema de janelas com um dispositivo apontador para direcionar o I/O, selecionar a partir de menus e escolher opções e um teclado para entrada de texto.
	 
	 Alguns sistemas fornecem 2 dessas variações ou as 3.


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Execução de programas</span>

	 O sistema deve ser capaz de <span style="color:rgb(255, 255, 0)">carregar um programa na memória</span> e <span style="color:rgb(255, 255, 0)">executar</span> esse programa. O programa deve ser capaz de <span style="color:rgb(255, 255, 0)">encerrar sua execução</span>, normal ou anormalmente (indicando o erro).


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Operações de I/O</span>

	 Um <span style="color:rgb(255, 255, 0)">programa em execução</span> pode <span style="color:rgb(255, 255, 0)">requerer I/O</span>, que pode envolver um <span style="color:rgb(255, 255, 0)">arquivo ou um dispositivo de I/O</span>.
	 
	 Para dispositivos específicos, <span style="color:rgb(255, 255, 0)">funções especiais podem ser desejáveis</span> (como a gravação em um drive de CD ou DVD ou a limpeza de uma tela).
	 
	 Para <span style="color:rgb(255, 255, 0)">eficiência e proteção</span>, os usuários geralmente não podem controlar os dispositivos de I/O diretamente. Portanto, o sistema operacional deve fornecer um meio para executar I/O.


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Manipulação do sistema de arquivos</span>

	 <span style="color:rgb(255, 255, 0)">Ler e gravar</span> de arquivos e diretórios
	 <span style="color:rgb(255, 255, 0)">Criar e apagar</span> arquivos e diretórios
	 <span style="color:rgb(255, 255, 0)">Procurar</span> um arquivo
	 <span style="color:rgb(255, 255, 0)">Listar</span> diretórios
	 Gerenciamento de Permissões


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Comunicações</span>

	 Os processos podem trocar informações entre si, no mesmo computador ou através de uma rede de computadores.
	 
	 As comunicações podem ocorrer via <span style="color:rgb(255, 255, 0)">memória compartilhada</span> ou através de <span style="color:rgb(255, 255, 0)">troca de mensagens</span>.


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Detecção de erros</span>

	 Os erros podem ocorrer na CPU, na memória, em dispositivos I/O e em programas de usuários.
	 
	 Para cada tipo de erro, o Sistema Operacional deve tomar a medida apropriada para garantir o processamento correto e consistente.
	 
	 <span style="color:rgb(255, 255, 0)">Recursos de depuração</span> podem melhorar muito as possibilidades de uso eficiente do sistema pelo usuário e pelo programador.


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Alocação de recursos</span>

	 Quando <span style="color:rgb(255, 255, 0)">múltiplos usuários ou jobs</span> estão em execução simultaneamente, os recursos devem ser alocados para cada um deles.
	 
	 Tipos de recursos:
	 -  ciclos de CPU, memória principal e armazenamento de arquivos possuem um <span style="color:rgb(255, 255, 0)">código de alocação especial</span>
	-  <span style="color:rgb(255, 255, 0)">dispositivos de I/O</span> possuem um <span style="color:rgb(255, 255, 0)">código mais genérico</span> de requisição e liberação de recurso


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Contabilização</span>

	 Quais usuários estão usando os recursos, que tipos de recursos estão sendo utilizados, a <span style="color:rgb(255, 255, 0)">quantidade.</span>
	 
	 Essa monitoração pode ser usada a título de **contabilização** ou simplesmente para <span style="color:rgb(255, 255, 0)">acúmulo de estatísticas de uso.</span> 


-  <span style="color:rgb(146, 208, 80);font-weight:600;font-style:italic">Proteção e segurança</span>

	 Os donos das informações armazenadas em um <span style="color:rgb(255, 255, 0)">sistema multiusuário ou sistema de rede de computadores</span> devem ser capazes de <span style="color:rgb(255, 255, 0)">controlar o uso</span> das informações.
	 
	 Processos concorrentes não devem interferir entre si.
	 
	 A <span style="color:rgb(255, 255, 0)">proteção</span> envolve a garantia de que todos os acessos aos recursos do sistema sejam <span style="color:rgb(255, 255, 0)">controlados.</span>
	 
	 A <span style="color:rgb(255, 255, 0)">segurança</span> do sistema requer a <span style="color:rgb(255, 255, 0)">autenticação do usuário</span>, a proteção de dispositivos contra tentativas de <span style="color:rgb(255, 255, 0)">acesso ilegal.</span>
	 
	 Para um sistema estar protegido e seguro, precauções devem ser tomadas em toda a sua extensão.


![[os-image11.png]]


#### 2.2 - Interface entre o Usuário e o Sistema Operacional

Serão abordados a <span style="color:rgb(146, 208, 80)">interface de linha de comando</span> (ou interpretador de comandos) e a <span style="color:rgb(146, 208, 80)">interface gráfica de usuário</span> (GUI).


##### 2.2.1 - Interpretadores de Comandos

Também conhecido como *CLI* (client line interface) ou interface de linha de comando.

Essa interface permite a entrada diretamente por um comando. Alguns SOs incluem o interpretador de comandos no ***kernel***. Outros, como o <span style="color:rgb(146, 208, 80)">Windows e o UNIX</span>, tratam o interpretador de comandos como um programa especial que está sendo executado quando um job é iniciado ou quando um usuário fez login pela primeira vez.

Em sistemas que permite a escolha entre vários interpretadores de comandos, são conhecidos como <span style="color:rgb(146, 208, 80);font-weight:600;text-decoration:underline">shells</span>.

Principal função:  capturar um comando do usuário e executá-lo.

Esse comandos podem ser implementados de 2 maneiras gerais :

1.  <span style="color:rgb(255, 255, 0)">Comandos Internos:</span>  o próprio interpretador de comandos contém o código que executa o comando.
   
	   ***Exemplos :***  
		   `cd`, `echo`, `pwd` (Linux). 
		   `dir`, `cls`, `cd` (Windows CMD).

1.  <span style="color:rgb(255, 255, 0)">Comandos Externos:</span>  implementa a maioria dos comandos por meio de programas de sistema. Nesse caso, o interpretador de comandos definitivamente não entende o comando; ele simplesmente usa o comando para identificar um arquivo a ser carregado na memória e executado.
   
	   ***Exemplos :***
		   `ls`, `cat`, `grep` (Linux).
		   `ping`, `ipconfig` (Windows).


> **Vantagem de comandos externos:**  implementações futuras não necessitam de modificações no ***shell***.


##### 2.2.2 - Interfaces Gráficas de Usuário

Uma estratégia de comunicação com o sistema operacional é por meio de uma <span style="color:rgb(146, 208, 80)">interface gráfica de usuário</span> amigável ou GUI (*graphical user interface*).

Ela possui um sistema de janelas e menus baseado em mouse, caracterizado por uma simulação de <span style="color:rgb(146, 208, 80)">área de trabalho</span>.

As interfaces gráficas de usuário surgiram, em parte, por causa de pesquisas que ocorreram no início dos anos 1970, no centro de pesquisas <span style="color:rgb(255, 255, 0)">Xerox PARC</span>. A primeira GUI surgiu no computador <span style="color:rgb(255, 255, 0)">Xerox Alto, em 1973.</span>

No entanto, as interfaces gráficas de usuário disseminaram-se nos anos 1980, com o advento dos computadores <span style="color:rgb(255, 255, 0)">Apple Macintosh</span>.


Muitos sistemas incluem interfaces CLI e GUI :

-  A primeira versão do Windows baseava-se em GUI adicionada ao shell de comandos CLI MS-DOS.
-  MAC OS X com GUI "Aqua" implementada com kernel UNIX
-  Sistemas Linux são tradicionalmente CLI, mas vários GUIs estão disponíveis (CDE e X-Windows)
-  Outras para o Linux em código-fonte aberto como o KDE e o Gnome


Em aparelhos móveis, a interação com a interface gráfica é dada por meio de <span style="color:rgb(146, 208, 80)">tela sensível ao toque</span> (*touchscreen*).


#### 2.3 - Chamadas de Sistema

As chamadas de sistema fornecem uma<span style="color:rgb(146, 208, 80)"> interface com os serviços disponibilizados por um sistema operacional.</span>

Geralmente, essas chamadas estão disponíveis como rotinas escritas em C e C++, embora certas tarefas de baixo nível possam precisar ser escritas usando instruções em linguagem de montagem.


Mesmo programas simples podem fazer uso intenso do sistema operacional, que executam milhares de chamadas de sistema por segundo.

A maioria dos programadores nunca vê esse nível de detalhe e projetam programas de acordo com uma <span style="color:rgb(146, 208, 80)">interface de programação de aplicações</span> (*API*).

-  A <span style="color:rgb(146, 208, 80)">API</span> especifica um conjunto de funções que estão disponíveis para um programador de aplicações, incluindo os parâmetros que são passados a cada função e os valores de retorno que o programador pode esperar.

As 3 APIs mais comuns, disponíveis para programadores de aplicações são:

1.  <span style="color:rgb(146, 208, 80)">API Windows</span> para sistemas Windows
2.  <span style="color:rgb(146, 208, 80)">API POSIX</span> para sistemas baseados em POSIX
3.  <span style="color:rgb(146, 208, 80)">API Java</span> para programas que são executados na máquina virtual Java


O programador acessa uma API por meio de uma biblioteca de códigos fornecida pelo sistema operacional. **Ex.:**  `libc` na linguagem C.

Em segundo plano, as funções que compõem uma API invocam tipicamente as chamadas de sistema reais em nome do programador de aplicações.

> **Exemplo :**

-  A função ***CreateProcess( )*** do Windows na verdade invoca a chamada de sistema ***NTCreateProcess( )*** no kernel do Windows

###### *Razões para uso de APIs*

-  <span style="color:rgb(146, 208, 80)">Portabilidade</span>:  o programador de aplicações espera que seu programa seja compilado e executado em qualquer sistema que dê suporte à mesma API.

-  <span style="color:rgb(146, 208, 80)">Simplicidade</span>:  chamadas de sistema são mais detalhadas e difíceis de manipular do que a API.


Na maioria das linguagens de programação, o sistema de suporte ao tempo de execução fornece uma <span style="color:rgb(146, 208, 80)">interface de chamada de sistema</span>, que serve como uma ponte para as chamadas de sistema disponibilizadas pelo sistema operacional.

Cada **chamada de sistema** tem um número associado e a interface de chamada de sistema mantém uma tabela indexada de acordo com esses números.

A interface de chamada de sistema invoca a chamada de sistema desejada no Kernel e retorna o status da chamada e qualquer valor de retorno associado.

O invocador não necessita ter conhecimento sobre como a chamada de sistema foi implementada, ele somente precisa seguir a API e saber o que o sistema operacional fará como resultado da execução da chamada.

A maioria dos detalhes da interface do sistema operacional é <span style="color:rgb(255, 255, 0)">oculta do programador pela API</span> e <span style="color:rgb(255, 255, 0)">gerenciada pela biblioteca de suporte ao tempo de execução.</span> 


###### *Tipos de passagem de parâmetros*

São 3 métodos gerais que são usados para passar parâmetros aos sistema operacional:

1.  Mais simples:  passagem de parâmetro em <span style="color:rgb(146, 208, 80)">registradores</span>.
2.  Parâmetros armazenados em um <span style="color:rgb(146, 208, 80)">bloco ou tabela</span> na memória
	- endereço do bloco é passado como parâmetro em um registrador
	- <span style="color:rgb(255, 255, 0)">Linux e Solaris</span> 

3.  Incluído na <span style="color:rgb(146, 208, 80)">pilha</span> pelo programa e extraídos da pilha pelo SO.
4.  Métodos de blocos e pilhas não limitam o número ou o tamanho de parâmetros passados ao SO.


#### 2.4 - Tipos de Chamadas de Sistema

As chamadas de sistema podem ser agrupadas em 6 categorias principais:

1.  Controle de Processos
2.  Manipulação de Arquivos
3.  Manipulação de Dispositivos
4.  Manutenção de Informações
5.  Comunicações
6.  Proteção

![[os-image12.png]]
###### Exemplos de Chamadas de Sistema do Windows e UNIX


-  <span style="color:rgb(146, 208, 80)">Controle de Processos:</span>
  
  ```bash
  --Windows
  
  CreateProcess()
  ExitProcess()
  WaitForSingleObject()
  
  --UNIX
  
  fork()
  exit()
  wait()
  ```

  -  <span style="color:rgb(146, 208, 80)">Manipulação de Arquivos:</span>

```bash
  --Windows
  
  CreateFile()
  ReadFile()
  WriteFile()
  CloseHandle()
  
  --UNIX
  
  open()
  read()
  write()
  close()
  ```

- <span style="color:rgb(146, 208, 80)"> Manipulação de Dispositivos:</span>

```bash
  --Windows
  
  SetConsoleMode()
  ReadConsole()
  WriteConsole()
  
  --UNIX
  
  ioctl()
  read()
  write()
  ```

-  <span style="color:rgb(146, 208, 80)">Manutenção de Informações:</span>

```bash
  --Windows
  
  GetCurrentID()
  SetTimer()
  Sleep()
  
  --UNIX
  
  getpid()
  alarm()
  sleep()
  ```

-  <span style="color:rgb(146, 208, 80)">Comunicações</span>:

```bash
  --Windows
  
  CreatePipe()
  CreateFileMapping()
  MapViewOfFile()
  
  --UNIX
  
  pipe()
  shm_open()
  mmap()
  ```

-  <span style="color:rgb(146, 208, 80)">Proteção</span>:

```bash
  --Windows
  
  SetFileSecurity()
  InitializeSecurityDescriptor()
  SetSecurityDescriptorGroup()
  
  --UNIX
  
  chmod()
  umask()
  chown()
  ```


##### 2.4.1 - Controle de Processos

-  Interpretador de comandos que é invocado quando o computador é iniciado
-  Não cria um novo processo
-  O programa é carregado na memória, gravando sobre grande parte de si próprio, para dar ao programa o máximo de memória possível
-  Em seguida, posiciona o ponteiro de instruções para a primeira instrução do programa


#### 2.5 - Programas de Sistema

