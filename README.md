# SkansenWikidata
Beskrivning av lite det som gjorts och utmaningar. Skapa gärna [nya issues](https://github.com/salgo60/SkansenWikidata/issues) med frågor...
* Exempel https://github.com/salgo60/SkansenWikidata/issues/2 - enklast är om du skapar ett konto i GITHUB https://github.com/join
## Plug-in
* [EasyQuery](https://www.wikidata.org/wiki/Special:Preferences): Ett verktyg som lägger till en ikon för att lättare hitta objekt samma uttalanden.
   * [video hur man aktiverar den](https://youtu.be/r0fjNkI9M9Q)
## Test av samma som Skansen
* Museala miljöer - TBA
### SKOS -  Simple Knowledge Organization System
Är ett sätt att utrycka semantiska likheter A är ung. som B se [exempel skos:closeMatch skos:relatedMatch ...](https://www.w3.org/TR/skos-reference/#mapping) 
 * exempel hur det lätt blir teoretiskt vad som är samma som "[When owl:sameAs Isn’t the Same: An Analysis of Identity in Linked Data](https://link.springer.com/content/pdf/10.1007%2F978-3-642-17746-0_20.pdf)"
 
* utmaningar som jag ser
   * Stegeborgs slott / ruin [funderingar vilka objekt vi bör ha](https://phabricator.wikimedia.org/T225522#5284001)

<img width="948" alt="image" src="https://user-images.githubusercontent.com/14206509/186656453-acaaae06-1088-46fd-b3ea-d85a41868134.png">

* Riksarkivet Tora projektet gjorde ett bra försök men tveksam hur det används se om [Tora](https://riksarkivet.se/tora) -  ["Historical Settlement Units as Linked Open Data"](http://ceur-ws.org/Vol-2364/24_paper.pdf)
* Trovärdighet på olika källor tycker jag Wikidata/Wikipedia inte fullt ut har löst - jag [frågade Denny i denna video som skapat Wikidata](https://youtu.be/VdAc0JReVSw?t=2450) och skrev ned detta "[We need a better model communicating quality/relevance of sources in Wikidata / Provenance" T222142](https://phabricator.wikimedia.org/T222142) 
* Video där jag visar hur iNaturalist har snyggt kopplats ihop med Wikicommons vi kan hitta de senaste bilderna av skator där vi söker **fria licenser** / arter Pica Pica --> iNaturlist [Taxonomy taxa/891696](https://www.inaturalist.org/taxa/891696)  där vi hämtar bilder med research level dvs. där flera sagt att det är en skata se [video 7 min](https://youtu.be/8FGFc5rljhc?t=421)
## Skapa en egen Wikidata --> Wikibase.cloud dvs. dom hostar en egen wikibase för er
* [om projektet](https://www.wikibase.cloud/)  
  * exempel hur jag skapade data för [kommunernas anslagstavlor](https://sweopendata.wikibase.cloud/wiki/Kommuner) i en egen wikibase som ligger i Wikibase.cloud
    * jag kombinerar då mitt wikibase data med Wikidata genom SPARQL federation [se sökfråga](https://sweopendata.wikibase.cloud/query/index.html#%23%23title%3A%20Kommuners%20Anslagstavla%20-%20test%20Wikibase%0A%23defaultView%3AMap%7B%22hide%22%3A%5B%22%3Fcoord%22%5D%7D%0A%0APREFIX%20wb%3A%20%3Chttps%3A%2F%2Fsweopendata.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20wbt%3A%20%3Chttps%3A%2F%2Fsweopendata.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3FrLabel%20%3Fvideo%20%3Fcoord%20%3Fimg%20%3FwdQ%20%3FsvWikipedia%20WHERE%20%7B%0A%20%20VALUES%20%20%3FAnslagsTavla%20%7Bwb%3AQ240%7D%0A%20%20%20%3Fr%20wbt%3AP2%20%3FAnslagsTavla%20.%0A%20%20%20%3Fr%20wbt%3AP11%20%3Fvideo.%0A%20%20%3Fr%20wbt%3AP1%20%3FwdQ%0A%20%20BIND%28URI%28concat%28%22http%3A%2F%2Fwww.wikidata.org%2Fentity%2F%22%2C%3FwdQ%29%29%20AS%20%3Fwikidata_iri%29%0A%20%20%0A%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata_iri%20wdt%3AP625%20%3Fcoord.%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP41%20%3Fflag%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP94%20%3Fcoat%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP154%20%3Flogo%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP18%20%3Fimage%20%7D%20%20%0A%20%20%20BIND%28%20COALESCE%28%3Fflag%2C%20%3Fcoat%2C%20%3Flogo%2C%20%3Fimage%29%20as%20%3Fimg%20%29%0A%20%20%20OPTIONAL%20%7B%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3Aabout%20%3Fwikidata_iri%20.%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3AinLanguage%20%22sv%22%20.%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fsv.wikipedia.org%2F%3E%20.%0A%20%20%20%20%7D%0A%20%20%20%20%7D%0A%09SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22sv%2Cen%22.%20%7D%0A%7D)
* vill man prata wikibase.cloud finns en Telegram grupp **"Wikibase.Cloud / WBStack"** som har bra fart
## Historiska yrken
Sammanställing jag gjorde av Historiska yrken se [GITHUB](https://github.com/salgo60/HISCOKoder) plus skickade ut en fråga rill DIGISAM / Riksarkivet om [Hur kommer vi vidare"](https://github.com/salgo60/HISCOKoder/issues/1)
# Hur stor är utmaningen?
Jag brukar [tjata om att jag jobbade på bank med att föra över pengar](https://youtu.be/GeDXzInR_mA?t=1130) och då var det inget snack om att vi skulle ha 0 del i leverans... dit kanske ma inte kan komma med kulturarvsdata men det måste bli mer ordning....

* Bra tankar som gått fel
  * Skapa ett svenskt Rättsinformationssystem med 100 myndigheters författningar starta 1998 man gav upp efter 15 år se mina [anteckningar vad som hände](https://github.com/salgo60/LagrummetLight)
  * Knyta ihop Europas kulturarv med länkade data -  När jag testade det 2019 hade man skickat runt textsträngar och laddat upp 55 miljoner bilder med metadata som inte kan användas se artikel [2019 Carl Larsson who is that - sadly Europeana doesnt know](http://minancestry.blogspot.com/2020/03/carl-larsson-who-is-that-sadly.html)... nu börjar Europeana inse detta i ett ML projekt där just bra metadata behövs....
     * ML ställer krav på bra metadata... när forskarna skulle digitalisera Riksdagstrycket se projekt welfare state och [Riksdagens corpis](https://github.com/welfare-state-analytics/riksdagen-corpus) dom [väljer att skapa](https://drive.google.com/drive/folders/1Vk2q7s8Pi4DgZ1_B2xZB9mjF2SfFSOZs) **samma som Wikidata** eftersom Riksarkivet, Kungliga biblioteket inte har data om Sveriges Riksdagsmän genom tiderna se [Wikidata_riksdagen-corpus/issues/38](https://github.com/salgo60/Wikidata_riksdagen-corpus/issues/38)

<img width="706" alt="image" src="https://user-images.githubusercontent.com/14206509/186889992-64916730-3ad4-45fe-a217-6ff18f36f959.png">

## Vad behövs ##
Jag har [skapat en lista - Magnus list](https://www.wikidata.org/wiki/User:Salgo60/ExternalIdentifiers) med alla fel jag hittar och en bra [föreläsning gjordes på Standford om detta se vid 26:30 min](https://stanford.zoom.us/rec/play/zCW7Zel4sQVeSIgwYL1fAz2E9dytx0_VDdCdKHd2e-CpXQJvS37W-PtohlON9wYLJ3PV_CCH1PR2Kg_s._N9DzHE1blpFqQNL)

<img width="1341" alt="image" src="https://user-images.githubusercontent.com/14206509/186665171-4d577529-f354-43da-8772-e5423c1f9b10.png">

<img width="888" alt="image" src="https://user-images.githubusercontent.com/14206509/186665301-366d3fae-0987-402c-bc06-ea52cbee5f2a.png">

### Vanliga problem - inga helpdesk nummer ###
Inga bra plattformar att rapportera in fel och se status på fel. 2018 gjorde jag en status lista över myndigheter och **det går inte att jobba utan tydlighet** se "[Lesson learned so far and what is needed](https://www.wikidata.org/wiki/Property_talk:P5587#Lesson_learned_so_far_and_what_is_needed)"... skall länkade data fungera så måste man prata med varandra '''[LinkeddataneedsLinkedpeople](https://twitter.com/hashtag/linkeddataneedslinkedpeople?src=hash&f=live)''' jag lyfte detta i [Bonn 2018 på SWIB](https://youtu.be/K0l4fv5uUvg?t=1577)

### Skickar runt textsträngar ###
* exempel European Data portal skickar textsträngar med språk tag se [Notebook](https://github.com/salgo60/open-data-examples/blob/master/European%20data%20portal%20-%20quality%20of%20Metadata.ipynb)  efter en presentation om hur Google jobbar med kunskapsgrafer så frågade jag dom varför dom inte gör rätt [video](https://youtu.be/COBykM5d_cg?t=3263)....
<img width="1013" alt="image" src="https://user-images.githubusercontent.com/14206509/186666160-9a45b7e3-188f-4641-945f-ac50b979fffd.png">
