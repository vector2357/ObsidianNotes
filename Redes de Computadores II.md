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