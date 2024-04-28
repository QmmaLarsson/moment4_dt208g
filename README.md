# Moment 4 i kursen DT208G, Programmering i TypeScript
**Namn:** Emma Larsson\
**Student-ID:** emla2309

### Beskrivning av webbplats
Detta är en webbplats med en tabell som visar kurser som ingår i utbildningen Webbutveckling på Mittuniversitetet. Det går att filtrera kurserna genom att skriva in en sökfras i input-fältet på sidan. Det går även att sortera kurserna i bokstavsordning genom att klicka på rubrikerna i tabellen.

Projektet skapades med hjälp av Angular CLI (https://github.com/angular/angular-cli) version 17.3.5.

### Beskrivning av lösning
**Skapa interface**\
Ett interface skapas med kommandot "ng generate interface model/course". Det fungerar som en mall för hur kurs-objektet ska se ut och vilka egenskaper det bör ha.

**Hämta data**\
För att kunna göra AJAX anrop till en server måste HttpClient-modulen installeras. Detta görs i app.module.ts. Därefter skapas en service skapas med kommandot "ng generate service service/course". HttpClient för att göra ett GET-anrop till URL:en https://webbutveckling.miun.se/files/ramschema_ht23.json. Svaret returneras som en array.

**Skapa tabell**\
En komponent skapas med kommandot "ng generate component courses". I denna skapas i sin tur en tabell. En *ng-loop används för att skriva ut alla kurser i tabellen. Interpolation används för att binda datan från komponentklassen till HTML-koden. Detta görs med hjälp av dubbla måsvingar.

**Filtrera data**\
Two-way binding(ngModel) används för att binda värdet på det användaren skriver in i input-fälten till variabeln filterValue som finns i komponentklassen. Detta innebär att ändringar i inputfältet uppdaterar värdet på variabeln. Även eventbinding används, när en användare skriver i input-fältet så körs metoden applyFilter(). Metoden jämför filterValue med de kurser som finns i listan. Innan jämförelsen utförs användes också .toLowerCase() för att konvertera filtervärdet och kurskoderna/kursnamnen till små bokstäver.

**Sortera data**\
Eventbinding används för att binda klickhändelserna på rubrikerna i tabellen till funktionen sortCourse() som finns i komponentklassen. Vid klick på en rubrik så körs en metod som sorterar kurserna i bokstavsorning, vid dubbla klick så vänds ordningen i listan.

### Installera projekt

För att installera och börja använda projektet, följ nedanstående steg:
* Klona projektet från Github. För att göra detta, nagivera till den mapp där du vill spara projektet, skriv in "git clone" följt av Github-repots URL.
* Installera beroenden. För att göra detta använd kommandot "npm install".
* Kör projektet. För att göra detta använd kommandot "ng serve".
* Kommandot för att bygga projektet är "ng build".
