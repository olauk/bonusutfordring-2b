# Bonusutfordring 2B Trafikklys


## Intro  @fullscreen @unplugged
Tid ca 15-30 minutter

Byens trafikklys virker ikke som de skal! Kan dere få skikk på lysstyringsprogrammet?

Du trenger: 
* micro:bit
* trafikklys
* 4 ledninger (bananplugger eller krokodilleklemmer)

Dette kobles slik:
![Trafikklys](https://github.com/olauk/static/blob/master/trafikklys_kobling.png?raw=true)

## Step 1

Koble en ledning fra raud (P0) på trafikklyset, til 0 på micro:bit. 
Vi må også koble en ledning fra GND på trafikklyset til GND på micro:bit for at dette skal bli en lukket krets. 
For å få lys i den røde led-dioden må vi skru på strømmen i pin 0. 
Dette gjør vi med blokken ``||pins:skriv digital til||`` Denne blokken finner du i kategorien ``||pins:Tilkobling||``. Plasser blokken i ``||basic:gjenta for alltid||`` Vi velger P0 for pin 0 og gir blokken verdi 1 som betyr strøm på. 

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
	
})
```
## Step 2
Vi vil la det røde lyset lyse i ett sekund før vi skrur på neste lys. Dette gjør vi ved å legge inn blokken ``||basic:pause||``. Tallet i denne blokken er antall millisekunder programmet venter før det går videre til neste kloss. 1000 ms = 1 sekund

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
	
})
```
## Step 3
Det neste vi vil gjøre er å koble til den gule led-dioden. Denne kobler vi til pin 1 (P1). Koble en ledning fra gul (P1) til 1 på micro:bit. Deretter henter vi inn en ny ``||pins:skriv digital til||`` blokk som vi endrer til P1 og gir verdien 1.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P1, 1)
	
})
```
## Step 4
Legg inn en ny pause etter det gule lyset er skudd på. Dette gjør vi ved å legge inn blokken ``||basic:pause||`` under den siste ``||pins:skriv digital til||``
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P1, 1)
	basic.pause(1000)
})
```

## Step 5
Så skal vi koble til den grønne led-dioden. Denne kobles til pin 2 (P2). Koble en ledning fra grøn (P2) på trafikklyset til 2 på micro:bit. Vi henter en ny ``||pins:skriv digital til||`` blokk og endrer til P2 og verdi 1.
Når du er ferdig med dette steget lyser alle led-diodene.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P2, 1)
    basic.pause(1000)	
})

```
## Step 6
Vi ønsker at trafikklyset skal veksle fra rødt via rødt og gult til grønt lys. For å skru av et lys må vi bruke blokken ``||pins:skriv digital til||`` og sette verdi til 0. Prøv selv å få trafikklyset til å lyse i riktig rekkefølge. Husk at P0 styrer rødt lys, P1 gult og P2 grønt lys. Lykke til. 
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(1000)
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 0)
    pins.digitalWritePin(DigitalPin.P2, 1)
    basic.pause(1000)	
})

```