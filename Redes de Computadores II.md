-- -

### Modelos e Camadas


Os **modelos em redes de computadores** são estruturas conceituais que descrevem como os dispositivos se comunicam em uma rede. Eles ajudam a padronizar a comunicação, garantindo que diferentes sistemas possam interagir de maneira eficiente. Esses modelos são divididos em **camadas**, onde cada camada tem funções específicas relacionadas à transmissão e recepção de dados.


#### Modelo OSI (Open Systems Interconnection)

O **modelo OSI** foi desenvolvido pela **ISO (International Organization for Standardization)** e é um modelo **teórico** que define **sete camadas** para a comunicação em redes:

1. <span style="color:rgb(255, 255, 0)">FÍSICA</span>

   Define aspectos elétricos e físicos do hardware (cabos, conectores, sinais).

2. <span style="color:rgb(255, 255, 0)">ENLACE DE DADOS</span> 

   Garante que os dados sejam transmitidos sem erros entre os dispositivos conectados diretamente.

3. <span style="color:rgb(255, 255, 0)">REDE</span> 

   Define roteamento e endereçamento como por exemplo no caso do **IP**.

4. <span style="color:rgb(255, 255, 0)">TRANSPORTE</span> 

   Garante entrega confiável e ordenada como no caso do **TCP**.

5. <span style="color:rgb(255, 255, 0)">SESSÃO</span> 

   Gerencia conexões entre aplicações.

6. <span style="color:rgb(255, 255, 0)">APRESENTAÇÃO</span> 

   Cuida da formatação e criptografia dos dados.

7. <span style="color:rgb(255, 255, 0)">APLICAÇÃO</span> 

   Interação com o usuário como por exemplo protocolos como: **HTTP, FTP**.


#### Modelo TCP/IP

O **modelo TCP/IP** é o padrão **prático** utilizado na Internet e possui **quatro camadas**, que correspondem a funções do modelo OSI:

1. <span style="color:rgb(146, 208, 80)">ACESSO À REDE</span> 

   Equivalente às camadas Física e Enlace do OSI. Cuida do hardware e protocolos de comunicação. Exemplos de Protocolos: 
   **IEEE 802.3 - CSMA/CD (Carrier Sense Multiple Access/Colision Detection) - Ethernet**
   **IEEE 802.11 - CSMA/CA (Carrier Sense Multiple Access/Colision Avoidance) - WiFi**   
2. <span style="color:rgb(146, 208, 80)">INTERNET</span> 

   Responsável pelo **roteamento** e **endereçamento** (usa o protocolo **IP**).

3. <span style="color:rgb(146, 208, 80)">TRANSPORTE</span> 

   Garante confiabilidade da comunicação (exemplo: **TCP e UDP**).

4. <span style="color:rgb(146, 208, 80)">APLICAÇÃO</span> 

   Equivalente às camadas superiores do OSI e inclui protocolos como **HTTP**, **FTP** e **SMTP**.


#### Diferença Principal entre OSI e TCP/IP


| Característica    | Modelo OSI                | Modelo TCP/IP                  |
| :---------------- | :------------------------ | :----------------------------- |
|                   |                           |                                |
| Uso               | Teórico                   | Prático                        |
| Número de Camadas | 7                         | 4                              |
| Abordagem         | Explicativa e padronizada | Implementável e eficiente      |
| Desenvolvido por  | ISO                       | Departamento de Defesa dos EUA |


### Modos de Transmissão de Dados


Os modos de transmissão de dados são basicamente o sentido pelo qual os dados poderão ser transmitidos em uma conexão.

1. <span style="color:rgb(146, 208, 80)">Simplex</span> 

   É o modo de transmissão em sentido único ou unidirecional, caracteriza-se em uma ligação na qual os dados circulam num só um sentido, ou seja do emissor para o receptor.  
   Exemplo: Rádio, TV.

