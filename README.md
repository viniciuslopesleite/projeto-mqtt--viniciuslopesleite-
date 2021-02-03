# projeto-mqtt--viniciuslopesleite-

 
 #include <PubSubClient.h>

#include <PubSubClient.h>
#include <UIPEthernet.h>
#include <utility/logging.h>
#include <SPI.h>


//Define o endereço MAC que será utilizado
byte mac[] = {0x00,0xE0,0x4C,0x77,0x37,0xDC};
int pino2 = 2;
bool estado_sensor;
boolean mensagem;

//Inicia o cliente Ethernet
EthernetClient client;

PubSubClient mqttClient(client);

void setup() {
    //Inicia o controlador Ethernet e solicita um IP para o servidor de DHCP
    Ethernet.begin(mac);
    

    //Inicia o monitor Serial
    Serial.begin(9600);
    pinMode(pino2, INPUT_PULLUP);

    mqttClient.setServer("54.144.190.205", 1883);

    //Exibe no Monitor Serial as informações sobre o IP do Arduino
    Serial.print("O IP do Arduino e: ");
    Serial.println(Ethernet.localIP());

    //Exibe no Monitor Serial as informações sobre a Máscara de Rede do Arduino
    Serial.print("A Mascara de Rede do Arduino e: ");
    Serial.println(Ethernet.subnetMask());

    //Exibe no Monitor Serial as informações sobre o Gateway do Arduino
    Serial.print("O Gateway do Arduino e: ");
    Serial.println(Ethernet.gatewayIP());

    //Exibe uma linha em branco
    Serial.println("");

}

void loop() {

      mqttClient.connect("vinicius");
      estado_sensor = digitalRead(pino2);

    if (estado_sensor == 0)

    {

      Serial.println("o rack esta fechado");
      mensagem = mqttClient.publish("vinicius-t", "Fechado");
      Serial.println(mensagem);
      mqttClient.loop();
      delay(500);
    }

    else

    {

      Serial.println("o rack esta aberto");
      mensagem = mqttClient.publish("vinicius-t", "Aberto");
      Serial.println(mensagem);
      mqttClient.loop();
      delay(500);
    }
    
     

    
}
