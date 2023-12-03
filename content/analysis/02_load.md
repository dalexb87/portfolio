---
Title: Laddningstider
Description: This is our Loadtimes page.
Template: analysis
---

Laddningstider
=======================



I den här uppgiften ska jag titta på laddningstider hos 3 olika webbplatser. För att kunna uföra en lite mer rättvisare bedömning ska jag även välja undersidor från respektive webbplats.<br>
<br>
Jag ska förutom laddningstiden även se hur många resurser som laddas in på varje sida samt den totala filstorleken - denna mätning utförs 3 gånger per sida och jag tar sedan medelvärdet av hur lång tid det tog att ladda in allt material för respektive sida.<br>
<br>
Efter insamling av mätvärden ska jag föra en diskussion kring vilka förbättringar som webbplatsen eventuellt skulle kunna göra och i enlighet med detta sammanfatta mitt resultat för att se vilka de mest förekommande förbättringsåtgärder tycks vara för de webbplatser jag valt att analysera. 


Urval
-----------------------

Webbplatserna som jag valt att undersöka i denna uppgift är:

- [crtzoo](https://www.crtzoo.se)
- [vetzoo](https://www.vetzoo.se)
- [zooplus](https://www.zooplus.se)

<br>
Min tanke var som så att online-butiker har i regel många bilder för att presentera sitt urval av olika produkter - och denna uppgift har ju handlat mycket om bilder och hur det påverkar laddningstider hos webbplatser.<br>
<br>
Samtidigt ville jag hålla mig till ett tema och då fick det bli zoobutiker.<br>
Det kändes lite roligare och mer passande för min webbplats som helhet och det passade även bra att mitt urval hade undersidor som liknade varandra, vilket tillför att min analys blir desto rättvisare.  


Metod
-----------------------

Den empiri som samlats in och som presenteras i resultatet har tillförskaffats tack vare följande verktyg:

**Google Pagespeed**<br>
    <br>
    Google erbjuder denna tjänst där man enkelt kan länka till en webbsida och få den betygsatt grundat på ett flertal kriterier. I denna uppgift är det främst "performance" som varit av intresse. Jag har dock lagt märke till att betygsättningen har en tendens att fluktuera en hel del men det är ändå ett värdefullt verktyg för att få ett hum om vad som bör eller kan åtgärdas på en webbsida.

**Devtools (Network Tab)**<br>
    <br>
    Varje webbutvecklares bästa vän devtools har möjligheten att mäta nätverksaktiviteten varje gång en webbsida besöks. I den här uppgiften har detta verktyg använts som så att för varje sida som skulle undersökas laddade jag om sidan 3 gånger och skrev ner värdena under *"Requests"*, *"Transferred"* samt *"Load"*.<br>
    <br>
    Jag räknade sedan ut medelvärdet för samtliga. Det tål även att nämnas att betyget från "performance" (google pagespeed) har genomgått samma process.

**Google sheets**<br>
    <br>
    Ännu en tjänst från Google. Att kunna skapa excel-ark online och sedan "embedda" det direkt i ett dokument som detta underlättar presentationen avsevärt.<br>
    <br>
    Jag hade dock lite svårt att komma på hur jag som bäst skulle presentera den insamlade datan - och nackdelen är väl det att kalkylbladet nedan inte är särskilt anpassat för mobila enheter.

Resultat
-----------------------

### Datainsamling

<iframe class="pageload-spreadsheet" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRQqinpV3Z_08TlXpflX1S3YPL2Gfy-0AycJsHDujMnnIw44wiq2fVHgYKarN9_XvU8TIqyRPW_ecby/pubhtml?widget=true&amp;headers=false"></iframe>
<br>

I detta kalkylblad går det enkelt att se vilka webbplatser och respektive undersidor som har undersökts i denna uppgift. Förutom webbplatsernas landningssidor är de sidor som jag har kollat på följande:

- [crtzoo/smådjur](https://www.crtzoo.se/smadjur)
- [crtzoo/varumärken](https://www.crtzoo.se/varumarken)
- [vetzoo/övriga-djur](https://vetzoo.se/ovriga-djur)
- [vetzoo/varumärken](https://vetzoo.se/product/varumarken)
- [zooplus/gnagare_smådjur](https://www.zooplus.se/shop/gnagare_smadjur)
- [zooplus/märkesfoder](https://www.zooplus.se/shop/markesfoder)

<br>
...och som synes är urvalet av webbsidor snarlika, där tanken är att mätningsvärden och bedömningen i min analys ska vara rättvisa.<br>
<br>
I kalkylbladet syftar "Betyg" på *performance*-betyget fått från Google Pagespeed för samtliga webbsidor. Vidare är *Load*, *Requests* och *Transferred* värden som jag fått från network-fliken i devtools.<br>
<br>
Mätvärden för så väl desktop som mobil har insamlats - där i det senare fallet har använts "throttling" i devtools för att simulera ett 4G bandbredd, vilket även Google Pagespeed verkar grunda sin "mobile" bedömning på.

### Crtzoo

![bild på crtzoo webbsida](%assets_url%/img/zoo/crtzoo.jpg){.website-screencap}

Kollar man över den data som insamlats ser vi snart att crtzoo's startsida är betydligt tyngre än sina konkurrenter med över 15 MB av data som måste hämtas innan sidan laddats klart. Trots detta tar det drygt 2 sekunder för det mest väsentliga att skrivas ut på skärmen. Undersidorna ligger tätt inpå även om mängden data som överförs är ungefär en fjärdedel av startsidans filstorlek.<br>
<br>
Värre blir det när man kollar på prestandan för mobiler. Här fick jag fram snittet att det tog cirka hela 17 sekunder för merparten att laddas in och undersidorna ligger runt 10 sekunder. Något som reflekteras i det mycket låga betyget från google pagespeed.

Undersöker man webbplatsen i devtools ser vi direkt att de två översta bilderna på startsidan är onödigt tunga, totalt över 5 MB. Bildformatet är dessutom png trots att ingen transparens skulle krävas för dessa bilderna.<br>
<br>
Vidare har pageload mer att säga om just bilder och vi märker snart att det inte enbart är dessa som har onödigt bildformat. Dessutom är de inte skalade efter innehållet utan man tycks använda orginalstorleken vilket totalt leder till att många megabyte måste överföras innan sidan laddas klart. Det finns dessutom ett par script som körs innan sidan kan rendera och även där finns det utrymme för förbättring.<br>
<br>
Överlag verkar det dock som att bilder är en mycket stor anledning till det låga betyget och att sidan laddas så långtsamt framförallt på mobila enheter - om man hade croppat bilder till den storlek som krävs för innehållet samt sparat om bilderna till ett mer passande format så som jpg så tror jag att man genast skulle få se en enorm skillnad på laddningstiden.

### Vetzoo

![bild på vetzoo webbsida](%assets_url%/img/zoo/vetzoo.jpg){.website-screencap}

För vetzoo är mätvärdena överlag något bättre än crtzoo. Webbsidor tar i snitt lite kortare tid att laddas in (i synnerhet undersida 2) och de får högre betyg från pagespeed - men framförallt så är startsidan långt ifrån lika tung som crtzoo vilket till mindre del även stämmer in på undersida 2.<br>
<br>
Kollar man på mobila enheter så får webbplatsen i stort sett mer än dubbelt betyg från pagespeed performance gradering och vi kan även snabbt se att sidorna tar avsevärt kortare tid att ritas.<br>
<br>
Trots detta tar det ungefär 5 sekunder för två av de undersidor som undersökts - där den tredje sidan "varumärken"  tar cirka 2.5 sekunder vilket även återspeglas i den mängd data som överförts, enbart 475 kilobyte! <br>
<br>
Även vetzoo hade kunnat slipa lite på sina bilder för att spara på kilobyten, men här har man iallafall varit noga med att använda hyffsat filformat. Oavsett föreslår pagespeed att man exempelvis hade kunnat göra om bilderna till WebP-format för att verkligen skala ner på storleken.<br>
<br>
Det största problemet tycks dock vara script-filter som blockerar rendering av sidan. Då bör man kolla lite närmare på vilka script som kan väntas med att köras tills efter det som man bedömer mest viktigast laddats färdigt. Man kan även undersöka om det används någon onödig kod i script eller stilmallar.


### Zooplus

![bild på zooplus webbsida](%assets_url%/img/zoo/zooplus.jpg){.website-screencap}

Sist men absolut inte minst har vi zooplus. I samma trend fortsätter betyget att stiga, denna gången betydligt högre än de föregående webbplatsernas som bedömts. Runt 70-80 för desktop och 40-50 för mobil. Likaså tar sidorna i snitt lite kortare tid på sig att laddas och inte är det då så konstigt att filstorleken på webbsidorna inte är så tunga.<br>
<br>
Detta är framförallt tydligt på mobilt bredband där man lyckats skala ner storleken, i synnerhet de två undersidor som undersökts där filerna totalt är långt under 1 megabyte. Effekten av detta syns åter på laddningstider för undersidorna i snitt tog under 2 sekunder samt startsidan som tog lite över 2 och en halv. I vilket fall som helst betydligt snabbare än sina konkurrenter och en klar vinnare i detta testet.<br>
<br>
Att på rak arm kunna säga vad denna webbplats skulle kunna göra för att förbättra sig när det kommer till laddningstider är svårt då det inte finns några omedelbara varningstecken. Den laddar snabbt och är relativt "nätt" till sitt utseende och får dessutom höga poäng av pagespeed.<br>
<br>
Det finns likväl några script som stör rendering av sidan, något som samtliga webbplatser har haft problem med hittils. Eftersom man lyckats hålla ner på filstorlekarna är detta kanske en icke-fråga för de vanligaste fallen, men om man verkligen hade velat skala ner webbsidorna ytterligare så är det scripten man bör undersöka närmre. I devtools kan vi snart se att det är alla javascript filer som verkar ta längst tid på sig att ladda in och om de då ligger i förgrunden och stör renderingen av sidan kan det leda till sämre laddningstiden framförallt på mobila enheter.


Analys
-----------------------

### Sammanfattning

Kollar man lite närmre på den datainsamling i mitt kalkylblad kan man börja tyda ett mönster. Webbsidor som är tyngre tar helt enkelt längre tid att ladda klart, så långt råder det inga tvivel. I en värld av fiberuppkopplingar har detta kanske ingen större påverkan för just stationära datorer där man i regel har ett snabbare bredband.<br>
<br>
Men än så länge ligger mobila enheter och deras uppkoppling åtminstone ett steg bakom. Jag vill därför mena på att man bör i största möjliga mån skala ner på filstorlekarna, särskilt när det gäller bildmaterial då det ändå är relativt enkelt att optimera och specificera vilka bilder som faktiskt ska laddas in för mobila skärmar.<br>
<br>
I min analys ser vi rätt så tydligt att crtzoo.se har en del att jobba på när det gäller filstorlek. Där bilderna är absolut det största problemet. Omskalning så väl som omsparning till vettiga format skulle krävas för att optimera laddningstiden.<br>
<br>
Även om optimering av bilder är det största problemet så är det inte det vanligaste, åtminstone inte i mitt urval. Renderingen av samtliga sidor tycks blockeras av olika script som har företräde. Det är svårt att säga hur stor skillnad detta egentligen skulle göra utan att jämföra sida vid sida men att det är ett vanligt förekommande problem som kan störa användarupplevelsen är iallafall ett faktum.<br>
<br>
En annan faktor som även pagespeed tar up är så kallat "lazy-loading". Vilket i korta drag innebär att innehåll enbart renderas när det väl krävs. I praktiken kan detta exempelvis leda till att bilder inte laddas in före man scrollar till dem - förslagsvis kan man kanske använda en mycket suddig bild med dålig upplösning som placeholder innan den riktiga bilden efterfrågas.

### Godtagbar laddningstid

Det är generellt ansett att en webbplats bör tar mellan 1-3 sekunder för kopplat kabelnät och jag skulle säga att det passar väl in även på min personliga erfarenhet. Tar en webbsida längre än 4 sekunder så kan det beroende på innehållet mycket väl vara så att jag börjar söka alternativ.<br>
<br>
För mobila enheter tycks det finnas avvikande åsikter men enligt studier som bland annat [denna artikel](https://blog.hubspot.com/marketing/page-load-time-conversion-rates) tar upp så verkar snittet röra sig om runt 8-10 sekunder. Hur lång tid en webbsida *bör* ladda färdigt på mobil är däremot en annan fråga som är lite svårare att besvara.<br>
<br>
Personligen surfar jag inte så mycket på mobilen så jag kan inte påstå att detta påverkar mig något större och i de få fallen där jag faktiskt gör det så brukar jag ändå syssla med annat vid sidan om - och då gör det mig inget att en sida tar lite längre tid att ladda färdigt.<br>
<br>
Jämför man dessa laddningstider med det resultat jag fått från samtliga webbsidor så ser vi att för hög uppkoppling så klarar samtliga gränsvärdet på 3 sekunder med god marginal. Jag vågar även påstå att både vetzoo och zooplus klarar sig fint - däremot har crtzoo som redan tidigare nämnt en del att jobba på. Att startsidan tar över 15 sekunder känns inte acceptabeln hur man än vrider och vänder på det. Särskilt inte då en webbplats landningssidan är ansiktet utåt så att säga vilket leder till att laddningstiden är av större vikt. Även undersidor tar mellan 8-10 sekudner på sig vilket även det känns något för långsamt.

### Utsedd vinnare

**Rangordning**

1. Zooplus **VINNARE**  
2. Vetzoo
3. Crtzoo

<br>
Lustigt nog så har mitt urval visat på bättre optimering för varje webbplats som jag undersökt, där crtzoo.se absolut har sämst prestanda. Vetzoo ligger något efter men i detta test som jag utfört, där framförallt laddningstiden har stått i fokus, så är det zooplus.se som ligger på topp med goda marginaler i stort sett samtliga mätningar.<br>
<br>
Anledningen till detta är troligen på grund av att man varit återhållsam med bilder men även för att man inte använt sig av png:er i onödan. Vidare verkar de flesta bilder vara skalade efter innehållet.<br>
<br>
På fiberuppkoppling är det inga konstigheter. Sidorna laddar in mycket snabbt utan strul. På 4G, vilket är den throttling som jag använt mig av för att testa samtliga sidor i devtools så är den som underförstått något långsammare, men håller sig i regel ändå runt eller under 3 sekunder - vilket vore godtagbart även för stationära datorer om man ser till det universala gränssnittet!


Referenser
-----------------------

Min bedömning av webbplatserna har grundat sig i verktyget pageload försedd av Google samt network-fliken i devtools.

Övrigt
-----------------------

Jag (Daniel Blom) har utfört den här uppgiften enskilt.