2. <span style="color:rgb(146, 208, 80)">Half-Duplex</span> 

   É o modo de transmissão em sentido duplo em função do tempo, não simultâneo. Assim, com este tipo de ligação, cada extremidade da ligação emite por sua vez.  
   Exemplo: Nextel.

3. <span style="color:rgb(146, 208, 80)">Full-Duplex</span>

   É o modo de transmissão em sentido duplo ou bidirecional simultâneo. Assim,  cada extremidade da linha pode emitir e receber ao mesmo tempo, o que significa que a banda concorrida está dividida por dois para cada sentido de emissão dos dados.  
   Exemplo: Celular.


### Endereçamento IP (v4)


O endereçamento IP é um sistema de identificação e localização de dispositivos conectados a uma rede de computadores. Ele é baseado no protocolo de internet (IP), que é um conjunto de regras que define o formato de dados enviados pela internet.

O endereço IP é dado por um valor binário de <span style="color:rgb(255, 255, 0)">32 bits</span> e representado visualmente por 4 **valores decimais** de <span style="color:rgb(255, 255, 0)">1 byte</span> (**ou octeto**) cada e separados por **ponto**.

> **Exemplo**

$$192.168.0.1$$

O endereço IP é acompanhado sempre por uma <span style="color:rgb(146, 208, 80)">Máscara de Rede</span>, que representa quais bits do endereço são de **Redes** e quais são de **Hosts**, no qual os bits mais significativos (à esquerda) são dados por **bits 1** e representam os bits reservados para Redes, enquanto **bits 0** (à direita) representam os bits do endereço reservado para Hosts.

Vale destacar que endereços Hosts apenas com <span style="color:rgb(192, 0, 0)">bits 0</span> não são válidos, uma vez que são utilizados apenas como identificador de Rede. Hosts apenas com <span style="color:rgb(146, 208, 80)">bits 1</span> também não são válidos, umas vez que são utilizados como propagação **Broadcast**.

Existem 4 classes de IP que definem os limites de endereçamento e as máscaras associadas aos endereço. São elas :

-- -
#### <span style="color:rgb(146, 208, 80)">Classe A</span> :

Máscara de Rede Classe A:

	255.0.0.0
	
	REDE.HOST.HOST.HOST

**Endereço IP:**  na classe A, endereços IP têm por padrão o primeiro bit **zerado**. Dessa forma, o intervalo válido de redes classe A é:

	1.x.x.x
	
	...
	
	126.x.x.x


> **Observação :**  o endereço IP `127.x.x.x` é um endereço reservado para <span style="color:rgb(255, 255, 0)">LOOPBACK</span>,   que é usado para testar conectividade de rede em um dispositivo, sem a necessidade de uma conexão externa. Também conhecido como <span style="color:rgb(146, 208, 80)">LOCALHOST</span>.


- ***Rede Privada***

  `10.x.x.x`

-- -
#### <span style="color:rgb(146, 208, 80)">Classe B</span> :

Máscara de Rede Classe B:

	255.255.0.0
	
	REDE.REDE.HOST.HOST

**Endereço IP:**  na classe B, endereços IP têm por padrão o **primeiro bit 1 e o segundo bit 0**. Dessa forma, o intervalo válido de redes classe B é:

	128.0.x.x
	
	...
	
	191.255.x.x


- ***Rede privada***

  `172.16.x.x`
  `172.17.x.x`

  `...`

  `172.31.x.x`

-- -

#### <span style="color:rgb(146, 208, 80)">Classe C</span> :

Máscara de Rede Classe C:

	255.255.255.0
	
	REDE.REDE.REDE.HOST

**Endereço IP:**  na classe C, endereços IP têm por padrão os **dois primeiros bits, 1**. Dessa forma, o intervalo válido de redes classe C é:

	192.0.0.x
	
	...
	
	223.255.255.x


- ***Rede privada***

  `192.168.0.x`
  `192.168.0.x`

  `...`

  `192.168.255.x`

-- -

#### <span style="color:rgb(146, 208, 80)">Classe D</span> :

A classe D foi criada com o intuito de enviar pacotes por propagação Multicast.

