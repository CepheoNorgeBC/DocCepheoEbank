# Aritma Finance Manager - Användarhandbok

## Innehållsförteckning

1. [Komma igång](#komma-igång)
2. [Första inställningar](#första-inställningar)
3. [Hantera bankkonton](#hantera-bankkonton)
4. [Behandla betalningar](#behandla-betalningar)
5. [Transaktionshantering](#transaktionshantering)
6. [Bankavstämning](#bankavstämning)
7. [Rapporter och analyser](#rapporter-och-analyser)
8. [Felsökning](#felsökning)
9. [Vanliga frågor](#vanliga-frågor)

---

## Komma igång

### Vad är Aritma Finance Manager?

Aritma Finance Manager är en omfattande banklösning för Microsoft Dynamics 365 Business Central som låter dig:

- Behandla betalningar direkt från Business Central
- Importera banktransaktioner automatiskt
- Stämma av bankkonton effektivt
- Hantera flera valutor och växelkurser
- Skapa betalningsförslag baserade på utestående fakturor
- Spåra betalningsstatus i realtid

### Nyckelegenskaper

✅ **Strömlinjeformad betalningshantering**: Skapa och skicka betalningar direkt från Business Central
✅ **Automatiserad transaktionsimport**: Importera banktransaktioner automatiskt
✅ **Statusspårning i realtid**: Övervaka betalningsstatus och uppdateringar
✅ **SEPA-efterlevnad**: Fullständig efterlevnad av europeiska betalningsstandarder
✅ **Säker bankverksamhet**: Branschstandard säkerhet med OAuth2-autentisering
✅ **Stöd för flera valutor**: Hantera betalningar i olika valutor

---

## Första inställningar

### Förutsättningar

Innan du börjar, se till att du har:
- Åtkomst till Microsoft Dynamics 365 Business Central
- Aritma Banking API-inloggningsuppgifter (klient-ID och hemlighet)
- Bankkontoinformation (IBAN, kontodetaljer)
- Lämpliga användarbehörigheter i Business Central

### Steg 1: Konfigurera E-Bank-inställningar

1. **Öppna E-Bank-inställningar**:
   - Sök efter "E-Bank-inställningar" i Business Central
   - Klicka för att öppna inställningssidan

2. **Konfigurera autentisering**:
   - Ange ditt **Klient-ID** (tillhandahållet av Aritma)
   - Ange din **Klienthemlighet** (tillhandahållet av Aritma)
   - Ställ in **Autentiserings-URL** till den angivna slutpunkten
   - Ställ in **Base API URL** till: `https://banking.dev.aritma.io/api/`

3. **Konfigurera bankinställningar**:
   - Välj ditt standardbankkonto
   - Ange ditt **IBAN**-nummer
   - Ställ in **Bokföringsmallar** efter behov
   - Konfigurera **Aviseringsinställningar**

4. **Testa anslutningen**:
   - Klicka på "Testa anslutning" för att verifiera din installation
   - Se till att du får ett framgångsrikt autentiseringssvar

### Steg 2: Ställ in bankkonton

1. **Navigera till Bankkonton**:
   - Gå till **Bankkonton** i Business Central
   - Välj det bankkonto du vill konfigurera

2. **Konfigurera bankkontodetaljer**:
   - Ange **IBAN** och **SWIFT-kod**
   - Ställ in **Valutakod** om det skiljer sig från LVA
   - Konfigurera **Bokföringsmallar**
   - Ställ in **Dimensioner** om det behövs

3. **Länka till API**:
   - Se till att bankkontot är korrekt länkat till Aritma Banking API
   - Testa anslutningen för att verifiera dataflödet

### Steg 3: Konfigurera användarbehörigheter

1. **Ställ in användarbehörigheter**:
   - Tilldela lämpliga behörighetsuppsättningar till användare
   - Se till att användare har åtkomst till bankfunktioner
   - Konfigurera godkännandearbetsflöden vid behov

---

## Hantera bankkonton

### Visa bankkontoinformation

1. **Få åtkomst till bankkonton**:
   - Sök efter "Bankkonton" i Business Central
   - Välj önskat bankkonto

2. **Visa kontodetaljer**:
   - Granska kontosaldo och valuta
   - Kontrollera senaste kontoutdragsdatum
   - Visa de senaste transaktionerna

### Lägga till nya bankkonton

1. **Skapa nytt bankkonto**:
   - Klicka på "Ny" i listan Bankkonton
   - Ange kontodetaljer (Namn, Nummer, IBAN)
   - Ställ in valuta och bokföringsmallar
   - Konfigurera API-integrationsinställningar

2. **Konfigurera integration**:
   - Ställ in anslutning till Aritma Banking API
   - Testa integrationen
   - Verifiera funktionalitet för transaktionsimport

---

## Behandla betalningar

### Skapa individuella betalningar

1. **Få åtkomst till banköverföringar**:
   - Sök efter "Banköverföring" i Business Central
   - Klicka på "Ny" för att skapa en ny överföring

2. **Ange betalningsdetaljer**:
   - Välj **Gäldenärskonto** (ditt bankkonto)
   - Välj **Kontotyp** (Leverantör, Kund, Bankkonto, Anställd)
   - Välj specifikt **Kontonr.**
   - Ange **Belopp** och **Valuta**
   - Ställ in **Utförandedatum** (när betalningen ska behandlas)

3. **Lägg till betalningsrader**:
   - Ange **Fordringsägarens IBAN**
   - Specificera **Fordringsägarens namn**
   - Lägg till **Remitteringsinformation** (betalningsreferens)
   - Inkludera eventuell ytterligare referensdata

4. **Skicka betalning**:
   - Granska alla detaljer noggrant
   - Klicka på "Skicka" för att skicka betalningen till banken
   - Övervaka statusuppdateringar

### Skapa massbetalningar

1. **Generera betalningsförslag**:
   - Gå till rapporten "Bankbetalningsförslag"
   - Ställ in filter för förfallodatum, leverantör eller belopp
   - Generera förslag baserat på utestående fakturor

2. **Granska och modifiera**:
   - Granska de genererade betalningsraderna
   - Modifiera belopp eller datum vid behov
   - Ta bort betalningar du inte vill behandla

3. **Behandla massbetalning**:
   - Välj alla betalningsrader som ska behandlas
   - Klicka på "Behandla betalningar"
   - Övervaka batchbehandlingsstatus

### Stödda betalningstyper

- **Standardkreditöverföringar**: Vanliga SEPA-betalningar
- **Direktbetalningar**: Betalningsbehandling i realtid
- **Schemalagda betalningar**: Framtidsdaterade betalningar
- **Massbetalningar**: Flera betalningar i en batch

### Spårning av betalningsstatus

1. **Övervaka betalningsstatus**:
   - Visa betalningsstatus i listan Bankbetalningar
   - Statusuppdateringar inkluderar: Föreslagen, Skickad, Bearbetar, Slutförd, Misslyckad

2. **Hantera misslyckade betalningar**:
   - Granska felmeddelanden för misslyckade betalningar
   - Korrigera eventuella problem (felaktigt IBAN, otillräckliga medel osv.)
   - Skicka korrigerade betalningar igen

---

## Transaktionshantering

### Importera banktransaktioner

1. **Automatisk import**:
   - Transaktioner importeras automatiskt från Aritma Banking API
   - Importfrekvens kan konfigureras i E-Bank-inställningar
   - Nya transaktioner visas i listan Banktransaktioner

2. **Manuell import**:
   - Gå till "Importera transaktioner"
   - Välj datumintervall för import
   - Välj specifika bankkonton
   - Klicka på "Importera" för att hämta transaktioner

### Visa och hantera transaktioner

1. **Få åtkomst till banktransaktioner**:
   - Sök efter "Banktransaktioner" i Business Central
   - Visa alla importerade transaktioner

2. **Transaktionsdetaljer**:
   - **Datum**: Transaktionsdatum
   - **Beskrivning**: Transaktionsbeskrivning från banken
   - **Belopp**: Transaktionsbelopp och valuta
   - **Typ**: Betalning, Mottagning, Avgift osv.
   - **Referens**: Bankreferensnummer

3. **Kategorisera transaktioner**:
   - Tilldela transaktionstyper för bättre organisering
   - Lägg till interna referenser eller anteckningar
   - Länka till relaterade Business Central-poster

### Transaktionsbehandling

1. **Granska nya transaktioner**:
   - Kontrollera för dubblettransaktioner
   - Verifiera transaktionsbelopp och datum
   - Säkerställ korrekt kategorisering

2. **Matcha transaktioner**:
   - Länka transaktioner till befintliga poster (fakturor, betalningar)
   - Använd automatiska matchningsfunktioner där tillgängliga
   - Matcha komplexa transaktioner manuellt

---

## Bankavstämning

### Automatisk avstämning

1. **Få åtkomst till bankavstämning**:
   - Gå till standard Business Central Bankavstämning
   - Välj det bankkonto som ska stämmas av

2. **Importera kontoutdrag**:
   - Importera kontoutdragsdata via Aritma-integration
   - Granska importerade transaktioner
   - Kontrollera eventuella avvikelser

3. **Automatisk matchning**:
   - Använd automatiska matchningsfunktioner
   - Granska föreslagna matchningar
   - Bekräfta korrekta matchningar

### Manuell avstämning

1. **Matcha transaktioner manuellt**:
   - För transaktioner som inte matchas automatiskt
   - Välj kontoutdragsraden
   - Välj motsvarande redovisningspost
   - Bekräfta matchningen

2. **Hantera avvikelser**:
   - Undersök omatchade transaktioner
   - Skapa redovisningsposter för bankavgifter eller kostnader
   - Lös eventuella skillnader

3. **Slutför avstämning**:
   - Se till att alla transaktioner är matchade
   - Bokför avstämningen
   - Granska det slutliga bankontosaldot

---

## Rapporter och analyser

### Betalningsrapporter

1. **Bankbetalningsrapporter**:
   - Visa alla betalningar efter datumintervall
   - Filtrera efter status, belopp eller konto
   - Exportera data för analys

2. **Betalningsstatusrapporter**:
   - Övervaka betalningsbehandlingsstatus
   - Spåra misslyckade betalningar och orsaker
   - Generera regelefterlevnadsrapporter

### Transaktionsrapporter

1. **Transaktionshistorik**:
   - Visa transaktionshistorik efter konto
   - Filtrera efter datum, belopp eller typ
   - Generera detaljerade transaktionsrapporter

2. **Saldorapporter**:
   - Aktuella kontosaldon
   - Historisk saldospårning
   - Flervslutarapportering

### Anpassade rapporter

1. **Skapa anpassade rapporter**:
   - Använd Business Centrals rapporteringsverktyg
   - Inkludera Aritma bankdata
   - Schemalägg automatisk rapportgenerering

---

## Felsökning

### Vanliga problem och lösningar

#### Autentiseringsproblem

**Problem**: Kan inte ansluta till Aritma Banking API
**Lösning**:
1. Verifiera att Klient-ID och Klienthemlighet är korrekta
2. Kontrollera att API-URL:en är korrekt konfigurerad
3. Se till att din IP-adress är vitlistad (om det krävs)
4. Kontakta Aritma support om inloggningsuppgifterna har gått ut

#### Betalningsfel

**Problem**: Betalning avvisad av banken
**Lösning**:
1. Verifiera att IBAN-formatet är korrekt
2. Kontrollera att kontot har tillräckliga medel
3. Se till att betalningsbeloppet inte överskrider gränser
4. Granska fordringsägarinformation för korrekthet

#### Problem med transaktionsimport

**Problem**: Transaktioner importeras inte automatiskt
**Lösning**:
1. Kontrollera API-anslutningsstatus
2. Verifiera datumintervall för import
3. Se till att bankkontot är korrekt konfigurerat
4. Granska API-begränsningsinställningar

#### Avstämningsproblem

**Problem**: Transaktioner matchas inte korrekt
**Lösning**:
1. Kontrollera transaktionsreferenser och belopp
2. Verifiera att datum överensstämmer mellan system
3. Leta efter dubblettransaktioner
4. Använd manuell matchning för komplexa fall

### Få hjälp

1. **Kontrollera dokumentation**: Granska denna användarhandbok och teknisk dokumentation
2. **Kontakta support**: 
   - Aritma Support: https://www.aritma.com
   - Teknisk support: https://www.cepheo.com
3. **API-dokumentation**: https://banking.dev.aritma.io/api/
4. **Business Central Community**: Använd Microsofts Business Central communityforumer

---

## Vanliga frågor

### Allmänna frågor

**Fråga: Vilka banker stöds av Aritma Finance Manager?**
Svar: Aritma Finance Manager stöder banker som följer SEPA-standarder och integrerar med Aritma Banking API. Kontakta Aritma för specifik bankkompatibilitet.

**Fråga: Kan jag behandla betalningar i flera valutor?**
Svar: Ja, systemet stöder betalningar i flera valutor med automatisk växelkurshantering.

**Fråga: Finns det en gräns för betalningsbelopp?**
Svar: Betalningsgränser bestäms av din bank och kontoinställningar. Kontrollera med din bank för specifika gränser.

### Tekniska frågor

**Fråga: Hur ofta importeras transaktioner?**
Svar: Frekvensen för transaktionsimport kan konfigureras i E-Bank-inställningar. Standard är vanligtvis var tredje timme, men kan ställas in på tätare intervaller.

**Fråga: Vad händer om en betalning misslyckas?**
Svar: Misslyckade betalningar markeras med en felstatus och detaljerat felmeddelande. Du kan granska felet, korrigera problemet och skicka betalningen igen.

**Fråga: Kan jag avbryta en betalning efter att den har skickats?**
Svar: Detta beror på betalningsstatus och din banks policyer. Kontakta din bank direkt för förfrågningar om betalningsavbrott.

### Säkerhetsfrågor

**Fråga: Hur säker är Aritma Finance Manager?**
Svar: Systemet använder branschstandard OAuth2-autentisering, TLS-kryptering och säker inloggningsuppgiftslagring via Azure Key Vault.

**Fråga: Vem kan få åtkomst till bankfunktionerna?**
Svar: Åtkomst kontrolleras genom Business Centrals behörighetssystem. Endast användare med lämpliga behörigheter kan behandla betalningar och få åtkomst till bankdata.

**Fråga: Lagras mina bankinloggningsuppgifter säkert?**
Svar: Ja, alla känsliga inloggningsuppgifter lagras i Azure Key Vault med säkerhetsåtgärder på företagsnivå.

### Frågor om regelefterlevnad

**Fråga: Är Aritma Finance Manager SEPA-kompatibel?**
Svar: Ja, systemet är helt kompatibelt med SEPA (Single Euro Payments Area) standarder och regler.

**Fråga: Vilken revisionslogg finns tillgänglig?**
Svar: Systemet upprätthåller omfattande revisionsloggar av alla transaktioner, betalningar och användaraktiviteter för regelefterlevnadsändamål.

---

## Support och resurser

### Dokumentationsresurser
- **API-dokumentation**: https://banking.dev.aritma.io/api/
- **Teknisk dokumentation**: Tillgänglig i applikationsmappen
- **Business Central Hjälp**: Microsofts officiella Business Central-dokumentation

### Supportkontakter
- **Aritma Support**: https://www.aritma.com
- **Teknisk support**: https://www.cepheo.com
- **Nödsupport**: Kontakta din systemadministratör

### Juridiskt och regelefterlevnad
- **Integritetspolicy**: https://www.aritma.com/privacy
- **Användarvillkor**: https://www.aritma.com/legal
- **GDPR-efterlevnad**: Fullständig efterlevnad av dataskyddsförordningar

---

*Denna användarhandbok är för Aritma Finance Manager version 1.0.0.4. För den mest aktuella informationen, se den officiella dokumentationen eller kontakta support.*
