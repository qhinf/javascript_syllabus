# Hoofdstuk 4: Loops 

> Het grote verschil tussen Python en JavaScript (en C en Java) is de manier waarop code wordt gegroepeerd. In Python gebruik je een inspring-niveau om aan te geven welke code bij elkaar hoort. En hoewel inspringen zeker een goed idee is, kiezen andere talen ervoor om `{ .. }`-haakjes te gebruiken. Dat haakje noemen we 'curly brace' (ok er is een taal die het 'snor' noemt, die taal heet zelf mustache). Dit betekent dat ondanks inspring-verschillen de code toch bij elkaar zal horen in C, JavaScript, Java ... . Dit zorgt naar mijn idee voor minder fouten maar is meer tekens op het scherm.

## Loops (lussen?)

Als je in een computerprogramma iets wil herhalen, of iets wil doen **voor elk ding** in een lijst, dan gebruik je daarvoor loops. Javascript heeft diverse soorten loops (want JavaScript is bijzonder).

### While-loop

Dit is de meest eenvoudige loop. De code in het blok tussen `{}` wordt herhaald zolang de voorwaarde geldt.

```javascript

const lekker = 21;
let temperatuur = 0;
let aircoAan = false;

// ! betekent 'niet', dus !klaar is niet-klaar
while (temperatuur > lekker) {
    if (!aircoAan) { zetAircoAan(); }
    wachtEenMinuut();
    temperatuur = meetTemperatuur();
}
zetAircoUit();
```


### For-loop met teller

Dit is de *klassieke* for-loop die bijna elke programmeertaal heeft:

```javascript
for(let i = 0; i < 10; i++) {
    console.log("i = " + 1);
}

output:
0
1
...
9
```

Die loop heeft de volgende constructie:

```javascript
for ( initialisatie ; voorwaarde ; verandering ) {

}
```

- De *initialisatie* wordt eenmalig uitgevoerd (bvb `let i = 0`),
- de *voorwaarde* wordt voor het uitvoeren van de lus gecheckt, als die `false` teruggeeft is de loop klaar (bvb `i < 10`),
- de *verandering* wordt na het uitvoeren van de lus-code uitgevoerd. (bvb `i = i + 1`).


### For-loop voor *arrays*

We hebben eerder gesproken over arrays, die je met `[]` noteert in JavaScript. Om alle elementen van een array af te lopen en een voor een iets mee te kunnen doen, heeft JavaScript een speciale syntax:

```javascript
let fruit = [ 'appel', 'banaan', 'citroen' ];

for (let f of fruit) {
    if (f === 'banaan') {
        console.log("Pieter van Engelen steekt ineens zijn hoofd om de hoek!");
    } else {
        console.log("Fruit: " + f);
    }
}

```

Deze for-loop werkt met *of* ... en dat is even verwarrend want in Python is dat `in`, maar in JavaScript kan dat ook maar dan betekent het iets anders:


### For-loop voor *object*en

In nog nieuwere versies (voor ruimhartige definitie van nieuw) bestaat deze mooie variant:

```javascript
let favFruit = {
    Pieter: "banaan",
    Merijn: "paprika, want dat is technisch gezien een vrucht en dus fruit?"
}

for (const naam in favFruit )  {
    // Je kunt in JavaScript uit een object een waarde halen bij een key met de syntax die lijkt op arrays:
    const fruit = favFruit[naam];
    console.log(`Het favoriete fruit van ${naam} is ${fruit}`);
}

```