>***Multicast***:  é uma técnica de comunicação em redes de computadores que permite enviar uma mensagem para vários destinatários de uma só vez. É uma forma de distribuição de tráfego de rede, também conhecida como rede multicast.

**Endereço IP:**  os endereços IP da classe D têm os quatro bits mais significativos em 1-1-1-0. Dessa forma, o intervalo válido de redes classe D é:

	224.0.0.0
	
	...
	
	239.255.255.255

-- -

#### DHCP (Dynamic Host Configuration Protocol)

É um protocolo que atribui endereços IP a dispositivos de uma rede, de forma automática.

#### Sub-Redes e CIDR (Classless Inter-Domain Routing)


**CIDR** é um método de alocação de endereços IP que permite especificar o tamanho de uma rede e alocar <span style="color:rgb(255, 255, 0)">sub-redes</span>.

>**Sub-Redes:**  uma sub-rede é uma rede menor dentro de uma rede maior. Ela é uma técnica de segmentação que permite dividir uma rede de computadores em partes menores e isoladas.


***Máscara de sub-rede***

A máscara de sub-rede é um conjunto de 32 bits que separa um endereço IP em rede, sub-rede e host. Dessa forma, a sub-rede é representado por **bits 1** também assim como o endereço de rede, de tal forma que esteja entre 0 e 255. Exemplos :

| Classe | Endereço | N. de Hosts | Netmask (Binary)                    | Netmask (Decimal) |
| :----- | :------- | :---------- | ----------------------------------- | ----------------- |
|        |          |             |                                     |                   |
| CIDR   | /4       | 240,435,456 | 11110000 00000000 00000000 00000000 | 240.0.0.0         |
| CIDR   | /9       | 8,388,608   | 11111111 10000000 00000000 00000000 | 255.128.0.0       |
| CIDR   | /26      | 64          | 11111111 11111111 11111111 11000000 | 255.255.255.192   |

#### Tabela de Roteamento


A **tabela de roteamento** é uma estrutura fundamental em **redes de computadores** que **direciona pacotes de dados** para seus destinos apropriados. Ela é usada por **roteadores e gateways** para **determinar o próximo salto** (next hop) no caminho até o destino final de um pacote.

Cada entrada na tabela de roteamento contém várias informações para definir como os pacotes devem ser encaminhados. As principais colunas de uma tabela de roteamento incluem:


| **Destino**      | **Máscara de Sub-rede** | **Gateway (Próximo Salto)** | **Interface de Saída** | **Métrica** |
| ---------------- | ----------------------- | --------------------------- | ---------------------- | ----------- |
| 192.168.1.0      | 255.255.255.0           | 0.0.0.0 (Rede Local)        | eth0                   | 1           |
| 10.0.0.0         | 255.0.0.0               | 192.168.1.1                 | eth1                   | 5           |
| 172.16.0.0       | 255.240.0.0             | 192.168.1.2                 | eth2                   | 3           |
| 0.0.0.0 (Padrão) | 0.0.0.0                 | 192.168.1.254               | eth0                   | 10          |


1. <span style="color:rgb(146, 208, 80)">Destino:</span>  A rede ou IP específico para onde os pacotes serão enviados.

2. <span style="color:rgb(146, 208, 80)">Máscara de Sub-rede:</span>  Define o tamanho da rede de destino.

3. <span style="color:rgb(146, 208, 80)">Gateway (Próximo Salto):</span>  Se o destino não estiver diretamente conectado, o pacote é enviado para este endereço intermediário.

4. <span style="color:rgb(146, 208, 80)">Interface de Saída:</span>  A interface de rede pela qual o pacote será transmitido (ex.: `eth0`, `wlan0`).

5. <span style="color:rgb(146, 208, 80)">Métrica:</span>  Indica o **custo da rota**; quanto menor, melhor. O sistema escolhe a **rota com menor métrica** caso existam múltiplos caminhos.


### Cisco Packet Tracer


