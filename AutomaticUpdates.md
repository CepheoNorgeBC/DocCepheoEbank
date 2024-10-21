# Konfigurasjon av automatisk oppdatering
Som en del av Cepheo E-Bank er det laget noen prosedyrer som automatisk vil utføre bestemte funksjoner i løsningen. Disse kan konfigureres til å kjøre gjennom jobbkøer i Business Central. Neden for finner du en beskrivelse av disse rutinene og hvordan de kan konfigureres.
## Automatiske statusoppdateringer - bankoverføinger
Codeunit 72182591 "DXTEBANK AritmaStatusUpdate"
Denne prosedyren vil automatiske hente statusoppdateringer for alle bankoverføringer som er sendt til bank. Vi anbefaler at denne konfigureres i en jobbkø som kjører minium en gang pr. time, men ikke oftere enn hvert 2. minutt.
## Automatisk henting av belastede bankoverføringer
Codeunit 72182594 "DXTEBANK GetBookedPayments"
Denne prosedyren vil automatisk hente nye belastede bankoverføringer fra banken. Vi anbefaler at denne konfigureres i en jobbkø som kjører minimum en gang pr. døgn, men ikke oftere enn en gang pr. time.
## Automatisk bokføring av belastede bankoverføringer.
Codeunit 72182595 "DXTEBANK Post Booked Banktrans"
Denne prosedyren vil automatisk bokføre bankoverførignger som er belastet i banken, men som ennå ikke er bokført i Business Central. Vi anbefaler at denne konfigureres i en jobbkø som kjøres minimum en gang pr. time, men ikke oftere en 2.hvert minutt.
