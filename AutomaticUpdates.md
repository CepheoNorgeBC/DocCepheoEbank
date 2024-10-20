# Konfigurasjon av automatisk oppdatering
Som en del av Cepheo E-Bank er det laget noen prosedyrer som automatisk vil utføre bestemte funksjoner i løsningen. Disse kan konfigureres til å kjøre gjennom jobbkøer i Business Central. Neden for finner du en beskrivelse av disse rutinene og hvordan de kan konfigureres.
## Automatiske statusoppdateringer
Codeunit 72182591 "DXTEBANK AritmaStatusUpdate"
Denne prosedyren vil automatiske hente statusoppdateringer for alle bankoverføringer som er sendt til bank. Vi anbefaler at denne konfigureres i en jobbkø som kjører minium en gang pr. time, men ikke oftere enn hvert 2. minutt.
