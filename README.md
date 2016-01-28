# NumberParser 
Ik zoek 'even snel' met Google naar een PHP functie die een getal converteert naar woorden. Ik vind voornamelijk topics waarin mensen vragen hoe dat moet. In enkele gevallen zit daar een stukje brakke code bij die voor de helft werkt. De oplossingen die mensen geven zijn treurig. Het feit dat deze functie niet even zo makkelijk te vinden is op het internet is een ernstig probleem in de wereld dat ik absoluut niet aan kan zien en ik voel de morele verplichting om een oplossing te bieden. Voor de zoveelste keer betekent 'even snel' iets opzoeken dat ik mijn kostbare tijd opoffer aan de maatschappij.

De PHP class in deze repository is eigenlijk de NumberParser Service class op <a href="https://github.com/TijdschriftVoorGeneeskunde/TijdschriftVoorGeneeskunde/blob/fbc745993d36d483ffa1dd1c35524b11012349f2/src/AppBundle/Service/NumberParser.php">https://github.com/TijdschriftVoorGeneeskunde/TijdschriftVoorGeneeskunde/blob/fbc745993d36d483ffa1dd1c35524b11012349f2/src/AppBundle/Service/NumberParser.php</a>, door mij aangepast om namespace/applicatie onafhankelijk te werken.

Ik heb NumberParser herschreven in een aantal talen / vormen
* NumberParser PHP Class
* NumberParser Javascript Object
* NumberParser Node.js / NPM module

### PHP Voorbeeld
Gebruik NumberParser in je PHP script.
```
include 'NumberParser.php';

$numparser  = new NumberParser();
print $numparser->parseNumber(7564928); // zeven miljoen vijfhonderdvierenzestigduizend negenhonderdachtentwintig
```

### Javascript Voorbeeld
```javascript
NumberParser.parseNumber(7564928); // zeven miljoen vijfhonderdvierenzestigduizend negenhonderdachtentwintig
```

### Webpagina Voorbeeld
NumberParser insluiten in de head van je webpagina om het te kunnen gebruiken.
```html
<script type="application/javascript" src="NumberParser.Node.js"></script>
<script type="application/javascript">
	NumberParser.parseNumber(7564928); // zeven miljoen vijfhonderdvierenzestigduizend negenhonderdachtentwintig
</script>
```

### Node.js / NPM require
Ik heb helemaal niets beters te doen en daarom is NumberParser ook als Node module inbegrepen. Het bestand NumberParser.Node.js is identiek aan NumberParser.js met als enige verschil dat het object toegewezen is aan module.exports zodat het kan worden ge-required.
```javascript
var NumberParser = require('./NumberParser.Node');
NumberParser.parseNumber(7564928); // zeven miljoen vijfhonderdvierenzestigduizend negenhonderdachtentwintig
```

## Opmerkingen
Omdat ik overal commentaar op heb.

#### fmod
Javascript heeft geen fmod functie. GitHub gebruiker wteuber schreef een Javascript equivalent van PHP fmod (inbegrepen)
```javascript
/* https://gist.github.com/wteuber/6241786 */
function fmod(a,b) { return Number((a - (Math.floor(a / b) * b)).toPrecision(8)); };
```

#### Overig
Binnen ennkele tijd voeg ik nog een NumberParser toe geschreven in C# en C++ en zal ik tevens NumberParser er ook bij doen als Shared Library (.dll) voor in je .NET applicatie.