# meshtastic-node-documentation

Dies ist eine mögliche Variante offgrid Meshtastic Knoten zu bauen. Siehe auch https://wiki.meshhessen.de/index.php?title=Solar_Node_(Autarker_Meshtastic_Knoten)

## netiquette

Es wird empfohlen der netiquette von meshhessen zu folgen: https://wiki.meshhessen.de/index.php?title=Traffic_Netiquette_f%C3%BCr_Meshtastic

Es gibt dafür hier eine YAML config (`netiquette.yml`) welche alle Konfigurationen schon macht und über die meshtastic python CLI eingespielt werden kann. 

```
 meshtastic --configure netiquette.yml 
```
> [!NOTE]
> Position (Latitude, Longitude, Altitude) und Namen muss danach noch gesetzt werden.


## Shopping

### RAK

* WisBlock Mini Base Board (RAK19003):  https://store.rakwireless.com/products/wisblock-base-board-rak19003?srsltid=AfmBOoronEY10BUkOF2Ij6HPZJUkzmV3RwWD_HeKMkQAFkpe63wxTRbu
* Module for LoRaWAN with LoRa SX1262 (RAK4631): https://store.rakwireless.com/products/rak4631-lpwan-node?_pos=1&_sid=6d1fb7b72&_ss=r&variant=37505443823814

> [!NOTE]
> Man kann einfach das Starter-Kit kaufen. Kostet 1€ mehr und man hat dafür ne kleine Antenne dabei: https://store.rakwireless.com/products/wisblock-meshtastic-starter-kit

> [!IMPORTANT]
> Frequenz = EU868 und Variante = RAK4631 Arduino


### Stromversorgung
* Solarmodul 5W 5V: https://de.aliexpress.com/item/1005003823736770.html
  Die 5V Volt sind wichtig. 5 Watt ist ok, 7 Watt oder 10 Watt sind besser bei schlechter Ausrichtung.
* DFRobot Solar Power Manager - Solarenergie-Managementmodul – 5V: https://botland.de/zubehor-fur-solarmodule/14423-dfrobot-solar-power-manager-solarenergie-managementmodul-5v-6959420913473.html
* INA219 I2C Bidirektionaler Gleichstrom-Stromversorgungssensor https://www.amazon.de/dp/B07YDH2PCY/
* Keeppower 26650 7000mAh 3,6V-3,7V Li-Ionen-Akku Mit PCB Schutzelektronik: https://www.akkuteile.de/lithium-ionen-akkus/26650/keeppower/keeppower-26650-7000mah-max-15a-entladestrom-3-6v-3-7v-li-ionen-akku_12119_3605
  
### Antenne
* MikroTik LoRaWAN - Omni Antenne 824-960 MHz:  https://www.omg.de/mikrotik/lorawan/mikrotik-lorawan-omni-antenne-824-960-mhz/a-25277
* Horizon Helium City 868 (anderer Anschluss!): https://interline.pl/de/antennas/HORIZON-HELIUM-CITY-868
* Anderer Anschluss, wenn nötig: https://de.aliexpress.com/item/1005005844592086.html

> [!IMPORTANT]
> Auf ebay Kleinanzeigen werden Teilweise günstige Antennen von alten Helium Minern verkauft. Die nutzen auch 868MHz und kann man benutzen. 


### Gehäuse 
* Ebay von AN3DAS.de:  https://www.ebay.de/itm/335611244498
* oder 3D Druck: https://www.printables.com/model/72839-customizable-parametric-stable-and-waterproof-elec <- sehr schönes Gehäuse!
* oder 3D Druck: https://www.printables.com/model/1012624-w9etc-meshtastic-solar-node <- hab ich genutzt. Passt sehr gut, Dichtung ist nicht optimal.
* Heated Inserst für Gehäuse( M3 x 5mm und M5 x 4mm): https://de.aliexpress.com/item/1005008165093382.html?spm=a2g0o.order_list.order_list_main.20.48d45c5f2FGRye&gatewayAdapt=glo2deu
 
### Kleinkram
* Dichtung: Schaumstoffstreifen aus Silikonkautschuk, 3mm: https://de.aliexpress.com/item/1005006511018794.html?spm=a2g0o.order_list.order_list_main.38.48d45c5f2FGRye&gatewayAdapt=glo2deu
* Silikonfett für die Dichtungen: https://www.amazon.de/dp/B00295DBQE
* Wasserdichte Druckausgleichsventile: https://www.aliexpress.com/item/1005007175727622.html?spm=a2g0o.order_list.order_list_main.16.df621802LlLh65
* Kabel mit Stecker für alle Solar/Batterie/Stromverbindungen: https://www.aliexpress.com/item/1005007548578228.html?spm=a2g0o.order_list.order_list_main.39.df621802LlLh65
* Kleber und Dichtmasse zwischen Solarpanel und Gehäuse: Sikaflex 522

## Namesschild

Die Datei `meshhessen_qr_code_name.3mf` ist ein 2-farbiger Druck für ein Namesschild mit QR-Code welcher auf fast jedem Drucker mit einem manuellen Filamentwechsel gedruckt werden kann. Man braucht kein automatisches Filamentwechsel. 
Der Text kann dann, passend zum Node, im slicer angepasst werden. Getestet im Prusa Slicer.
![alt text](meshhessen_qr_code.png "QR Code")
Das Schild kann dann auf das Gehäuse von außen aufgeklebt werden.

> [!IMPORTANT]
> Für den 2-farbigen Druck sollte man zwei Farben mit einem starken helligkeitsunterschied nutzen. Schwarz und Weiß ist perfekt. In dem Renderbild des QR-Codes sieht man zwar einen starken Kontrast zwischen Grün und Orange, der Grau-wert beider Farben ist aber im Vergleich kontrastarm und die meisten Scanner kommen damit nicht klar. 



## Config Checklist
* Namen und Short
* Frequenz auf Europa
* `netiquette.yml` einspielen
* `channels_and_mqtt.yml` einspielen
* Bluetooth pin verändern
* keys speichern
* remote admin key festlegen
