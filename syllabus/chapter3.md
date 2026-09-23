# Hoofdstuk 3: Javascript en de browser (en Object)

In je browser kun je Javascript gebruiken via de `console`; maar dat is een beetje "flauw"... we willen eigenlijk websites in beweging brengen!

Wil je zelf expermenteren, maak een mapje aan op je laptop/computer en copy-paste deze stukjes code:
(PS let op dat windows niet zelfs een bestands-extensie toevoegt, als je 'new text document' kiest, maakt windows er `.txt` van; vraag AI om uitleg hoe je dat fixt)

- maak een bestand `style.css` met daarin: 

```css
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f4f4f9;
}

.container {
    text-align: center;
    background: white;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

input {
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-bottom: 10px;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

#output {
    margin-top: 20px;
    font-size: 18px;
    color: #333;
    font-weight: bold;
}
```


- maak een bestand `index.html` met daarin: 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Demo</title>
    <link rel="stylesheet" href="style.css"> <!-- dit laadt de stylesheet in en koppelt het aan de html pagina -->
</head>
<body>

    <div class="container">
        <h1>Input Demo</h1>
        <input type="text" id="myInput" placeholder="Type something here...">
        <button id="myButton">Click Me</button>
        <p id="output"></p>
    </div>

    <script src="script.js" defer></script>
</body>
</html>
```

- maak een bestand `script.js` met daarin: 

```javascript
const inputField = document.getElementById('myInput');
const actionButton = document.getElementById('myButton');
const outputText = document.getElementById('output');

actionButton.addEventListener('click', function() {
    const value = inputField.value;
    
    if (value === "") {
        outputText.textContent = "Please enter something!";
        outputText.style.color = "red";
    } else {
        outputText.textContent = "You entered: " + value;
        outputText.style.color = "dark blue";
        inputField.value = ""; 
    }
});
```

### Wat herken je al aan deze Javascript?

Er zitten constantes in, er gebeuren toewijzingen, er staan teksten (strings) in.

### Wat is er nieuw?

Je ziet vaak een `.` staan; dit zijn `Object`s in Javascript.

Een object is een opslag van `eigenschappen`. Een `eigenschap` heeft een naam, en een waarde.


## Object

Een object slaat een *waarde* op bij een *sleutel*, zodat je die terug kunt halen. Dit noemen we in Javascript *eigenschappen* (**properties** in het Engels).

Je kunt een object schrijven in code met `{}`:

```javascript
let docent = {
    "naam": "Merijn Vogel",
    "schoolvak": "Informatica",
    "geboortejaar": 1975
    
};

// en informatie er uit halen met de `.`:

console.log(docent.naam);
console.log(docent.schoolvak);
console.log("leeftijd als die al is jarig geweest op 12 september: " + (2026 - docent.geboortejaar));
```

- Welke eigenschappen heeft het object `docent` in bovenstaande code?

- Leeftijd is niet een eigenschap van het object zelf, waarom niet?



## De DOM / de browser

Laten we even inzoomen op de eerste regel van de voorbeeldcode:

```javascript
const inputField = document.getElementById('myInput');
```

We zien een toewijzing (assignment) aan de constante `inputField`. 

Deze wordt gehaalt uit het object `document`. Dat object is voor javascript de manier om dingen te benaderen die in html staan. Die 'dingen' noemen we `elementen`. `Elementen` zie je in html terug als 
de woordjes tussen spitse haakjes, bvb: `<p>`. Zo'n element in HTML is ook weer een object met daarbinnen eigenschappen, bijvoorbeeld het `id`. `id` is speciaal: het identificeert precies dat element[1].

Dan `getElementById`: dit is een **functie** die tegelijk een **eigenschap** is van een object. Een functie in Javascript is, net zoals in Python, code die je kunt **aanroepen**.  [2]

`getElementById` wordt aangeroepen met een string-waarde als **parameter**.

Het resultaat van die functie is een object. Dat object heeft eigenschappen die specifiek zijn voor `input`-elementen van Javascript, zoals `value`.



> [1]: Je kunt natuurlijk de fout maken en een id twee keer gebruiken. Dat mag officieel niet, maar browsers doen toch hun best een pagina met zulke fouten weer te geven; daardoor zie je programmeerfouten in html gauw over het hoofd.

> [2]: een **functie** die ook een **property** is, heet in Javascript ook wel een **method**. Je hoeft zelf geen objecten te maken met functies erin voor deze module, al zal ik het in een demonstratie wel een keer laten zien.
