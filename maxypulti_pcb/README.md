![GitHub Logo](http://www.heise.de/make/icons/make_logo.png)

Maker Media GmbH und c't, Heise Zeitschriften Verlag

***

### MaXYposi-Schrittmotorsteuerung, Stückliste Kontrollpult

In diesem Unterverzeichnis finden Sie die Stücklisten, Schalt- und Bestückungspläne 
zur MaXYposi-Schrittmotorsteuerung, Kontrollpult (MaXYpulti).

    Bauteil                                   Anzahl Name/Bemerkung
    =============================================================================
    
    PSS 254/4G, Wire-To-Board 4-pol. RM2,54      1   PL6
    PSS 254/5G, Wire-To-Board 5-pol. RM2,54      2   PL1 PL2
    PSS 254/6G, Wire-To-Board 6-pol. RM2,54      2   PL4    
    Zweireihige Pfostenleiste RM 2.54            1   PL3                 
    WSL 16, Wannenstecker 16pol.                 1   PL5               
    Jumper 2pol. RM2.54                          1   JP1                 
    14WP, Zweireihige Pfostenleiste RM 2.54      1   PL7 (siehe Text unten)                

    74HC165 DIL                                  4   U4 U5 U6 U7         
    74HC595 DIL                                  2   U8 U9               
    ATmega328-DIL                                1   U3  (ggf. mit Bootloader)               
    DS26LS32CM DIL                               1   U1  (oder AM26LS32ACN)                
    22p RM5                                      2   C3 C5               
    100n RM5                                     8   C6 C4 C1 C10 C11 C12 C13 C14           
    10µ 63V                                      4   C7 C9  C2 C8              
    LCD alphanum 2x16 Zeichen                    1   U2                  
    LED rot 3mm                                  1   LED1                
    4k7                                          1   R6                  
    10k                                          1   R2                  
    10R                                          1   R3                  
    220R                                         3   R7 R8 R9            
    1K                                          16   R15 R20 R21 R22 R23 R24 R25 R26 R27 R28 R29 R30 R31 R32 R33 R34
    4k7                                          1   R19                 
    22k                                          1   R4                  
    100R                                         8   R12 R10 R11 R13 R14 R16 R17 R18
    SIL 9-8 10k Netzwerk 8-fach, 9-pin           4   RN3 RN4 RN5 RN6     
    Print-Poti Alps, RK11K113-LOG10K             1   P1  (auch RK11K113-LIN10K oder 50K möglich)     
    Trimmer 5mm, 2k5                             1   R1                  
    Taster Multimec 3FTH9                       30   SW1..SW34
    Taster Multimec 3ATH9                        4   SW3, SW6, SW8, SW9   
    Quartz 16 MHz HC49U                          1   XTAL1 

    =============================================================================

Beachten Sie die Hinweise im Artikel zu den LED-Vorwiderständen. Diese sind hier 
pauschal mit 1k für blaue/weiße LEDs angegeben, müssen aber für eine ungefähr 
gleiche Helligkeit der einzelnen Farben angepasst werden. Der jeweilige 
Vorwiderstand ist immer in der Nähe des zugehörige Tasters.

PL7 kann alternativ für ein Display mit seitlichem 14pol. Anschluss verwendet 
werden und wird bei 16x2-Standard-Displays nicht benötigt. Hierfür sollten Sie 
eine einreihige Pfostenleiste RM 2,54 mm mitbestellen.

Die LEDs für die Taster sowie die Tastenkappen sind in der Stückliste NICHT 
aufgeführt. Wählen Sie die Farben nach persönlichem Gusto. Wir haben die Farben 
wie folgt gewählt: Blau = X (Kappe 1D00), Grün = Y (Kappe 1D02), Rot = Z (Kappe 
1D08), Gelb = C-Achse (Kappe 1D04). Die transparent-weißen Tastenkappen haben 
die Bezeichnung 1D16, die schwarzen heißen 1D09. beachten Sie zur Auswahl der 
Farben auch die Bilder im Artikel.

[Flachkopf-LEDs von LED1.de](https://www.led1.de/shop/standard-leds/led-3mm-ultrahell-flat-top/)

[Tastenkappen Serie 1Dxx von MEC Switches, Beispielfarbe Rot, bei Reichelt](https://www.reichelt.de/Kurzhubtaster/KAPPE-1D08/3/index.html?ACTION=3&LA=3&ARTICLE=79710&GROUPID=7587&trstct=vrt_pdn)

[Tastenkappe Serie 1ZCxx von MEC Switches, Jogpad-Mittelkreis, Beispielfarbe Schwarz, bei Reichelt](https://www.reichelt.de/Kurzhubtaster/KAPPE-1ZC09/3/index.html?ACTION=3&LA=2&ARTICLE=79739)

[Tastenkappen Serie 1ZBxx von MEC Switches, Jogpad-Außenkreis, Beispielfarbe Schwarz, bei Reichelt](https://www.reichelt.de/Kurzhubtaster/KAPPE-1ZB09/3/index.html?ACTION=3&LA=517&ARTICLE=79744)

Bitte denken Sie bei einer Bestellung auch an Zubehör wie Flachbandkabel, Steck-
und Pfostenverbinder.

Wer unbestückte Platinen fertigen (lassen) will, kann die Gerber- und 
Bohrdateien "maxypulti_gerber.zip" herunterladen. Bitte beachten Sie: Das Layout 
unterliegt unserem Copyright und darf **nur für private Zwecke** verwendet 
werden. Für eine kommerzielle Nutzung [kontaktieren Sie bitte die 
Redaktion](https://www.heise.de/make/kontakt/).

Vorlagen für die Frontplatte liegen in zwei Versionen vor: Mit und ohne 
Ausschnitt für ein CNC-Handrad (Dial), jeweils als DXF-, SVG- und CorelDraw-Datei. 
Die Vorlagen eignen sich zum Plexiglas-Zuschnitt mit Beschriftung bei einem 
Dienstleister Ihrer Wahl, z.B. www.formulor.de oder einem beliebigen Fablab mit 
Lasercutter.

#### AVR-CPU für Display

Als Prozessor empfehlen wir einen ATmega328p mit bereits installiertem 
Bootloader, erhältlich zum Beispiel bei [Watterott 
electronic](http://www.watterott.com/de/ATmega328-Arduino-Bootloader); damit ist 
das Flashen der GRBL-Display-Firmware über die Arduino-IDE möglich: Geben Sie 
als Board den Arduino Nano an und verwenden Sie einen USB-Seriell-Wandler mit 
FTDI-Chip. Ansonsten benötigen Sie zum Flashen
[einen ISP-Programmer](https://www.reichelt.de/Programmer-Entwicklungstools/DIAMEX-PROG-S2/3/index.html?ACTION=3&LA=446&ARTICLE=164172). 
Beachten Sie auch die Leser-Anleitung unten auf dieser Seite.

#### GRBL-644 anpassen

Um das MaXYposi-GRBL mit unserem Kontrollpult einzusetzen, müssen Sie in der 
Datei **config.h** die Zeilen
```
#define USER_PANEL_SMALL 
// #define USER_PANEL_LARGE 
```
ändern in
```
// #define USER_PANEL_SMALL 
#define USER_PANEL_LARGE 
```
und den Sketch **grblUpload_644.ino** neu kompilieren.

#### Weitere Tipps

Unser Leser **[HorstBaerbel](https://github.com/HorstBaerbel)** hat 
dankenswerterweise das Programmieren des HEX-Files für den Display-Prozessor 
genauer beschrieben - im Heft wurde die Prozedur nur kurz angerissen. Außerdem 
hat er hier einige wichtige Hinweise zusammengetragen. Vielen Dank dafür! :+1: 

* Das Label für C9 fehlt auf dem Bestückungsdruck.

* Bei allen anderen Tastern ist es egal, aber die vier speziellen Taster (Multimec 3ATH9) für das Jogpad MÜSSEN in der richtigen Orientierung eingebaut werden (grob umschrieben "Verriegellungsnasen innen")! Der "Strich" auf dem Bestückungsplan ist etwas irreführend da die MEC-Taster sowohl eine Kante, als auch einen solchen Strich haben. Ein Hinweis wäre praktisch, auslöten nervt nämlich ;)

* Ich habe für P1 das Poti "RK11K113-LOG10K" von Reichelt bestellt. Leider ist die Achse etwas kurz, so dass ev. "RK09K113-LOG10K" besser wäre. Dort müsste man dann allerdings die Achse kürzen. Man kann das "RK11K113-LOG10K" aber auch, wie die Joypad-Taster, mit 1,5mm Abstand zur Platine einbauen um möglichst viel von der Achse zum klemmen übrig zu haben.

* Der "DS26LS32CM" ist bei Reichelt nicht zu bekommen, aber der Ersatztyp "AM26LS32ACN".

* Der "74LS595" ist bei Reichelt nicht zu bekommen, als Ersatz aber der "74HC595".

* Die Teilenummer des 16MHz-Quartzes ist "16,0000-HC49U-S".

* Der Drehencoder / Handrad ist z.B. bei Ebay sehr gut mit der Suche "100PPR hand wheel" zu finden.

* Wer die lange Versandzeit nicht scheut bekommt einen ganzen Satz 
verschiedenfarbige straw-hat-LEDs z.B. von Aliexpress. Man findet mit der Suche 
"flat top led mix" einige Angebote für 5*20 LEDs (RGBYW) um die 3€...

* Die Firmware mit einem Arduino als ISP auf den ATMEGA328P zu bringen ist nicht ganz einfach. Hier meine Anleitung (für Linux, sollte aber auch für andere OS gehen):

  *  Nach dem Tutorial [hier](https://www.arduino.cc/en/Tutorial/ArduinoISP) den Arduino mit einem ISP-Sketch versehen und mit dem MaxyPulti verbinden. Im Detail bei einem Arduino UNO oder Pro als ISP: (Arduino ISP->MaxyPulti PL3) ISP1->9, ISP2->2, ISP3->7, ISP4->1, ISP5->4 und Arduino Pin 10->5.

  * In den Arduino-IDE-Voreinstellungen "Ausführliche Ausgabe während ... Hochladen" aktivieren.

  * Als Board "Arduino/Genuino UNO" und als Programmer "Arduino as ISP" einstellen und auf "Bootloader brennen" klicken. Nun sollte der Bootloader installiert sein.

  * Die erste Kommandozeile aus dem Ausgabefenster kopieren (fett markierter Teil). Sie sollte in etwa so aussehen: "**/home/USERNAME/.arduino15/packages/arduino/tools/avrdude/6.3.0-arduino9/bin/avrdude -C/home/USERNAME/.arduino15/packages/arduino/tools/avrdude/6.3.0-arduino9/etc/avrdude.conf -v -patmega328p -cstk500v1 -P/dev/ttyACM0 -b19200 -Uflash:w:**/home/USERNAME/.arduino15/packages/arduino/hardware/avr/1.6.21/bootloaders/optiboot/optiboot_atmega328.hex:i -Ulock:w:0x0F:m". Hier ist USERNAME der Name des angemeldeten Benutzers.

  * Die Datei "grbl_display.hex" herunterladen. Terminal öffnen und in das Verzeichnis mit der Datei wechseln.

  * Kommandozeile für HEX-Upload zusammenbauen (oben kopierter Teil, plus fett markierter Teil): "/home/USERNAME/.arduino15/packages/arduino/tools/avrdude/6.3.0-arduino9/bin/avrdude -C/home/USERNAME/.arduino15/packages/arduino/tools/avrdude/6.3.0-arduino9/etc/avrdude.conf -v -patmega328p -cstk500v1 -P/dev/ttyACM0 -b19200 -Uflash:w:**grbl_display.hex -D**".

  * Nachdem der Upload fertig ist, sollte LED1 auf dem MaxyPulti rhythmisch blinken.

* In der Frontplatte ist das Loch für P1 mmn zu groß; 7mm sollten laut Schieblehre für den "RK11K113-LOG10K" reichen.

