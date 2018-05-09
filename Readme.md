# Locator Used by Chiara and Andrea (L.U.C.A)

**Notice: sniffer program have to be executed as root!**

### Software requirements
* https://www.elinux.org/RPi_Bluetooth_LE
* http://ianharvey.github.io/bluepy-doc/
* http://flask.pocoo.org/
* https://medium.com/@erinus/mosquitto-paho-mqtt-python-29cadb6f8f5c
* https://github.com/eclipse/paho.mqtt.python
* https://docs.python.org/2/library/json.html
* https://github.com/python-telegram-bot/python-telegram-bot

### REST API
||GET|POST|DELETE|
|---|---|---|---|
|**/rooms/**|Get the list of all rooms|-|-|
|**/rooms/[rid]**|-|Create new room (given as parameter)|Delete a room (given as parameter)|
|**/readings/[bId]**|Get the list of readings about a beacon (grouped by room)|-|Delete ALL readings about a beacon|
|**/people/[rId]**|Get the list of people (iBeacon) in the selected room|-|-|

## TODO
- [ ] Dormire :lollipop:
- [x] ~chiedere la macchina virtuale al chessa~ :disappointed:
- [x] sniffer  : leggere il file di configurazione per settare le variabili
- [X] sniffer  : inviare al broker un messaggio formattato json contenente macAddrBeacon, idRaspberry, RSSI, timestamp :collision:
- [X] analyzer : registrarlo al topic mqtt e raggruppare i dati per macAddrBeacon[].idRaspberry[]
- [ ] analyzer : trovare un algoritmo di triangolazione (leggere bene su RSSI distanza stimata), per esempio media pesata con maggior peso alla stazione da cui abbiamo ricevuto più messaggi (perché magari le altre sono fuori portata / al di là di un ostacolo) , varianza :tractor:
- [ ] RESTful : scrivere il API servizio (soprattutto pensare alla fase di installazione ed aggiunta di nuovi dispositivi / attori)
