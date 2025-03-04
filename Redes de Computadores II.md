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


### Fluxo de Transmissão de Dados


