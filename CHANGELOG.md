# 📋 Muutosloki (Changelog)

Tämä tiedosto sisältää TeeVee Player (Android TV / Google TV) -sovelluksen käyttäjälle näkyvät muutokset ja parannukset.

---

## [0.9.2] - 2026-11-07

### 🇫🇮 Suomi
- **Suosikit-oletusvalinta ja listan automaattinen alkuun palautus:**
  - Kaikissa osioissa (Live TV, Elokuvat, Sarjat, Arkisto) avautuu nyt suoraan Suosikit, ja ryhmiä vaihdettaessa kanavalista asettuu aina siististi listan alkuun.
- **Jakson tiedot (Info-painike) sarjanäkymässä:**
  - Sarjan kausi- ja jaksonäkymään on lisätty selkeä Tiedot-painike sekä tuki kaukosäätimen INFO-painikkeelle jakson tietojen tarkasteluun.
- **Sarjojen ja Arkiston katseluhistoria:**
  - Katsotut sarjat ja arkistolähetykset tallentuvat nyt luotettavasti Viimeksi katsotut -listalle.
- **Sarjojen suosikit ja suosikkiryhmät:**
  - Sarjojen Suosikit-valikko ja suosikkilista avautuvat välittömästi ilman latausviiveitä ja näyttävät oikein sekä suosikkiryhmät että suosikkisarjat.
- **Kattavat suorituskykyparannukset ja vakaampi virheenkäsittely:**
  - Sovelluksen käynnistys, valikoiden selaus kaukosäätimellä, soittolistojen ja ryhmien vaihto sekä kuvien lataus toimivat huomattavasti nopeammin ja kevyemmin laitteen muistia kuormittamatta. Tietokanta eheytyy automaattisesti taustalla, ja virheellisistä tunnuksista tai yhteysongelmista näytetään selkeä ilmoitus tallennettuja kanavia hukkaamatta.

### 🇸🇪 Svenska
- **Favoriter som standard och listan återställs till toppen:**
  - Alla sektioner (Live TV, Film, Serier, Arkiv) öppnas nu direkt under Favoriter, och kanallistan återgår alltid snyggt till början vid kategoribyte.
- **Avsnittsinformation (Info-knapp) i serievisningen:**
  - Ny Tiedot (Info)-knapp för serieavsnitt samt stöd för fjärrkontrollens INFO-knapp.
- **Visningshistorik för Serier och Arkiv:**
  - Sedda serieavsnitt och arkivprogram sparas nu tillförlitligt under Viimeksi katsotut (Senast visade).
- **Seriefavoriter och favoritgrupper:**
  - Serieavdelningens favoriter öppnas blixtsnabbt och visar tydligt både favoritgrupper och favoritserier.
- **Omfattande prestandaförbättringar och stabilare felhantering:**
  - Snabbare start, omedelbar fjärrkontrollsnavigering, smidigare bildladdning och automatisk databaskomprimering (VACUUM). Säker felrapportering vid inloggnings- eller nätverksproblem utan dataförlust.

### 🇬🇧 English
- **Favorites as Default & Clean Top Reset:**
  - All main sections (Live TV, Movies, Series, Catchup) now open directly into Favorites, and category switching resets the channel grid cleanly back to the top.
- **Episode Info Button in Series View:**
  - Added dedicated Info buttons to episode rows along with TV remote INFO key support.
- **Watch History for Series & Catchup:**
  - Watched series episodes and catchup broadcasts are now reliably tracked under Recently watched.
- **Series Favorites and Favorite Groups:**
  - Series Favorites menu and favorite list now load instantaneously with clear support for both favorite groups and individual series.
- **Comprehensive Performance & Error Handling Improvements:**
  - Significantly faster app startup, fluid TV remote navigation, lightweight image loading, and automatic database maintenance (VACUUM). Clear error reporting for network/credential issues without loss of stored channels.

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

