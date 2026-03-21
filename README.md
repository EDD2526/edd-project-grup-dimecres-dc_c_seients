View this project on [CADLAB.io](https://cadlab.io/project/30193). 

# Projecte Seients

>**Autors: MIGUEL Angel Tovar Jaime - Pol Salas Costa** 
>**Versió: 1.0.0**

----------

## Objectiu

>Dissenyar una Unitat de Control Electrònic (ECU) per al control dels seients, capaç de gestionar la posició, memòria de la posició i l'escalfador del seient, comunicant-se amb la resta del vehicle mitjançant bus CAN.


## Diagrama de blocs

![Diagrama de Blocs](DiagramadeBlocs.png)

### Descripció/funcionalitat de cada bloc

  * **Processament Lògic:** Microcontrolador PIC24HJ128GP502 a 3.3V encarregat de l'execució del firmware i gestió de perifèrics
  * **Alimentació:** Sistema de doble regulació. Un convertidor LM2596 que redueix els 12V de la bateria a 5V per a comunicacions, i un regulador LM1117 que  proporciona 3.3V nets per a la lògica digital
  * **Control de Potència:** Controlador PWM actuant a través del bus I2C, PCA9685, per accionar els drivers dels 3 motors (posició, altura, reclinació). S'inclou un MOSFET per al control de la manta calefactora
  * **Emmagatzematge:** Memòria EEPROM I2C, 24LC256, per desar de forma no volàtil certes posicions dels seients
  * **Interfícies de Comunicació:** Transceptor TCAN1043 per a connexió al bus CAN del vehicle, i MAX3232 per adaptar els nivells lògics UART a RS232 per a depuració mitjançant connector DE-9
  * **Entrades/Sensors:** Connectors per a la botonera d'usuari i finals de cursa

-----------

## Requisits / Especificacions

  * Alimentació d'entrada: 12V DC
  * Tensions de regulació interna: 5V DC i 3.3V DC
  * Microcontrolador: PIC24HJ128GP502
  * Freqüència de rellotge: Cristall extern de 8 MHz
  * Entrades digitals: 6 botons de control de seient i 3 finals de cursa agrupats
  * Comunicacions: Bus CAN, bus I2C, i port sèrie UART/RS232

-----------

## Components

| Descripció | Ref | Package | Datasheet | Proveïdor | Preu | Unitats |
| --- | --- | --- | --- | --- | --- | --- |
| Microcontrolador | PIC24HJ128GP502 | SOIC-28 | [Datasheet](https://www.microchip.com/en-us/product/PIC24HJ128GP502) | Mouser | 4,50&euro; | 1x |
| Controlador PWM I2C | PCA9685BS | HVQFN-28 | [Datasheet](https://www.nxp.com/docs/en/data-sheet/PCA9685.pdf) | Mouser | 2,10&euro; | 1x |
| Driver de Motor (Pont H) | DRV8871 | HSOP-8 | [Datasheet](https://www.ti.com/lit/ds/symlink/drv8871.pdf) | Mouser | 1,50&euro; | 3x |
| MOSFET de potència | IRLZ44N | TO-220 | [Datasheet](https://www.infineon.com/dgdl/irlz44n.pdf?fileId=5546d462533600a40153567206892720) | Mouser | 0,90&euro; | 1x |
| Memòria EEPROM I2C | 24LC256 | SOIC-8 | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/21203M.pdf) | Mouser | 0,60&euro; | 1x |
| Transceptor CAN | MCP2562-E-SN | SOIC-8 | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20005167C.pdf) | Mouser | 1,10&euro; | 1x |
| Traductor RS232 | MAX3232 | SOIC-16 | [Datasheet](https://www.ti.com/lit/ds/symlink/max3232.pdf) | Mouser | 1,20&euro; | 1x |
| Expansor I/O I2C | PCF8574T | SOIC-16 | [Datasheet](https://www.ti.com/lit/ds/symlink/pcf8574.pdf) | Mouser | 1,30&euro; | 1x |
| Regulador (12V a 5V) | LM2596 | TO-263 | [Datasheet](https://www.ti.com/lit/ds/symlink/lm2596.pdf) | Mouser | 1,50&euro; | 1x |
| Regulador (5V a 3.3V) | LM1117 | TO-252 | [Datasheet](https://www.ti.com/lit/ds/symlink/lm1117.pdf) | Mouser | 0,80&euro; | 1x |
| Connector RS232 | DE-9_socket (Femella)| THT | - | Mouser | 1,00&euro; | 1x |
| Connector CAN | DE-9_plug (Mascle) | THT | - | Mouser | 1,00&euro; | 1x |
| Sensor cinturó | 5F0857756YLZ | OEM | - | Recanvis VAG | 45,00&euro; | 1x |
| Motor DC amb reductora | JGY370 (12V, 30 RPM) | Eix 6mm D | - | Genèric | 9,00&euro; | 3x |
| Manta Calefactora | Carbon Fiber Pad | Genèric | - | Genèric | 15,00&euro; | 1x |
| Sensor Temperatura | Termistor NTC 10k | Gota / Cable| [Datasheet](https://www.vishay.com/docs/29049/ntcle100.pdf) | Genèric | 0,50&euro; | 1x |
-----------

## Software

### Eines:

  * KiCad 9.0 o superior
  * 

### Configuraci&#243; :

  * 

### Funcionalitats:

  * 

-----------


## Historial de canvis

| Data | Autor     | Branch | Versi&#243; | Descripci&#243; |
| --- | --- | --- | --- | --- |
|  28/03/2023 | mlopez | Master | initial commit | Primera versi&#243; d'esquem&#224;tic i selecci&#243; de components |
| 17/03/2026 | Pol i Miguel | main | 1.0.0 | Finalització de l'esquemàtic |
