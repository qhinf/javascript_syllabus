# De module JavaScript

# Introductie

Welkom bij de module over javascript. Javascript is de meestgebruikte programmeertaal in 2023. Waarom dat zo is?
Javascript is ingebouwd in elke webbrowser. Sommige PC apps worden gemaakt in Javascript. Het is onderdeel van veel mobiele apps. Het wordt gebruikt in de back-end "de cloud", om verzoeken van webbrowsers en apps af te handelen.

Je docent is Merijn Vogel, als docent een beetje een noob, maar zeer ervaren als software ontwikkelaar.

# Kennismaken met javascript

De eerste les maak je kennis met de module. En maak je kennis met Javascript. En met je docent.

## Heel beknopte geschiedenis van Javascript

Javascript heeft een lange geschiedenis, sinds de jaren negentig van de vorige eeuw.

Een tijdlijn vind je hier:  https://www.w3schools.com/js/js_history.asp

Webbrowsers waren ooit heel saai. Een beetje als boeken en papier. Puur bedoeld om informatie te delen. De toen grootste browsermaker wilde wat meer beweging krijgen in sites, wat meer dynamiek. Daarvoor vonden ze een script-taal die ze konden gebruiken, Javascript. Sinds vrij kort daarna heet het eigenlijk ECMAscript, maar de naam Javascript is blijven hangen.

Een wat uitgebreidere geschiedenis lees je bijvoorbeeld hier: https://dev.to/dboatengx/history-of-javascript-how-it-all-began-92a

### Heeft Javascript iets te maken met Java?

Nee. Om een leerling te citeren: "*Java* versus *JavaScript* is als *car* versus *carpet*".

# Aan de slag met Javascript

## Het eerste begin

Begin met deze tutorial om de programmeertaal een beetje te leren kennen: https://www.w3schools.com/js/default.asp Het internet staat verder vol met tutorials over JavaScript. Google is een vriend in dezen. In de lessen komen bijzonderheden aan bod.

Werk de tutorial door tot `JS Loop while`.

## Werken op je computer of laptop: keuzes!

#### Html, CSS en Javascript op je computer

Maak een map aan op je computer. Maak daarin drie bestandjes of download het startpakketje hier.
Bestanden:
- `index.html` is de HTML pagina die je met je browser opent. Hierin staat de HTML en de JavaScript code.
- `style.css` is voor de styling van de HTML (als je de module *HTML en CSS* hebt gedaan komt dit je waarschijnlijk bekend voor).

Bewerken van dit soort bestanden doe je met een code-editor (en zeker niet met Word!).
Bijvoorbeeld `notepad++` . Gebruik voor deze module liever geen "echte" programmeeromgeving zoals Visual Studio Code. Een dergelijke programmeeromgeving is zo erg behulpzaam dat het lastig wordt.


Zie het 'startpakket' bij de eindopdracht.

#### Anders, namelijk...

Zoals altijd bij Q-highschool mag je het "beter weten" / iets anders doen... wij zijn er voor jou!

- Wil je een app maken en die met andere delen? Gebruik dan `electron`. Dit wordt gebruikt als platform voor bijvoorbeeld discord, Obsidian, Teams, ... Meer informatie hiervoer vind je hier: https://www.electronjs.org/

- Wil je een website maken die publiek zichtbaar is? Breng je broncode onder in github pages.

- Wil je iets bewegends en artistieks maken, gebruik `p5js`. Zoals ik liet zien tijdens de fysieke les.  Links: https://p5js.org/ en https://editor.p5js.org/ Het resultaat van de *live coding* sessie in de klas in blok 4 2022-2023: https://editor.p5js.org/merijnv/sketches/OwYe2GDEX


# Javascript en de browser: de DOM-boom

Javascript werkt in browsers en kan daar acties teweegbrengen.

Achtergrondinformatie:  https://www.w3schools.com/js/js_htmldom.asp

# 'Netjes' en slim programmeren

> Voor je hier verder leest: neem de tijd om de tutorials door te nemen. 

Klei is flexibel; je kunt er alle driedimensionale vormen mee maken die je maar wil. Het is ook beperkt: er zijn maar drie ruimtelijke richtingen en klei heeft een beperkte sterkte. Wat heeft dit te maken me programmeren?

Programmacode is nog veel flexibeler dan klei. Je kunt werkelijk alle kanten op en programma's kunnen nogal uit de hand lopen als je ongestructureerd te werk gaat. Om die reden zijn er zogenaamde "abstracties" bedacht, in deze syllabus maak je kennis met functies en classes.


## Afspraken over code-stijl

Er zijn in de loop van de jaren wat afspraken ontstaan hoe javascript programma's eruit moeten zien. Bijvoorbeeld:
- Namen van variabelen zijn in kleine letters `let count = ...` 
- Namen van variabelen zijn beschrijvend `let myFavoriteAnimal = 'Cat'` en elk nieuw woord start met een hoofdleter (camelCase)
- Namen van functies beginnen met een kleine letter `function describe() { ... }`
- Omdat Javascripts `==` "bijzonder" gedrag vertoont, doe je vergelijkingen bij voorkeur met `===`.

