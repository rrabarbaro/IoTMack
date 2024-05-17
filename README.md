# IoTMack
Projeto de objetos inteligentes conectados
Link URL de demonstração: https://youtu.be/6xskkNbH3k4

Descrição do projeto:
Através da utilização do Arduino foi possível a realizar o desenvolvimento do código e enviá-lo para a placa ESP8266 que é parte do protótipo. Através do código foram definidas as portas da placa em que os componentes foram conectados, definidos os parâmetros da rede WiFi que é conectada através do método MQTT, bem como a lógica de conexão, em seguida foi desenvolvido a lógica de funcionamento dos leds, sendo o led vermelho + led azul da placa respondendo diretamente aos comandos de subscribe e o led amarelo respondendo ao sensor que envia os dados de fotossensibilidade ao dispositivo, graças a conexão WiFi com o protótipo, permitindo que a partir da lógica a luz amarela fique acesa quando a fotossensibilidade for menor que o padrão definido no código.
A partir do momento que o usuário realiza o envio da mensagem subscribe de valor ‘1’ inscrito no tópico inTopic, através do método MQTT, o sistema apaga a luz vermelha da placa e acende a luz azul brevemente, logo retornando após o ping, deixando claro para o usuário através da sinalização de luz que ele deve tomar a medicação. Esta sinalização enviada através de mensagem pelo MQTT pode ser repetida quantas vezes forem necessárias.
Em paralelo, o sensor de fotossensibilidade está medindo a quantidade de luz emitida e quando for menor que ‘100’, o dispositivo comunicará ao protótipo que o led amarelo deve ser aceso, desta forma o paciente terá visibilidade de onde se encontra a medicação.

Lista de hardware e softwares:
- Método MQTT
- Software Tinkercad
- Arduino IDE
- Resistor 1K 1/4W
- Sensor Fotoresistor LDR
- Placa NodeMCU ESP8266
- Cabo USB
- Kit Jumper Premium Macho x Macho - 30 Fios
- Protoboard 830 Pontos
- Protoboard 400 Pontos
- Led Difuso
- Software MQTTx

Passos necessários para implementação:
1. Faça download da IDE Arduino
2. Faça download do MQTTx
3. Monte o protótipo de acordo com a documentação disponível neste repositório
4. Instale o driver da placa ESP8266 para que seja possível a leitura do placa via usb
5. Na IDE Arduino crie uma nova sketch com o código baixado
6. Com a placa conectada envie o código para a placa
7. Ligue a conexão com a porta 1883 através do MQTTx
8. O projeto está pronto para ser utilizado

* Documentação mosquitto: https://mosquitto.org/documentation/
* Documentação arduino: https://docs.arduino.cc/
* Documentação placa ESP8266: https://arduino-esp8266.readthedocs.io/en/latest/
