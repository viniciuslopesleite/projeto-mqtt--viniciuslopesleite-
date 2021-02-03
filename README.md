O objetivo desse projeto é utilizar um Arduino Uno mais um Sensor Magnético para monitorar se a porta de um Rack
de Rede está *ABERTO* ou *FECHADO*, enviar essa informação via Internet utilizando o protocolo MQTT (Message
Queuing Telemetry Transport) para um servidor MQTT hospedado na *Amazon Web Service* (AWS) e exibir a informação
em um cliente MQTT [MQTT DASH](https://play.google.com/store/apps/details?id=net.routix.mqttdash&hl=pt_BR&gl=US) instalado em um Smartphone, conforme imagem abaixo.

![]( https://camo.githubusercontent.com/7beef2d4780d87a603d7de49b2da0467c8537dff96575b628a04bd4010ebb1cc/68747470733a2f2f692e696d6775722e636f6d2f4d576870586b562e706e67)

Foram utilizadas as seguintes bibliotecas:
- [UIPEthernet](https://github.com/UIPEthernet/UIPEthernet)
- [PubSubClient](https://github.com/knolleary/pubsubclient)

*Materiais utilizados*

- Arduino Uno
- Módulo Ethernet (ENC28J60)
- Sensor Magnético (MC-38)
- Jumpers

Circuito

![]( https://camo.githubusercontent.com/ad1da211b35b60b23fb095a64e76dc6504d0c3229e853bd82a69a4d5d27bbb88/68747470733a2f2f692e696d6775722e636f6d2f594947477453472e706e67)


Autor: Vinicius Lopes Leite

[Gmail] viniciuslopesleite19@gmail.com

[Linkedin] https://www.linkedin.com/in/vinicius-lopes-leite-65721b204
