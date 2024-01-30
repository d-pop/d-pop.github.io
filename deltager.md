---
layout: lecture
title: Deltag
---

Hvis I har grundlæggende færdigheder i programmering og har lyst til at løse problemer i samarbejde med andre, så er I målgruppen for at deltage i D-Pop.

Det er sjovest, når man er tre personer.
Papir og blyant er gode at have ved hånden.
I skal have adgang til én computer som man kan programmere på.

## Hvad skal man kunne?

Mindst én af jer skal kunne programmere – variable, selektion (`if`), gentagelse (`for`, `while`), strenghåndtering, grundlæggende matematiske operationer (addition, multiplikation, osv.), indlæsning, udskrift.
  
I skal desuden kunne snakke sammen om hinandens gode og dårlige ideer.
Det kræver gode samarbejdsrutiner og behagelige omgangsformer.

## Hvilke sprog?

Problemerne til D-Pop formuleres på dansk.

Løsningerne skrives i et af de gængse, tekstbaserede programmeringssprog, som fx Python, Java, forskellige C-dialekter, Javascript, Kotlin, osv.

Se [listen af programmeringssprog på Kattis](https://open.kattis.com/help/).

## Hvor er det henne?

Problemerne fra sidste år kan findes på [dpop23.kattis.com](https://dpop22.kattis.com).
<!-- %TODO: Insert new Kattis link when ready 
Problemerne kan findes på dommeren [dpop22.kattis.com](https://dpop22.kattis.com) fredag d. 19. april 2024 kl. 16.
 -->
IT-Universitetet i København afholder et åbent D-Pop-arrangement 
* fredag d. 19. april 2024, kl. 16–18.
Alle er velkomne.
Nogle af ITUs søde og dygtige studerende står til rådighed med hjælp og vejledning som _d-popstjerner_.
Spørg os om alt muligt.

## Forberedelse

Hvis I har lyst til at forberede jer, mest for at sikre at de tekniske detaljer er på plads til arrangemtet, kan I gøre det på [dpopopvarmning.kattis.com](https://dpopopvarmning.kattis.com).
Begynd med »Hej verden!«, »Skru up!«, »Forskel« og »Gæt et tal«.
Fortsæt med »Chokoladeæsken«.
Der er masser af andre problemer – mange af dem så svære, at I garanteret ikke kan løse dem.

Kattis-platformen har gode hjælpesider for de relevante programmeringssprog, som blandt andet indeholder en mønsterløsning for »Forskel«.

# Første skridt på Åben Kattis

Hvis I har lyst, kan I også følge skridt-for-skridt-vejledningen forneden, som taler jeg igennem platformen _Open Kattis_ og bruger Python eller Javascript. Hvis I har klaret de første to-tre problemer forneden, er I mere end parate til D-Pop.

## Brugerprofil på Kattis

* Besøg [open.kattis.com](http://open.kattis.com)
* Vælg »Log in« in højre venstre hjørne, følg instruktionerne

## Første problem: Hello, World!

* Find kattisproblemet **Hello World!** (`hello`) enten ved at søge på Kattis eller direkte på [https://open.kattis.com/problems/hello](https://open.kattis.com/problems/hello). 
* Læs problembeskrivelsen
* Tryk _Submit_, derefter _Switch to Editor_
* Her er to løsninger lige til at skrive af:

Python:
```python
print("Hello World!")
```
JavaScript (Node.js)
```javascript
console.log("Hello World!")
```

Husk at angive det rigtige programmeringssprog i venstre hjørne, tryk på _Submit_.

Du burde nu have fået dommen `Accepted`. (Ellers: ret dine fejl, prøv igen.)

Gå til din brugerprofil (højre øvre hjørne) og se alle dine indsendelser. Du kan altid gå tilbage til gamle indsendelser, ændre og sende forbedrede udgaver.


## Andet problem: Echo Echo Echo

* Find `echoechoecho`
* Hvis du har en høj frustrationstærskel, brug kattiseditoren til også at løse dette problem
* Bedre: gå til [https://onecompiler.com/javascript/](https://onecompiler.com/javascript/) henholdsvis [https://onecompiler.com/python/](https://onecompiler.com/python/). Hvis du har et udviklingsmiljø på din egen maskine, bruger du bare den.
* Skriv programmet i venstre vindue.
* Skriv indlæsnigen (»Hello« eller »ECHO«) i vinduet »STDIN«, tryk på »RUN«.

Pythonløsning:
```python
skrig = input()
print(skrig)
print(skrig)
print(skrig)
```

Javascriptløsningen er betydelig mere omstændig, fordi Javascript håndterer standardindlæsning ved brug af såkaldt hændelsesstyret programmering, hvilket fører til tre kryptiske første linjer. Detaljerne er uvæsentlige for os, men variablen `skrig` indeholder efter `=> {` værdien af inlæsningen, ganske som tildelingen `skrig = input()` gør i Python.
```javascript
const lytter = require("readline").createInterface({input: process.stdin});

lytter.on('line', (skrig) => {
	console.log(skrig);
	console.log(skrig);
	console.log(skrig);
});
```

## Tredje problem: Stuck In A Time Loop

Et godt næste problem er nu `timeloop`. Her er to skeletter, hvor der mangler kode ved `[...]`.  Først i Python:

```python
N = int(input())
i = 1
while i <= N:
    # [...]
    i = i + 1
```

Og i Javascript:

```javascript
const rl = require('readline').createInterface({input: process.stdin});

rl.on('line', linje => {
  const N = parseInt(linje);
  let i = 1;
  while (i <= N) {
    // [...]
    i = i + 1;
  }
});
```

## Fjerde problem: Odd Echo

* Find `oddecho`

Løsningen for testgruppe 2 kræver typekonvertering (indlæsningen er altid strenge), evnen at læse et variabelt antal linjer, og en smule problemløsning (hvordan skelner vi lige linjer fra ulige?). Det kan gøres på mange måder.

```python
N = int(input())
ulige = True
for _ in range(N):
    linje = input()
    if ulige:
        print(linje)
    ulige = not ulige
```

Javascriptløsningen er endnu mere omstændigt. Løsningens logik havner i kodestumpen for `løs_problemet`.

```javascript
const rl = require('readline').createInterface({input: process.stdin});

var indlæsning = [];
rl.on('line', linje => { indlæsning.push(linje) });
rl.on('close', () => { løs_problemet() });

function løs_problemet() {
	const N = parseInt(indlæsning[0]);
	let ulige = true;
	let i = 1;
	while (i <= N) {
		if (ulige)
			console.log(indlæsning[i]);
		ulige = !(ulige);
		i = i + 1;
	}
}
```

