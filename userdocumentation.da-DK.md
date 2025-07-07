# Aritma Finance Manager - Brugervejledning

## Indholdsfortegnelse

1. [Kom godt i gang](#kom-godt-i-gang)
2. [Første opsætning](#første-opsætning)
3. [Administrering af bankkonti](#administrering-af-bankkonti)
4. [Behandling af betalinger](#behandling-af-betalinger)
5. [Transaktionsstyring](#transaktionsstyring)
6. [Bankafstemning](#bankafstemning)
7. [Rapporter og analyser](#rapporter-og-analyser)
8. [Fejlfinding](#fejlfinding)
9. [Ofte stillede spørgsmål](#ofte-stillede-spørgsmål)

---

## Kom godt i gang

### Hvad er Aritma Finance Manager?

Aritma Finance Manager er en omfattende bankløsning til Microsoft Dynamics 365 Business Central, der giver dig mulighed for at:

- Behandle betalinger direkte fra Business Central
- Importere banktransaktioner automatisk
- Afstemme bankkonti effektivt
- Administrere flere valutaer og valutakurser
- Oprette betalingsforslag baseret på udestående fakturaer
- Spore betalingsstatus i realtid

### Nøglefordele

✅ **Strømlinet betalingsbehandling**: Opret og send betalinger direkte fra Business Central
✅ **Automatiseret transaktionsimport**: Importér banktransaktioner automatisk
✅ **Realtids statussporing**: Overvåg betalingsstatus og opdateringer
✅ **SEPA-overholdelse**: Fuld overholdelse af europæiske betalingsstandarder
✅ **Sikker bankvirksomhed**: Branchestandardsikkerhed med OAuth2-godkendelse
✅ **Multi-valuta understøttelse**: Håndter betalinger i forskellige valutaer

---

## Første opsætning

### Forudsætninger

Før du begynder, skal du sikre dig, at du har:
- Microsoft Dynamics 365 Business Central-adgang
- Aritma Banking API-legitimationsoplysninger (klient-ID og hemmelighed)
- Bankkontoinformation (IBAN, kontodetaljer)
- Passende brugertilladelser i Business Central

### Trin 1: Konfigurer E-Bank opsætning

1. **Åbn E-Bank opsætning**:
   - Søg efter "E-Bank opsætning" i Business Central
   - Klik for at åbne opsætningssiden

2. **Konfigurer godkendelse**:
   - Indtast dit **Klient-ID** (leveret af Aritma)
   - Indtast din **Klienthemmelighed** (leveret af Aritma)
   - Indstil **Godkendelses-URL** til det angivne endepunkt
   - Indstil **Base API URL** til: `https://banking.dev.aritma.io/api/`

3. **Konfigurer bankindstillinger**:
   - Vælg din standard **Bankkonto**
   - Indtast dit **IBAN**-nummer
   - Opsæt **Bogføringsgrupper** efter behov
   - Konfigurer **Notifikationsindstillinger**

4. **Test forbindelsen**:
   - Klik på "Test forbindelse" for at verificere din opsætning
   - Sørg for, at du modtager et vellykket godkendelsessvar

### Trin 2: Opsæt bankkonti

1. **Naviger til Bankkonti**:
   - Gå til **Bankkonti** i Business Central
   - Vælg den bankkonto, du ønsker at konfigurere

2. **Konfigurer bankkontodetaljer**:
   - Indtast **IBAN** og **SWIFT-kode**
   - Indstil **Valutakode** hvis forskellig fra LVA
   - Konfigurer **Bogføringsgrupper**
   - Opsæt **Dimensioner** hvis påkrævet

3. **Link til API**:
   - Sørg for, at bankkontoen er korrekt forbundet til Aritma Banking API
   - Test forbindelsen for at verificere dataflow

### Trin 3: Konfigurer brugertilladelser

1. **Indstil brugertilladelser**:
   - Tildel passende tilladelsessæt til brugere
   - Sørg for, at brugere har adgang til bankfunktioner
   - Konfigurer godkendelsesarbejdsgange efter behov

---

## Administrering af bankkonti

### Visning af bankkontoinformation

1. **Få adgang til bankkonti**:
   - Søg efter "Bankkonti" i Business Central
   - Vælg den ønskede bankkonto

2. **Vis kontodetaljer**:
   - Gennemgå kontosaldo og valuta
   - Tjek seneste kontoudtogsdato
   - Se nylige transaktioner

### Tilføjelse af nye bankkonti

1. **Opret ny bankkonto**:
   - Klik på "Ny" i Bankkonti-listen
   - Indtast kontodetaljer (Navn, Nummer, IBAN)
   - Angiv valuta og bogføringsgrupper
   - Konfigurer API-integrationsindstillinger

2. **Konfigurer integration**:
   - Opsæt forbindelse til Aritma Banking API
   - Test integrationen
   - Verificer funktionalitet for transaktionsimport

---

## Behandling af betalinger

### Oprettelse af individuelle betalinger

1. **Få adgang til bankoverførsler**:
   - Søg efter "Bankoverførsel" i Business Central
   - Klik på "Ny" for at oprette en ny overførsel

2. **Indtast betalingsdetaljer**:
   - Vælg **Debitorkonto** (din bankkonto)
   - Vælg **Kontotype** (Kreditor, Debitor, Bankkonto, Medarbejder)
   - Vælg det specifikke **Kontonr.**
   - Indtast **Beløb** og **Valuta**
   - Angiv **Udførelsesdato** (hvornår betalingen skal behandles)

3. **Tilføj betalingslinjer**:
   - Indtast **Kreditors IBAN**
   - Specificer **Kreditors navn**
   - Tilføj **Remitteringsinformation** (betalingsreference)
   - Inkluder eventuel yderligere reference-data

4. **Indsend betaling**:
   - Gennemgå alle detaljer omhyggeligt
   - Klik på "Indsend" for at sende betaling til banken
   - Overvåg statusopdateringer

### Oprettelse af massebetalinger

1. **Generer betalingsforslag**:
   - Gå til "Bankoverførselsforslag" rapport
   - Indstil filtre for forfaldsdato, kreditor eller beløb
   - Generer forslag baseret på udestående fakturaer

2. **Gennemse og modificer**:
   - Gennemgå de genererede betalingslinjer
   - Modificer beløb eller datoer efter behov
   - Fjern eventuelle betalinger, du ikke ønsker at behandle

3. **Behandl massebetaling**:
   - Vælg alle betalingslinjer, der skal behandles
   - Klik på "Behandl betalinger"
   - Overvåg batch-behandlingsstatus

### Understøttede betalingstyper

- **Standard kreditoverførsler**: Almindelige SEPA-betalinger
- **Øjeblikkelige betalinger**: Realtids betalingsbehandling
- **Planlagte betalinger**: Fremtidsdaterede betalinger
- **Massebetalinger**: Flere betalinger i én batch

### Sporing af betalingsstatus

1. **Overvåg betalingsstatus**:
   - Vis betalingsstatus i Bankoverførselslisten
   - Statusopdateringer inkluderer: Foreslået, Indsendt, Behandler, Fuldført, Mislykket

2. **Håndter mislykkede betalinger**:
   - Gennemgå fejlmeddelelser for mislykkede betalinger
   - Korriger eventuelle problemer (forkert IBAN, utilstrækkelige midler osv.)
   - Genindsend korrigerede betalinger

---

## Transaktionsstyring

### Import af banktransaktioner

1. **Automatisk import**:
   - Transaktioner importeres automatisk fra Aritma Banking API
   - Importfrekvens kan konfigureres i E-Bank opsætning
   - Nye transaktioner vises i Banktransaktionslisten

2. **Manuel import**:
   - Gå til "Importer transaktioner"
   - Vælg datointerval for import
   - Vælg specifikke bankkonti
   - Klik på "Importer" for at hente transaktioner

### Visning og administration af transaktioner

1. **Få adgang til banktransaktioner**:
   - Søg efter "Banktransaktioner" i Business Central
   - Vis alle importerede transaktioner

2. **Transaktionsdetaljer**:
   - **Dato**: Transaktionsdato
   - **Beskrivelse**: Transaktionsbeskrivelse fra bank
   - **Beløb**: Transaktionsbeløb og valuta
   - **Type**: Betaling, Modtagelse, Gebyr osv.
   - **Reference**: Bankreferencenumre

3. **Kategoriser transaktioner**:
   - Tildel transaktionstyper for bedre organisering
   - Tilføj interne referencer eller noter
   - Link til relaterede Business Central-poster

### Transaktionsbehandling

1. **Gennemgå nye transaktioner**:
   - Tjek for eventuelle dublettransaktioner
   - Verificer transaktionsbeløb og datoer
   - Sikre korrekt kategorisering

2. **Match transaktioner**:
   - Link transaktioner til eksisterende poster (fakturaer, betalinger)
   - Brug automatiske matchingfunktioner hvor tilgængelige
   - Match komplekse transaktioner manuelt

---

## Bankafstemning

### Automatisk afstemning

1. **Få adgang til bankafstemning**:
   - Gå til standard Business Central Bankafstemning
   - Vælg den bankkonto, der skal afstemmes

2. **Importer kontoudtog**:
   - Importer kontoudtogsdata via Aritma-integration
   - Gennemgå importerede transaktioner
   - Tjek for eventuelle uoverensstemmelser

3. **Auto-matching**:
   - Brug automatiske matchingfunktioner
   - Gennemgå foreslåede matches
   - Bekræft nøjagtige matches

### Manuel afstemning

1. **Match transaktioner manuelt**:
   - For transaktioner, der ikke auto-matches
   - Vælg kontoudtogslinjen
   - Vælg den tilsvarende finanspost
   - Bekræft matchet

2. **Håndter uoverensstemmelser**:
   - Undersøg umatchede transaktioner
   - Opret finansposter for bankgebyrer eller omkostninger
   - Løs eventuelle forskelle

3. **Fuldfør afstemning**:
   - Sørg for, at alle transaktioner er matchet
   - Bogfør afstemningen
   - Gennemgå den endelige bankkontobalance

---

## Rapporter og analyser

### Betalingsrapporter

1. **Bankoverførselsrapporter**:
   - Vis alle betalinger efter datointerval
   - Filtrer efter status, beløb eller konto
   - Eksporter data til analyse

2. **Betalingsstatusrapporter**:
   - Overvåg betalingsbehandlingsstatus
   - Spor mislykkede betalinger og årsager
   - Generer compliance-rapporter

### Transaktionsrapporter

1. **Transaktionshistorik**:
   - Vis transaktionshistorik efter konto
   - Filtrer efter dato, beløb eller type
   - Generer detaljerede transaktionsrapporter

2. **Balancerapporter**:
   - Aktuelle kontosaldi
   - Historisk balancesporing
   - Multi-valuta balancerapportering

### Tilpassede rapporter

1. **Opret tilpassede rapporter**:
   - Brug Business Centrals rapporteringsværktøjer
   - Inkluder Aritma bankdata
   - Planlæg automatisk rapportgenerering

---

## Fejlfinding

### Almindelige problemer og løsninger

#### Godkendelsesproblemer

**Problem**: Kan ikke forbinde til Aritma Banking API
**Løsning**:
1. Verificer at Klient-ID og Klienthemmelighed er korrekte
2. Tjek at API-URL'en er korrekt konfigureret
3. Sørg for, at din IP-adresse er whitelisted (hvis påkrævet)
4. Kontakt Aritma support, hvis legitimationsoplysningerne er udløbet

#### Betalingsfejl

**Problem**: Betaling afvist af bank
**Løsning**:
1. Verificer at IBAN-formatet er korrekt
2. Tjek at kontoen har tilstrækkelige midler
3. Sørg for, at betalingsbeløbet ikke overskrider grænser
4. Gennemgå kreditoroplysninger for nøjagtighed

#### Problemer med transaktionsimport

**Problem**: Transaktioner importeres ikke automatisk
**Løsning**:
1. Tjek API-forbindelsesstatus
2. Verificer datoområder for import
3. Sørg for, at bankkontoen er korrekt konfigureret
4. Gennemgå API-begrænsningsindstillinger

#### Afstemningsproblemer

**Problem**: Transaktioner matches ikke korrekt
**Løsning**:
1. Tjek transaktionsreferencer og beløb
2. Verificer at datoer stemmer overens mellem systemer
3. Se efter dublettransaktioner
4. Brug manuel matching for komplekse tilfælde

### Få hjælp

1. **Tjek dokumentation**: Gennemgå denne brugervejledning og teknisk dokumentation
2. **Kontakt support**: 
   - Aritma Support: https://www.aritma.com
   - Teknisk support: https://www.cepheo.com
3. **API-dokumentation**: https://banking.dev.aritma.io/api/
4. **Business Central Community**: Brug Microsofts Business Central community-forummer

---

## Ofte stillede spørgsmål

### Generelle spørgsmål

**Spørgsmål: Hvilke banker understøttes af Aritma Finance Manager?**
Svar: Aritma Finance Manager understøtter banker, der overholder SEPA-standarder og integrerer med Aritma Banking API. Kontakt Aritma for specifik bankkompatibilitet.

**Spørgsmål: Kan jeg behandle betalinger i flere valutaer?**
Svar: Ja, systemet understøtter multi-valuta betalinger med automatisk valutakurshåndtering.

**Spørgsmål: Er der en grænse for betalingsbeløb?**
Svar: Betalingsgrænser bestemmes af din bank og kontoindstillinger. Tjek med din bank for specifikke grænser.

### Tekniske spørgsmål

**Spørgsmål: Hvor ofte importeres transaktioner?**
Svar: Transaktionsimportfrekvens kan konfigureres i E-Bank opsætning. Standard er typisk hver få timer, men kan indstilles til hyppigere intervaller.

**Spørgsmål: Hvad sker der, hvis en betaling mislykkes?**
Svar: Mislykkede betalinger markeres med en fejlstatus og detaljeret fejlmeddelelse. Du kan gennemgå fejlen, rette problemet og genindsende betalingen.

**Spørgsmål: Kan jeg annullere en betaling efter den er indsendt?**
Svar: Dette afhænger af betalingsstatus og din banks politikker. Kontakt din bank direkte for anmodninger om betalingsannullering.

### Sikkerhedsspørgsmål

**Spørgsmål: Hvor sikker er Aritma Finance Manager?**
Svar: Systemet bruger branchestandard OAuth2-godkendelse, TLS-kryptering og sikker legitimationsopbevaring via Azure Key Vault.

**Spørgsmål: Hvem kan få adgang til bankfunktionerne?**
Svar: Adgang kontrolleres gennem Business Centrals tilladelsessystem. Kun brugere med passende tilladelser kan behandle betalinger og få adgang til bankdata.

**Spørgsmål: Er mine banklegitimationsoplysninger opbevaret sikkert?**
Svar: Ja, alle følsomme legitimationsoplysninger opbevares i Azure Key Vault med sikkerhedsforanstaltninger på virksomhedsniveau.

### Compliance-spørgsmål

**Spørgsmål: Er Aritma Finance Manager SEPA-compliant?**
Svar: Ja, systemet er fuldt compliant med SEPA (Single Euro Payments Area) standarder og regler.

**Spørgsmål: Hvilken revisionsspor er tilgængeligt?**
Svar: Systemet vedligeholder omfattende revisionslogger af alle transaktioner, betalinger og brugeraktiviteter til compliance-formål.

---

## Support og ressourcer

### Dokumentationsressourcer
- **API-dokumentation**: https://banking.dev.aritma.io/api/
- **Teknisk dokumentation**: Tilgængelig i applikationsmappen
- **Business Central Hjælp**: Microsofts officielle Business Central dokumentation

### Supportkontakter
- **Aritma Support**: https://www.aritma.com
- **Teknisk support**: https://www.cepheo.com
- **Nødsupport**: Kontakt din systemadministrator

### Juridisk og compliance
- **Privatlivspolitik**: https://www.aritma.com/privacy
- **Brugsvilkår**: https://www.aritma.com/legal
- **GDPR-compliance**: Fuld overensstemmelse med databeskyttelsesforordninger

---

*Denne brugervejledning er til Aritma Finance Manager version 1.0.0.4. For de mest aktuelle oplysninger, se venligst den officielle dokumentation eller kontakt support.*
