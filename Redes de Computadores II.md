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

   Equivalente às camadas Física e Enlace do OSI. Cuida do hardware e protocolos de comunicação.

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

   É o modo de transmissão em sentido duplo ou bidirecional simultâneo. Assim, cada extremidade da linha pode emitir e receber ao mesmo tempo, o que significa que a banda concorrida está dividida por dois para cada sentido de emissão dos dados.  
   Exemplo: Celular.