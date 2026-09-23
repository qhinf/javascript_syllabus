# Hoofdstuk 2: Variabelen en waarden

Hoe weet een computer dat een naam 'Merijn' is of een score '42'? Net zoals een contactenlijst namen koppelt aan nummers of adressen, gebruiken we in JavaScript variabelen om informatie te onthouden en te veranderen.

## Hoe voer je de oefeningen uit?

De oefeningen in dit hoofdstuk zijn ontworpen om direct in je **webbrowser** uitgevoerd te worden. Dit betekent dat je geen ingewikkelde software hoeft te installeren om te beginnen. Je kunt de code die je hier ziet, kopiëren en plakken in de "Console" van je browser (meestal te vinden via de rechtermuisknop -> Inspecteren -> Console).

## Oefening 0: console openen

In je webbrowser, open de javascript console. In de meeste browsers werkt de keyboard-shortcut `control-shift-i`.

Typ in de console:

```javascript
32 + 10
```

en druk op enter, je ziet het antwoord `42`. Dit is de eerste JavaScript die je hebt uitgevoerd!

> Terzijde: op `firefox` na zijn bijna alle browsers gebaseerd op `chrome` dat uit de koker van google komt. Er is een Nederlands initiatief, technisch geleid door mijn oud-collega Jelle: [https://ladybird.org/](Ladybird). Zij maken een nieuwe onafhankelijk gemaakte browser. Net zoals firefox dat ooit was, en chrome, en daarvoor in de verre geschiedenis mozilla, na de grondlegger netscape... En ik vergeet Safari bijna...


De voorkennis voor deze module is basis programmeren python en/of html/css, maar gezien de lijst van leerlingen kan het zijn dat je nog geen programmeer-ervaring hebt.
We gaan daarom stap voor stap onderdelen uit de programmeertaal leren kennen. Als je al iets als python kent heb je een beetje een voorsprong, maar in Javascript zien veel dingen er anders uit.


Bijna elke programmeertaal heeft *variabelen*. Een *variabele* is een vaste naam die hoort bij iets dat zou kunnen veranderen.

Een vergelijking: in je telefoon heb je een lijst contacten. Bij zo'n contact (bvb 'Pieter' in mijn telefoon) hoort een adres. Als Pieter verhuist dan verander ik het adres, de naam Pieter blijft hetzelfde.

Zo is het ook met variabelen: het is een vaste naam en daaraan koppelen we een variabele inhoud.
Dat koppelen van inhoud aan een variabele noemen we `toewijzen`, in het Engels `assignment`. Dit doen met met het symbool `=`. 


## Oefening 1: variabele maken en toewijzing

Type het volgende in de browser-console:

```javascript
let docent = "Merijn";
```

Het levert "niets" op als resultaat, dat is wat de console bedoelt met `undefined`.

Je hebt wel iets bereikt: de variabele `docent` bestaat nu.

Probeer:

```javascript
docent
```

In de highlight van de console zie je het antwoord al verschijnen en als je op `enter` drukt dan krijg je als resultaat de inhoud.

Variabelen zoals deze zijn bedoeld om te kunnen veranderen, dus we mogen deze opnieuw toewijzen:

```javascript
docent = "Pieter";

docent
```

Het voor het eerst *maken* van een nieuwe variabele noemen we in programmeertalen een `declaratie`.

### Wat je nog meer ziet in dit voorbeeld

Het ding dat we toekennen aan een variabele heet een *waarde*. In deze voorbeelden was die waarde steeds een tekst geweest. Een *tekst* het ook wel een *string* in het Engels. Deze herken je aan de aanhalingstekens die er omheen staan `""`.

In JavaScript mag je ook `'` gebruiken als tekens rondom een string, zolang begin en eind van een string maar hetzelfde teken gebruiken. Dus `"Q-vakken"`  en `'Q-vakken'` zijn precies hetzelfde voor JavaScript!

In plaats van tekst, kun je ook getallen toewijzen aan variabelen; bijvoorbeeld `let n = 0;` maakt de variabele `n` aan en wijst er de waarde `0` aan toe.


### Zelf doen / beredeneren

- Hoe verander je de inhoud van `docent` hierboven weer terug in Merijn?
- Hoe maak je een variabele met de naam `ik` en je eigen naam er in?
- Maak twee variabelen `a` en `b`. Geef `a` een waarde, bijvoorbeeld `42`. Wijs nu `b` toe aan `a`, wat gebeurt er met de inhoud van `a` en `b`?
- Maak twee variabelen, `c` en `d`. Geef `c` een tekst als waarde (met aanhalingstekens)


## Meerdere soorten variabelen (die niet altijd variabel zijn)

JavaScript kent *vier* manieren om variabelen te maken die nog niet bestaan:

`a = 42;` Als `a` nog niet bestaat, wordt deze aangemaakt. Je kunt `a` daarna aanpassen. Als `a` wel al bestaat dan wijst dit nieuwe inhoud toe. Maar! Dit is niet een "declaratie": het is meer per ongeluk dat dit werkt. In een webbrowser bestaat alle code die wij schrijven in een *object* met de naam `window` (wees gerust, dat leg ik later uit). En daarmee wordt `a` een eigenschap van het object `window` en kan het dus ook bereikt worden met `window.a`.

`var a = 42;` Als `a` nog niet bestaat wordt deze aangemaakt. Je kunt `a` daarna aanpassen. Als `a` wel al bestaat dan wordt deze opnieuw toegewezen. Een `var`-declaratie wordt "hoisted" en omdat ik de uitleg ook nooit perfect snap verwijs ik naar [Hoisting op mozilla.org](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting).

Deze eerste twee varianten zijn "ouderwets" en komen uit de eerste generaties van de taal. We gebruiken eigenlijk altijd deze twee varianten hieronder:
Het is lastig om zoiets fundamenteels als *declaratie* van variabelen te veranderen. Tip: bedenk waarom. En daarom bestaat de oude manier nog.

`let a = 42;` Als `a` nog niet bestaat wordt deze aangemaakt. Je kunt `a` daarna aanpassen. Als `a` wel al bestaat dan is dit een fout. Een ander verschil met `var` is het *bereik*, in het Engels *scope*, dat komt later.

`const a = 42;` Als `a` nog niet bestaat wordt deze aangemaakt. Je kunt `a` *NIET* meer aanpassen. Als `a` wel al bestaat dan is dit een fout. De *bereik* / *scope* regels zijn hetzelfde.

### Maar... waarom kan dit op al deze manieren?


Sterke voorkeur: gebruik `let` en `const`.

Een `const` gebruik je om een waarde een keer in te stellen en daarna te gebruiken. Een getal zoals `10` bijvoorbeeld heeft niet echt betekenis. Net zoals een 06-nummer niet echt betekenis heeft zonder dat je weet wie erbij hoort.
Daarom gebruiken programmeurs graag constanten: een soort-van variabele die niet kan veranderen. Bijvoorbeeld `const maxWachttijdInSeconden = 10;` geeft aan dat we hiermee kunnen instellen hoe lang we maximaal op iets willen wachten.
Dus als we dat later in een programma juist gebruiken, dan wordt dat stuk programma leesbaarder.

`let` geeft als voordeel dat het een *fout* is om een variabele met dezelfde naam opnieuw te proberen te declareren. Als we dat per ongeluk doen, dan wijst dat bijna altijd op een fout. Een `let` heeft ook een beter afgesproken bereik, dus een beter afgesproken regel over waar in het programma die variable zichtbaar en bruikbaar is. 


## Oefening 2: broncode lezen en onderdelen benoemen

```javascript
const a = 10;
let b = 32;

let antwoord = a + b;

b = 42;

console.log(b);

console.log(a + b);
```

- Wat verschijnt er in de `console` van de browser als je dit uitvoert?

- Hoe noem je de = in de regel `let antwoord = ...` ?

- wat is het verschil tussen `let b = 32;` en `b = 42` even verderop?

- Waarom mag er op de regel `b = 42;` niet `let b = 42;` staan?


[chapter3.md](chapter3.md)

> Deze module is geschreven met Nederlands als voertaal. De meeste termen die echt afwijken benoemen we ook in het Engels. Als we praten over broncode kun je de Nederlandse of Engelse termen gebruiken.

> Het symbool voor toewijzing is `=`. We noemen zo'n symbool een `operator`, andere voorbeelden zijn `+`, `*`, `-`, `/`. Omdat JavaScript het niet toestaat zelf operators te maken of aan te passen is deze term niet zo belangrijk voor de les.

> In JavaScript kan soms hetzelfde op meerdere manieren. Dit geldt in dit eerste voorbeeld dus al voor tekst-waarden en voor het maken van variabelen!

> Bij het maken van deze teksten van de module is beperkt gebruik gemaakt van AI: de tekst is geschreven door Merijn, AI is gebruikt voor controle en soms als bron van kennis om aannames te controleren.
