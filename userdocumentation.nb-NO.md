# Cepheo E-bank - Brukerveiledning

## Innholdsfortegnelse

1. [Komme i gang](#komme-i-gang)
2. [Førstegangsoppsett](#førstegangsoppsett)
3. [Administrere bankkontoer](#administrere-bankkontoer)
4. [Behandle betalinger](#behandle-betalinger)
5. [Transaksjonsadministrering](#transaksjonsadministrering)
6. [Bankavstemming](#bankavstemming)
7. [Rapporter og analyser](#rapporter-og-analyser)
8. [Feilsøking](#feilsøking)
9. [Ofte stilte spørsmål](#ofte-stilte-spørsmål)

---

## Komme i gang

### Hva er Cepheo E-bank?

Cepheo E-bank er en omfattende bankløsning for Microsoft Dynamics 365 Business Central som lar deg:

- Behandle betalinger direkte fra Business Central
- Importere banktransaksjoner automatisk
- Avstemme bankkontoer effektivt
- Administrere flere valutaer og valutakurser
- Opprette betalingsforslag basert på utestående fakturaer
- Spore betalingsstatus i sanntid

### Nøkkelfordeler

✅ **Strømlinjeformet betalingsbehandling**: Opprett og send betalinger direkte fra Business Central
✅ **Automatisert transaksjonsimport**: Importer banktransaksjoner automatisk
✅ **Sanntids statussporing**: Overvåk betalingsstatus og oppdateringer
✅ **SEPA-samsvar**: Fullt samsvar med europeiske betalingsstandarder
✅ **Sikker bankvirksomhet**: Bransjestandard sikkerhet med OAuth2-autentisering
✅ **Støtte for flere valutaer**: Håndter betalinger i forskjellige valutaer

---

## Førstegangsoppsett

### Forutsetninger

Før du begynner, sørg for at du har:
- Microsoft Dynamics 365 Business Central-tilgang
- Aritma Banking API-legitimasjon (klient-ID og hemmelighet)
- Bankkontoinformasjon (IBAN, kontodetaljer)
- Passende brukertillatelser i Business Central

### Trinn 1: Konfigurer E-Bank-oppsett

1. **Åpne E-Bank-oppsett**:
   - Søk etter "E-Bank-oppsett" i Business Central
   - Klikk for å åpne oppsettssiden

2. **Konfigurer autentisering**:
   - Angi **Klient-ID** (gitt av Aritma)
   - Angi **Klienthemmelighet** (gitt av Aritma)
   - Sett **Autentiserings-URL** til det oppgitte endepunktet
   - Sett **Base API URL** til: `https://banking.dev.aritma.io/api/`

3. **Konfigurer bankinnstillinger**:
   - Velg standard **Bankkonto**
   - Angi ditt **IBAN**-nummer
   - Sett opp **Bokføringsgrupper** etter behov
   - Konfigurer **Varslingsinnstillinger**

4. **Test tilkoblingen**:
   - Klikk "Test tilkobling" for å verifisere oppsettet
   - Sørg for at du mottar en vellykket autentiseringsrespons

### Trinn 2: Sett opp bankkontoer

1. **Naviger til Bankkontoer**:
   - Gå til **Bankkontoer** i Business Central
   - Velg bankkontoen du vil konfigurere

2. **Konfigurer bankkontodetaljer**:
   - Angi **IBAN** og **SWIFT-kode**
   - Sett **Valutakode** hvis forskjellig fra LVA
   - Konfigurer **Bokføringsgrupper**
   - Sett opp **Dimensjoner** om nødvendig

3. **Koble til API**:
   - Sørg for at bankkontoen er riktig koblet til Aritma Banking API
   - Test tilkoblingen for å verifisere dataflyt

### Trinn 3: Konfigurer brukertillatelser

1. **Angi brukertillatelser**:
   - Tildel passende tillatelsessett til brukere
   - Sørg for at brukere har tilgang til bankfunksjoner
   - Konfigurer godkjenningsarbeidsflyter ved behov

---

## Administrere bankkontoer

### Vise bankkontoinformasjon

1. **Få tilgang til bankkontoer**:
   - Søk etter "Bankkontoer" i Business Central
   - Velg ønsket bankkonto

2. **Vis kontodetaljer**:
   - Gjennomgå kontosaldo og valuta
   - Sjekk siste kontoutskriftsdato
   - Se nylige transaksjoner

### Legge til nye bankkontoer

1. **Opprett ny bankkonto**:
   - Klikk "Ny" i Bankkontoer-listen
   - Angi kontodetaljer (Navn, Nummer, IBAN)
   - Angi valuta og bokføringsgrupper
   - Konfigurer API-integrasjonsinnstillinger

2. **Konfigurer integrasjon**:
   - Sett opp tilkobling til Aritma Banking API
   - Test integrasjonen
   - Verifiser funksjonalitet for transaksjonsimport

---

## Behandle betalinger

### Opprette individuelle betalinger

1. **Få tilgang til banktransaksjoner**:
   - Søk etter "Bankoverføring" i Business Central
   - Klikk "Ny" for å opprette en ny overføring

2. **Angi betalingsdetaljer**:
   - Velg **Debitorkonto** (din bankkonto)
   - Velg **Kontotype** (Leverandør, Kunde, Bankkonto, Ansatt)
   - Velg spesifikt **Kontonr.**
   - Angi **Beløp** og **Valuta**
   - Angi **Utførelsesdato** (når betalingen skal behandles)

3. **Legg til betalingslinjer**:
   - Angi **Kreditors IBAN**
   - Spesifiser **Kreditors navn**
   - Legg til **Remitteringsinformasjon** (betalingsreferanse)
   - Inkluder eventuell tilleggsinformasjon

4. **Send betaling**:
   - Gjennomgå alle detaljer nøye
   - Klikk "Send" for å sende betaling til banken
   - Overvåk statusoppdateringer

### Opprette massebetalinger

1. **Generer betalingsforslag**:
   - Gå til rapporten "Bankoverføringsforslag"
   - Angi filtre for forfallsdato, leverandør eller beløp
   - Generer forslag basert på utestående fakturaer

2. **Gjennomgå og endre**:
   - Gjennomgå de genererte betalingslinjene
   - Endre beløp eller datoer om nødvendig
   - Fjern betalinger du ikke ønsker å behandle

3. **Behandle massebetaling**:
   - Velg alle betalingslinjer som skal behandles
   - Klikk "Behandle betalinger"
   - Overvåk status for batch-behandling

### Støttede betalingstyper

- **Standard kredittoverføringer**: Vanlige SEPA-betalinger
- **Umiddelbare betalinger**: Sanntids betalingsbehandling
- **Planlagte betalinger**: Fremtidsdaterte betalinger
- **Massebetalinger**: Flere betalinger i én batch

### Sporing av betalingsstatus

1. **Overvåk betalingsstatus**:
   - Vis betalingsstatus i Bankoverføringslisten
   - Statusoppdateringer inkluderer: Foreslått, Sendt, Behandler, Fullført, Mislykket

2. **Håndter mislykkede betalinger**:
   - Gjennomgå feilmeldinger for mislykkede betalinger
   - Korriger eventuelle problemer (feil IBAN, utilstrekkelige midler, osv.)
   - Send korrigerte betalinger på nytt

---

## Transaksjonsadministrering

### Importere banktransaksjoner

1. **Automatisk import**:
   - Transaksjoner importeres automatisk fra Aritma Banking API
   - Importfrekvens kan konfigureres i E-Bank-oppsett
   - Nye transaksjoner vises i Banktransaksjonslisten

2. **Manuell import**:
   - Gå til "Importer transaksjoner"
   - Velg datoperiode for import
   - Velg spesifikke bankkontoer
   - Klikk "Importer" for å hente transaksjoner

### Vise og administrere transaksjoner

1. **Få tilgang til banktransaksjoner**:
   - Søk etter "Banktransaksjoner" i Business Central
   - Vis alle importerte transaksjoner

2. **Transaksjonsdetaljer**:
   - **Dato**: Transaksjonsdato
   - **Beskrivelse**: Transaksjonsbeskrivelse fra banken
   - **Beløp**: Transaksjonsbeløp og valuta
   - **Type**: Betaling, Mottak, Gebyr, osv.
   - **Referanse**: Bankreferansenumre

3. **Kategoriser transaksjoner**:
   - Tildel transaksjonstyper for bedre organisering
   - Legg til interne referanser eller notater
   - Koble til relaterte Business Central-poster

### Transaksjonsbehandling

1. **Gjennomgå nye transaksjoner**:
   - Sjekk for dupliserte transaksjoner
   - Verifiser transaksjonsbeløp og datoer
   - Sikre riktig kategorisering

2. **Match transaksjoner**:
   - Koble transaksjoner til eksisterende poster (fakturaer, betalinger)
   - Bruk automatiske matchingfunksjoner der det er tilgjengelig
   - Match komplekse transaksjoner manuelt

---

## Bankavstemming

### Automatisk avstemming

1. **Få tilgang til bankavstemming**:
   - Gå til standard Business Central Bankavstemming
   - Velg bankkontoen som skal avstemmes

2. **Importer kontoutskrift**:
   - Importer kontoutskriftsdata via Aritma-integrasjon
   - Gjennomgå importerte transaksjoner
   - Sjekk for eventuelle avvik

3. **Automatisk matching**:
   - Bruk automatiske matchingfunksjoner
   - Gjennomgå foreslåtte matcher
   - Bekreft nøyaktige matcher

### Manuell avstemming

1. **Match transaksjoner manuelt**:
   - For transaksjoner som ikke matches automatisk
   - Velg kontoutskriftslinjen
   - Velg tilsvarende finanspost
   - Bekreft matchen

2. **Håndter avvik**:
   - Undersøk umatchede transaksjoner
   - Opprett finansposter for bankgebyrer eller avgifter
   - Løs eventuelle forskjeller

3. **Fullfør avstemming**:
   - Sørg for at alle transaksjoner er matchet
   - Bokfør avstemmingen
   - Gjennomgå endelig bankkontobalanse

---

## Rapporter og analyser

### Betalingsrapporter

1. **Bankoverføringsrapporter**:
   - Vis alle betalinger etter datoperiode
   - Filtrer etter status, beløp eller konto
   - Eksporter data for analyse

2. **Betalingsstatusrapporter**:
   - Overvåk betalingsbehandlingsstatus
   - Spor mislykkede betalinger og årsaker
   - Generer samsvarsrapporter

### Transaksjonsrapporter

1. **Transaksjonshistorikk**:
   - Vis transaksjonshistorikk etter konto
   - Filtrer etter dato, beløp eller type
   - Generer detaljerte transaksjonsrapporter

2. **Saldorapporter**:
   - Nåværende kontosaldoer
   - Historisk saldosporing
   - Flervaluta saldorapportering

### Tilpassede rapporter

1. **Opprett tilpassede rapporter**:
   - Bruk Business Centrals rapporteringsverktøy
   - Inkluder Aritma bankdata
   - Planlegg automatisk rapportgenerering

---

## Feilsøking

### Vanlige problemer og løsninger

#### Autentiseringsproblemer

**Problem**: Kan ikke koble til Aritma Banking API
**Løsning**:
1. Verifiser at Klient-ID og Klienthemmelighet er korrekte
2. Sjekk at API-URL er riktig konfigurert
3. Sørg for at IP-adressen din er hvitelistet (hvis nødvendig)
4. Kontakt Aritma support hvis legitimasjonen er utløpt

#### Betalingsfeil

**Problem**: Betaling avvist av banken
**Løsning**:
1. Verifiser at IBAN-formatet er korrekt
2. Sjekk at kontoen har tilstrekkelige midler
3. Sørg for at betalingsbeløpet ikke overskrider grenser
4. Gjennomgå kreditorinformasjon for nøyaktighet

#### Problemer med transaksjonsimport

**Problem**: Transaksjoner importeres ikke automatisk
**Løsning**:
1. Sjekk API-tilkoblingsstatus
2. Verifiser datoperioder for import
3. Sørg for at bankkontoen er riktig konfigurert
4. Gjennomgå API-begrensningsinnstillinger

#### Avstemmingsproblemer

**Problem**: Transaksjoner matches ikke riktig
**Løsning**:
1. Sjekk transaksjonsreferanser og beløp
2. Verifiser at datoer samsvarer mellom systemer
3. Se etter dupliserte transaksjoner
4. Bruk manuell matching for komplekse tilfeller

### Få hjelp

1. **Sjekk dokumentasjon**: Gjennomgå denne brukerveiledningen og teknisk dokumentasjon
2. **Kontakt support**: 
   - Aritma Support: https://www.aritma.com
   - Teknisk støtte: https://www.cepheo.com
3. **API-dokumentasjon**: https://banking.dev.aritma.io/api/
4. **Business Central-fellesskap**: Bruk Microsofts Business Central-forumfellesskap

---

## Ofte stilte spørsmål

### Generelle spørsmål

**Spm: Hvilke banker støttes av Cepheo E-bank?**
Svar: Cepheo E-bank støtter banker som overholder SEPA-standarder og integrerer med Aritma Banking API. Kontakt Aritma for spesifikk bankkompatibilitet.

**Spm: Kan jeg behandle betalinger i flere valutaer?**
Svar: Ja, systemet støtter flervalutabetalinger med automatisk valutakurshåndtering.

**Spm: Er det en grense for betalingsbeløp?**
Svar: Betalingsgrenser bestemmes av banken og kontoinnstillingene dine. Sjekk med banken din for spesifikke grenser.

### Tekniske spørsmål

**Spm: Hvor ofte importeres transaksjoner?**
Svar: Transaksjonsimportfrekvens kan konfigureres i E-Bank-oppsett. Standard er vanligvis hver få timer, men kan settes til hyppigere intervaller.

**Spm: Hva skjer hvis en betaling mislykkes?**
Svar: Mislykkede betalinger merkes med en feilstatus og detaljert feilmelding. Du kan gjennomgå feilen, korrigere problemet og sende betalingen på nytt.

**Spm: Kan jeg kansellere en betaling etter at den er sendt?**
Svar: Dette avhenger av betalingsstatus og bankens retningslinjer. Kontakt banken din direkte for forespørsler om betalingskansellering.

### Sikkerhetsspørsmål

**Spm: Hvor sikker er Cepheo E-bank?**
Svar: Systemet bruker bransjestandard OAuth2-autentisering, TLS-kryptering og sikker legitimasjonslagring via Azure Key Vault.

**Spm: Hvem kan få tilgang til bankfunksjonene?**
Svar: Tilgang kontrolleres gjennom Business Centrals tillatelsessystem. Bare brukere med passende tillatelser kan behandle betalinger og få tilgang til bankdata.

**Spm: Er banklegitimasjonen min lagret sikkert?**
Svar: Ja, all sensitiv legitimasjon lagres i Azure Key Vault med sikkerhetstiltak på bedriftsnivå.

### Samsvarsspørsmål

**Spm: Er Cepheo E-bank SEPA-kompatibel?**
Svar: Ja, systemet er fullt kompatibelt med SEPA (Single Euro Payments Area) standarder og forskrifter.

**Spm: Hvilken revisjonssporing er tilgjengelig?**
Svar: Systemet opprettholder omfattende revisjonslogger for alle transaksjoner, betalinger og brukeraktiviteter for samsvarsformål.

---

## Support og ressurser

### Dokumentasjonsressurser
- **API-dokumentasjon**: https://banking.dev.aritma.io/api/
- **Teknisk dokumentasjon**: Tilgjengelig i applikasjonsmappen
- **Business Central Hjelp**: Microsofts offisielle Business Central-dokumentasjon

### Supportkontakter
- **Aritma Support**: https://www.aritma.com
- **Teknisk støtte**: https://www.cepheo.com
- **Nødsupport**: Kontakt systemadministratoren din

### Juridisk og samsvar
- **Personvernpolicy**: https://www.aritma.com/privacy
- **Bruksvilkår**: https://www.aritma.com/legal
- **GDPR-samsvar**: Fullt samsvar med personvernforordninger

---

*Denne brukerveiledningen er for Cepheo E-bank versjon 1.0.0.4. For mest oppdatert informasjon, vennligst se den offisielle dokumentasjonen eller kontakt support.*