Zo zijn er nog veel meer afspraken over javascript, zie bijvoorbeeld https://www.w3schools.com/js/js_conventions.asp.

Deze afspraken zijn uiteraard niet allemaal even heilig en precies; dus in het bedrijfsleven kom je vaak precieze afspraken tegen. Deze afspraken zijn er om elkaars broncode beter te kunnen lezen. Een computer iets laten doen is een doel van een programma, maar het kunnen aanpassen, onderhouden en overdragen aan anderen is ook erg belangrijk.

## Structuren
 
### Objecten: gegevens elkaar houden

> In Python is dit een `dictionary`, in Java is dit een `Map`.

De belangrijkste structuur van Javascript is het `Object`. Een `Object` heeft `properties`, eigenschappen, die een naam hebben. In Python is dit de dictionary, of `dict` .
Je gebruikt objecten om eigenschappen die bij elkaar horen, bij elkaar te houden.
```javascript
let aap = { };
aap.naam = 'Pipo';
aap.eet = 'Banaan';
aap.soort = 'Baviaan';

// wat eet deze aap?
console.log("Deze aap eet " + aap.eet)
```

Hier wordt een variabele `aap` gemaakt als `object`. De `aap` heeft de eigenschappen `naam`, `eet` en `soort`.

### Arrays: lijsten in Javascript

```javascript
let apen = [];
let aapPipo = { "naam": "Pipo", "eet": "Banaan", "soort": "Baviaan" };
let aapGuusje = { "naam": "Guusje", "eet": "Nootjes", "soort": "Ringstaartmaki" };

apen[0] = aapPipo;
apen[1] = aapGuusje;

console.log(apen);
```
Een `[]` als deze is onder water een `Array`, maar lijkt veel op een `Object` met als `properties` de cijfers waar een waarde bij hoort.

In Javascript mag je gaten laten in de rij en kun je een rij onbeperkt uitbreiden. 
Om dingen toe te voegen aan een  gebruik je de `.push()` methode van `Array`.
```javascript
let apen = [];
let pipo = { "naam": "Pipo", "eet": "Banaan", "soort": "Baviaan" };
let guusje = { "naam": "Guusje", "eet": "Nootjes", "soort": "Ringstaartmaki" };

apen.push(pipo);
apen.push(guusje);

console.log(apen);
```

Een `[]` bevat niet de inhoud van het `object`, zelf maar een verwijzing naar het `object`; dus als een eigenschap van een `object` verandert, dan verandert het `object` in de lijst ook:
```javascript
let pipo = { "naam": "Pipo", "eet": "Banaan", "soort": "Baviaan" };
let guusje = { "naam": "Guusje", "eet": "Nootjes", "soort": "Ringstaartmaki" };

let apen = [];
apen.push(pipo);
apen.push(guusje);

console.log(JSON.stringify(apen));
// [{"naam":"Pipo","eet":"Banaan","soort":"Baviaan"},{"naam":"Guusje","eet":"Nootjes","soort":"Ringstaartmaki"}]

guusje.eet = "Nootjes en bananen";
console.log(JSON.stringify(apen));
// [{"naam":"Pipo","eet":"Banaan","soort":"Baviaan"},{"naam":"Guusje","eet":"Nootjes en bananen","soort":"Ringstaartmaki"}] 
```

## Functies

Een *functie* in een programmeertaal is een rijtje instructies die een _specifieke taak_ uitvoeren. Dit dient vooral om herhaling te voorkomen en om een programma overzichtelijk te houden.

```javascript
// Voorbeeld van een functie in node-red.
function selectInstant(msg) {
	if (msg.payload.hasOwnProperty('instant')) {
	    msg.payload = msg.payload.instant;
	} else {
	    msg.payload = "";
	}
	return msg;
}
```

## Classes
Een Class in Javascript is een "blauwdruk" (_template_) van een Object. Het dient om _properties_ en de _bijhorende functies_ bij elkaar te groeperen.
In vaktermen heet dit `encapsulatie` (inkapselen).

```javascript
class Teacher {
  constructor(name, course) {
    this.name = name;
    this.course = course;
  }
  // describe method describes the teacher
  describe() {
    return "Your teacher for " + this.course + " is " + this.name;
  }
}

let merijn = new Teacher("Merijn", "JavaScript");
let pieter = new Teacher("Pieter", "Python");

console.log(merijn.describe());
// Your teacher for JavaScript is Merijn
console.log(pieter.describe());
// Your teacher for Python is Pieter
```

Let op: De eigenschappen van een class die je binnen de _method_ benadert, moet je benaderen via `this`. 

# De eindopdracht (2026, blok 4)

## Wat ga je maken

We maken varianten op boter, kaas en eieren (tic-tac-toe in het Engels)

## Inspiratie en code "lenen" 

Natuurlijk is het internet een goede hulpbron; maar je maakt je werk wel zelf. Als je een tutorial volgt, geef duidelijk aan welke tutorial dat is. Dat maakt het mogelijk om bij het nakijken te zien wat je eigen inbreng is. De reden dat we willen dat je het _persoonlijk_ maakt, heeft hiermee ook te maken.

