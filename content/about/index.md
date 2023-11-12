---
Title: About
Description: Min om-sida.
# hidden: true
---

## Använda SASS tekniker {.lightbulb-icon}

I denna uppgift har jag använt mig av följande SASS-tekniker

### Variabler
Variabler liknar till stor del hur man skriver i många programmeringsspråk. Genom att skapa variabler är det möjligt att skapa struktur och skalbarhet eftersom det räcker med att bara ändra i själva variabeln för att dynamiskt ändra alla element som använder sig av den variabeln.<br>
<br>
För att skapa en variabel skriver man ett dollar-tecken följt av namnet på variabeln och till slut värdet. För att sedan använda variabeln i övriga stilmallar ersätter man värdet till namnet på den variabeln man skapat.
### Nesting
SASS erbjuder ett smidigare sätt att överskådligt strukturera upp klasser genom att "nästla" selektorer så att det liknar den hierarki som vi finner i HTML. I denna uppgift har jag således strävat efter att organisera CSS-koden bättre genom att nästla selektorer i deras respektive stilmallar på så vis att jag lättare kan se vilka "block" som hör till varandra.

### Moduler (import/use)
För att få lite bättre ordning på alla stilmallar och importer av fonter så som fontawesome och externa google fonter så har jag valt att använda mig av @import och @use som går att ta del av i SASS. Kort sagt har jag delat upp det som så att allt som behövs för att få fontawesome fungera ligger i en modul och de externa fonter som jag hämtar från google ligger i sin egen modul.<br>
<br>
Jag har även valt att skapa en modul för de FA-ikoner som jag använder i artiklarnas headers på sidan då det krävdes lite skräddarsydd behandling för att få detta att fungera som jag ville. Genom att ha dessa selektorer för sig i sin egen modul blir det hela lite mer överskådligt och behändligt.<br>
<br>
Jag bestämde mig även för att skapa en modul för variablerna (_vars.scss) då det kändes logiskt och smidigt att ha dessa för sig i sin egen stilmall.

### Övrigt
Det finns så klart fortfarande fler tekniker inom SASS som jag ännu inte använt mig av så som t.ex. operatorer och mixins -- det återstår att se om jag i framtida uppgifter kan ha större användning utav av dessa funktioner! 
