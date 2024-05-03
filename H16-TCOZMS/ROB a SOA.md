---
share: "true"
---

## Arduino, jeho základné časti
- Arduino je mikroovládač
- Skladá sa z: pinov (veľa rôznych funkcií), samotný mikroovládač, USB konektor, pripojenie na zdroj, tlačítko RESET, ICSP (debug a nahrávanie programov), podporné obvody
![[labelled-arduino-parts-1173772155.png|labelled-arduino-parts-1173772155.png]]
## Popíšte využitie servomotora v praxi
- Robotická ruka 
- Servomotor vie držať presné uhly, ktoré mu zadáme cez PWM signál
- Preto je ideálny na ovládanie robotickej ruky

## Porovnajte pojmy robot a robotický manipulátor

### Robot
- všeobecný pojem, ktorý pomenúva stroje alebo zaridenia, ktoré sú schopné vykonávať určité úlohy alebo činnosti s menšou alebo žiadnou ľudskou interakciou

## Vysvetlite pojem kinematická štruktúra


## Vymenujte a popíšte typy podvozkov mobilných robotov


## Odvodte polomer otáčania deferenciálneho podvozku


## Porovnajte optický inkrementálny a absolútny snímač polohy
- inkrementalny snimac vie snimat pohyb v nejakom smere
- ako priklad myska, opticky snimac porovnava ktorym smerom sa posuva myska a posiela signal, mysku mozete polozit hocikde, snima to len smer pohybu a jej rychlost
- ![[Pasted image 20240503103910.png|Pasted image 20240503103910.png]]
- absolutny snimac polohy snima absolutnu polohu nejakej suciastky
- vyuzivane castejsie v robotike a tak
- ako priklad GPS, viete vasu presnu polohu nie len smer ktorym sa pohybujete
## Vytvorte porgram, v ktorom bude blikať LED 0,5s

```c++\
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(500);                       // wait for a second
  digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
  delay(500);                       // wait for a second
}
```
## Charakterizujte najpoužívanejšie komponenty v aplikáciach s grafickým rozhraním
Button, TextBox, ComboBox, Scrollbar, Lista nastrojov, Grafika, Context Menu, 