Dat geldt ook voor het gebruik van chat-bots. Je kunt ChatGPT heel veel laten doen voor je, maar dan leer je het zelf niet! Natuurlijk werkt jullie docent dagelijks met chatbots samen, maar dat is wel na 20+ jaar alles zelf doen!

Dus als je een chatbot gebruikt, houdt dan ajb bij wat je vraag was, wat de reactie was en _waarom_ dat een goed idee is (of juist niet).

## Bespreking

Je moet je werk helemaal kunnen uitleggen. Er komt aan het eind van het blok een moment waarop je met de docent het werk bespreekt. In dat gesprekje geef je een demo, geef je een rondleiding door de code en stelt de docent vragen over de code. Je moet elke regel kunnen uitleggen.


## boter-kaas-eieren-extended

Gegeven de start-html van dit pakket, maak een spel dat lijkt op boter-kaas en eieren.

Maar... er zijn wat uitbreidingen nodig:

Verplicht:
- Maak het bord groter dan 3x3
- Je speelt tegen een computerspeler: maak een simpele tegenspeler

Optioneel:
- Elke N beurten (laat te speler bij start N kiezen) komt er een RANDOM X of O in het veld op een lege plek
- Laat de gebruiker kiezen hoe groot het veld is (tot een max van 8x8 oid)


# Startpakket

Kopieer de inhoud van dit startpakket naar bestanden op je computer.

**HTML (index.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tic Tac Toe</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Tic Tac Toe</h1>
    <div class="status" id="status">Player X's turn</div>
    <div class="board" id="board">
        <div class="cell" id="r1c1"></div>
        <div class="cell" id="r1c2"></div>
        <div class="cell" id="r1c3"></div>
        <div class="cell" id="r2c1"></div>
        <div class="cell" id="r2c2"></div>
        <div class="cell" id="r2c3"></div>
        <div class="cell" id="r3c1"></div>
        <div class="cell" id="r3c2"></div>
        <div class="cell" id="r3c3"></div>
    </div>
</body>
</html>
```

**CSS (style.css):**

```css
body {
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    margin-top: 20px;
    padding: 20px;
}

.board {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 5px;
}

.cell {
    width: 100px;
    height: 100px;
    background-color: #f0f0f0;
    border: 2px solid #333;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 48px;
    font-weight: bold;
    cursor: pointer;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.status {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
}

h1 {
    color: #2c3e50;
}
```


**JavaScript (script.js)**

```javascript
// Jouw javascript hier

```


Veel plezier!


## Inleveren

- Maak een map met je naam erin als naam. (bijvoorbeeld `merijnvogel-js2025`)
- Maak van die map een zip-bestandje
- Lever het in via https://app.q-highschool.nl/ 


## Beoordeling

Het gaat om de Javascript en niet zozeer om de HTML en CSS. Een leuk uiterlijk is prettig en kan bonus opleveren maar is niet noodzakelijk om een hoog cijfer te halen. 

* Werk netjes, dus evenveel inspringen overal, gebruik code conventies of in elk geval doe steeds hetzelfde
* Geef functies en variabelen duidelijke namen. 
* Voorkom herhalingen; schrijf je niet meerdere keren hetzelfde of copy/paste, maar gebruikt loops en functies.
* Probeer grote stukken programma op te breken in kleinere stukken door functies te gebruiken. Wat "groot" is verschilt soms.


Op "deadline-donderdag" plan ik gesprekjes met jullie in. Dat kan de deadline-donderdag zelf zijn, of de uitstel-deadline-donderdag.
In een kort gesprekje kun je uitleggen wat je hebt gemaakt en waarom je bepaalde keuzes hebt gemaakt. Komen die dagen je niet uit, dan kunnen we in overleg een andere dag afspreken, zolang dat maar voor de deadline ligt!


# Enkele vreemde dingen  in Javascript

## Twee (of meer!) manieren om hetzelfde te bereiken

Javascript is in zoverre een beetje "raar", dat veel dingen op meerdere manieren kunnen. Dit komt deels door de roerige geschiedenis.

Het veranderen van een programmeertaal is erg lastig: Je wil niet dat bestaande sites en programma's niet meer werken. Dat is 'backwards compatibility', wat al bestaat moet blijven werken. Toch zijn er vaak mooiere en betere manieren om dingen te doen; de inzichten in hoe programmeren "zou moeten zijn" veranderen.


## Loops `for (a in iets)` versus `for (a of iets)`
(TODO)

## Gelijkheid: `==` vs `===`

`==` is bedoeld om twee dingen te vergelijken met elkaar. In Javascript is de betekenis daarvan een beetje "raar"; er zijn wat gevallen waarbij het resultaat soms anders is dan je verwacht; met name als je lijsten (`[]`) en objecten (`{}`) wil vergelijken. 

Om dit op te lossen is er de `===`  bijgekomen in de loop van de tijd; die vergelijkt eerst of twee kanten hetzelfde soort ding zijn (dus zijn het twee lijsten, dan weet het wat het moet doen). Dit voorkomt een hoop narigheid, dus het heeft de voorkeur om `===` te gebruiken.
```

