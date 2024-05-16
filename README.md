# oskimark.github.io
 [impedir instalacion de driver pl2303](impedir instalacion de driver2/impedir instalacion de driver2.html).
 [Contribution  guidelines for this project](docs/CONTRIBUTING.md)
### ATMEGA8A

Vamos a programar el **MCU ATMEGA8A**.
compre por aliexpress 20 chips en formato QFN32

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ2fTX08NwgapdyukYtDhpqXx8xJElgzs85iA&s)
y algunas placas adaptadoras a QFN32 a DIP32.
![](https://github.com/Oskimark/oskimark.github.io/blob/main/qfn32.png)
este es el pinout del chip
![pinout atmega8](https://camo.githubusercontent.com/18796d8b7673e3b6c14b6bdfb61d86b58c6f0d670398973abd4207afce960277/68747470733a2f2f692e696d6775722e636f6d2f6e6177657145362e6a7067)




para poder programarlo usando el IDE de Arduino tnemos que instalar el paquete para ese chip. 
estos son los pasos tal como estan en *https://github.com/MCUdude/MiniCore?tab=readme-ov-file#pinout*

Open the Arduino IDE.
Open the File > Preferences menu item.
Enter the following URL in Additional Boards Manager URLs:
https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json
Open the Tools > Board > Boards Manager... menu item.
Wait for the platform indexes to finish downloading.
Scroll down until you see the MiniCore entry and click on it.
Click Install.
After installation is complete close the Boards Manager window.

ahora tendremos la opcion para nuestro micro:
![](https://oskimark.github.io/conf.png)
despues usando el sketch 
/ This sketch turns the Arduino into a AVRISP using the following Arduino pins:
//
// Pin 10 is used to reset the target microcontroller.
// pins MOSI, MISO and SCK are the same pins as
// digital pin 11, 12 and 13, respectively.

conectamos asi:
![](https://oskimark.github.io/programar%20avrisp.png)

y le damos a !quemar bootloader. esto nos va a permitir subir codigo usando solo la uart y un adaptador pl2303 o ch341, hacer debug por esa uart (puerto serie, serialPrint) usando dos cables tx y rx.ademas de quemar los fuses correspondientes . oscilador interno a 8mhz watchdog brownout etc
si todo esta conectado correcta y firmemente (los dos problemas de siempre) tendriamos qeu tener esto en la terminal del IDE:

![](https://oskimark.github.io/terminal1.png)

![](https://oskimark.github.io/terminal2.png)

el chipp en el adaptador queda con este pinout, en rojo estan resaltados oos pines para quemar el bootloader. y e azul los del serial.

![](https://oskimark.github.io/pinout_qfn_adapt.png)
