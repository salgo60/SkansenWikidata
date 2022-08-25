# SkansenWikidata
Beskrivning av lite det som gjorts och utmaningar. Skapa gärna [nya issues](https://github.com/salgo60/SkansenWikidata/issues) med frågor...

## Plug-in
* [EasyQuery](https://www.wikidata.org/wiki/Special:Preferences): Ett verktyg som lägger till en ikon för att lättare hitta objekt samma uttalanden.
   * [video hur man aktiverar den](https://youtu.be/r0fjNkI9M9Q)
## Test av samma som Skansen
* Museala miljöer - TBA
### SKOS -  Simple Knowledge Organization System
Är ett sätt att utrycka semantiska likheter A är ung. som B
* utmaningar som jag ser
  * Stegeborgs slott / ruin -TBA
    * Riksarkivet Tora projektet gjorde ett bra försök men tveksam hur det används se om [Tora](https://riksarkivet.se/tora) -  ["Historical Settlement Units as Linked Open Data"](http://ceur-ws.org/Vol-2364/24_paper.pdf)
## Skapa en egen Wikidata --> Wikibase.cloud dvs. dom hostar en egen wikibase för er
* [om projektet](https://www.wikibase.cloud/)  
  * exempel hur jag skapade data för [kommunernas anslagstavlor](https://sweopendata.wikibase.cloud/wiki/Kommuner) i en egen wikibase som ligger i Wikibase.cloud
    * jag kombinerar då mitt wikibase data med Wikidata genom SPARQL federation [se sökfråga](https://sweopendata.wikibase.cloud/query/index.html#%23%23title%3A%20Kommuners%20Anslagstavla%20-%20test%20Wikibase%0A%23defaultView%3AMap%7B%22hide%22%3A%5B%22%3Fcoord%22%5D%7D%0A%0APREFIX%20wb%3A%20%3Chttps%3A%2F%2Fsweopendata.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20wbt%3A%20%3Chttps%3A%2F%2Fsweopendata.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3FrLabel%20%3Fvideo%20%3Fcoord%20%3Fimg%20%3FwdQ%20%3FsvWikipedia%20WHERE%20%7B%0A%20%20VALUES%20%20%3FAnslagsTavla%20%7Bwb%3AQ240%7D%0A%20%20%20%3Fr%20wbt%3AP2%20%3FAnslagsTavla%20.%0A%20%20%20%3Fr%20wbt%3AP11%20%3Fvideo.%0A%20%20%3Fr%20wbt%3AP1%20%3FwdQ%0A%20%20BIND%28URI%28concat%28%22http%3A%2F%2Fwww.wikidata.org%2Fentity%2F%22%2C%3FwdQ%29%29%20AS%20%3Fwikidata_iri%29%0A%20%20%0A%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata_iri%20wdt%3AP625%20%3Fcoord.%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP41%20%3Fflag%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP94%20%3Fcoat%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP154%20%3Flogo%20%7D%0A%20%20%20OPTIONAL%20%7B%20%3Fwikidata_iri%20wdt%3AP18%20%3Fimage%20%7D%20%20%0A%20%20%20BIND%28%20COALESCE%28%3Fflag%2C%20%3Fcoat%2C%20%3Flogo%2C%20%3Fimage%29%20as%20%3Fimg%20%29%0A%20%20%20OPTIONAL%20%7B%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3Aabout%20%3Fwikidata_iri%20.%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3AinLanguage%20%22sv%22%20.%0A%20%20%20%20%20%20%3FsvWikipedia%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fsv.wikipedia.org%2F%3E%20.%0A%20%20%20%20%7D%0A%20%20%20%20%7D%0A%09SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22sv%2Cen%22.%20%7D%0A%7D)
* vill man prata wikibase.cloud finns en Telegram grupp **"Wikibase.Cloud / WBStack"** som har bra fart
## Historiska yrken
Sammanställing jag gjorde av Historiska yrken se [GITHUB](https://github.com/salgo60/HISCOKoder) plus skickade ut en fråga rill DIGISAM / Riksarkivet om [Hur kommer vi vidare"](https://github.com/salgo60/HISCOKoder/issues/1)
