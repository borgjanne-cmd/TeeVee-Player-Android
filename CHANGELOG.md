# 📋 Muutosloki (Changelog)

Tämä tiedosto sisältää TeeVee Player (Android TV / Google TV) -sovelluksen käyttäjälle näkyvät muutokset ja parannukset.

---

## [0.9.1] - 2026-10-31

### 🇫🇮 Suomi

#### Suorituskyky- ja vakausparannukset:
- **Salamannopea soittolistan päivitys:** Korjattu soittolistan tallennuksen jäätyminen "Tallennetaan nimikkeitä..." -vaiheeseen. Käyttäjätilojen (suosikit, historia, katselukohta) siirtologiikka optimoitiin kohdennetuksi: tallennusvaihe lyheni minuuteista alle 2 millisekuntiin.
- **EPG-ohjelmaoppaan asynkroninen lataus:** Ohjelmaoppaan raskas XMLTV-lataus irrotettiin kanavalistan synkronoinnista omaksi taustaprosessikseen. Kanavalistan päivitys valmistuu ja käyttöliittymä vapautuu nyt heti kanavien ja kategorioiden tallennuksen jälkeen.
- **Kanavalistan latausluupin poisto:** Korjattu käynnistyksen toistuva latausluuppi sekä kanavaryhmien (kuten Finland) kymmenien sekuntien latausviive, joka johtui taustalla käynnistyneestä toistuvasta tietokantakirjoituksesta.
- **Sujuva videotoistin ilman uudelleenpiirtoja:** Toistonäytön videopinta (`TvVideoSurface`) on eristetty kaukosäädinvalikoista ja soittimen käyttöliittymäelementeistä. Ohjauspalkin avaaminen tai piilottaminen ei enää aiheuta videopinnan uudelleenpiirtoa eikä kuvan pätkimistä.
- **Nopeammat kanavakyselyt ja DOM-kierrätys:**
  - Lisätty nopeat monisarakkeiset B-Tree -indeksit kanavien lajittelua ja ryhmähakuja varten (Tietokantamigraatio v8).
  - Kanava-, kategoria- ja sarjaverkkoihin lisätty tarkat avaimet (`key`) ja sisältötyypit (`contentType`) sujuvaa selausta varten heikommilla laitteilla (kuten Chromecast with Google TV 4K).

#### Virheenkorjaukset ja turvallisuus:
- **Pois vilkkuva virheilmoitus:** Korjattu virheilmoituksen vilkkuminen ruudulla, kun kanavalistan päivitysnäkymästä poistutaan kaukosäätimen Takaisin-painikkeella.
- **Kaukosäätimen poistovahvistus:** Soittolistan poisto- ja tietokannan nollausdialogeissa oletusfokus ohjataan nyt aina suoraan **"Peruuta"**-painikkeelle vahinkopoistojen estämiseksi.

---

### 🇸🇪 Svenska

#### Prestanda- och stabilitetsförbättringar:
- **Blixtsnabb uppdatering av spellistor:** Åtgärdat frysning vid slutfasen ("Sparar titlar..."). Logiken för att bevara användartillstånd (favoriter, historik, uppspelningsposition) har optimerats. Fasen slutförs nu på under 2 millisekunder istället för flera minuter.
- **Asynkron EPG-nedladdning:** Nedladdning av omfattande XMLTV-programguider körs nu helt i bakgrunden. Uppdateringen av kanallistan blir omedelbart klar så fort kanaler och kategorier sparats.
- **Eliminerad omladdningsloop:** Fixat problemet där kanallistan och grupper fastnade i omladdningsloopar och tog tiotals sekunder att öppna vid start.
- **Jämn videouppspelning utan omritningar:** Videoytan (`TvVideoSurface`) har isolerats från kontroller och menyer, vilket förhindrar mikrolagg när fjärrkontrollens kontroller visas eller döljs.
- **Optimerade databasindex:** Nya sammansatta B-Tree-index (migration v8) och exakta listnycklar garanterar smidig navigering på Chromecast with Google TV 4K.

#### Buggfixar:
- **Inga felmeddelanden vid avbrytning:** Fjärrkontrollens Bakåt-knapp stänger nu dialoger rent utan att utlösa falska felmeddelanden på skärmen.
- **Säker standardknapp vid borttagning:** Dialoger för borttagning fokuserar nu automatiskt på "Avbryt" för att förhindra oavsiktliga raderingar.