Cisco Packet Tracer é um software de simulação de redes de computadores de modo virtual. Usaremos ele para entender vários conceitos, estruturas e configurações de Redes de Computadores na prática.

#### Dispositivos de Redes

As redes de computadores utilizam dispositivos de rede para interligar máquinas e permitir a comunicação eficiente entre elas. Entre os principais dispositivos, temos roteadores, switches, hubs e access points.

1. <span style="color:rgb(0, 176, 240)">Roteador (Router)</span>

   Um **roteador** é um dispositivo responsável por conectar redes diferentes e direcionar o tráfego de dados entre elas. Ele opera na **Camada 3 (Rede) do modelo OSI**, utilizando endereços **IP** para encaminhar pacotes de dados.

   - ***Para que serve?***

     - Conectar redes locais (**LANs**) à Internet.
     - Direcionar pacotes de dados entre redes distintas.
     - Criar **redes domésticas e empresariais**, distribuindo o acesso à Internet.
     - Aplicar **segurança**, como firewall e filtragem de pacotes.

   - ***Como funciona?***

     - O roteador recebe pacotes de dados e examina seu **endereço IP de destino**.
     - Com base em sua **tabela de roteamento**, decide para onde enviar o pacote.
     - Encaminha os pacotes para a rede correta, garantindo que os dados cheguem ao destino certo.


2. <span style="color:rgb(0, 176, 240)">Switch</span> 

   Um **switch** é um dispositivo que interconecta dispositivos dentro de uma mesma **rede local (LAN)**, operando na **Camada 2 (Enlace) do modelo OSI**. Ele usa **endereços MAC** para encaminhar os dados divididos em pacotes, processo chamado de **comutação**. Portanto, o switch também é conhecido como **comutador**.

   - ***Para que serve?***

     - Criar redes locais eficientes.
     - Reduzir congestionamento na rede, pois envia dados apenas ao destinatário correto.
     - Melhorar a segurança e a velocidade da comunicação entre dispositivos.

   - ***Como funciona?***

     - Quando um dispositivo envia um quadro de dados, o switch lê o **endereço MAC de destino**.
     - Ele verifica em sua **tabela de endereços MAC** para saber qual porta usar para encaminhar o dado.
     - Envia o pacote diretamente para o dispositivo correto, sem interferir nos outros.


3. <span style="color:rgb(0, 176, 240)">Hub</span> 

   Um **hub** é um dispositivo que conecta vários computadores dentro de uma rede local, mas ao contrário do switch, ele **não gerencia o tráfego de dados**. Ele funciona na **Camada 1 (Física) do modelo OSI**.

   - ***Para que serve?***

     - Conectar vários dispositivos dentro de uma LAN.
     - Permitir que máquinas se comuniquem entre si.
     - Usado em redes simples, mas menos eficiente que o switch.

   - ***Como funciona?***

     - Quando um computador envia um pacote de dados, o hub **replica essa informação para todos os dispositivos conectados**.
     - Apenas o destinatário correto aceita o pacote, mas todos os outros recebem a mesma informação.
     - Isso gera **tráfego desnecessário**, podendo diminuir a eficiência da rede.


4. <span style="color:rgb(0, 176, 240)">Access Point (AP)</span> 

   Um **Access Point (AP)** é um dispositivo que permite que dispositivos **se conectem a uma rede sem fio (Wi-Fi)**. Ele funciona na **Camada 2 (Enlace) do modelo OSI**.

   - ***Para que serve?***

     - Criar uma rede Wi-Fi para conectar dispositivos sem fio.
     - Expandir o alcance de uma rede sem fio existente.
     - Melhorar a cobertura e reduzir pontos cegos em redes Wi-Fi.

   - ***Como funciona?***

     - O **Access Point** está conectado via cabo a um roteador ou switch.
     - Ele emite um **sinal Wi-Fi**, permitindo que dispositivos móveis se conectem sem fio.
     - Atua como uma **ponte** entre os dispositivos Wi-Fi e a rede cabeada.