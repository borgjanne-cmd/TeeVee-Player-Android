# 📺 TeeVee Player (Android TV & Google TV)

[![GitHub Downloads](https://img.shields.io/github/downloads/borgjanne-cmd/TeeVee-Player-Android/total?style=flat-square&logo=android&logoColor=white&label=Lataukset)](https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases)
[![Latest Release](https://img.shields.io/github/v/release/borgjanne-cmd/TeeVee-Player-Android?include_prereleases&style=flat-square&color=blue&label=Uusin%20versio)](https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases)
[![Platform](https://img.shields.io/badge/Platform-Android%20TV%20%2F%20Google%20TV-green?style=flat-square&logo=google)](https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases)

Huippusuorituskykyinen ja helppokäyttöinen IPTV-mediasoitin **Android TV- ja Google TV -laitteille** (erityisesti **Chromecast with Google TV**). Suunniteltu käsittelemään sujuvasti **kymmeniätuhansia kanavia** ilman muistiongelmia tai käyttöliittymän nykimistä.

---

## 🚀 Keskeiset ominaisuudet

- **10-foot TV -käyttöliittymä (Jetpack Compose for TV):**
  - Optimoitu kaukosäädinkäyttöön (D-pad).
  - **Nopea kanavanvaihto (Zapping):** Vaihda kanavaa suoraan Ylös / Alas -painikkeilla toiston aikana.
  - **Pikakanavalista (Channel Drawer):** Avaa katseltavan kanavan rinnalla sivupalkki (OK-painikkeella) toistoa keskeyttämättä.

- **Kymmenientuhansien kanavien suorituskyky:**
  - **Streaming M3U -jäsennin:** Lukee soittolistan virrasta rivi kerrallaan ja tallentaa tietokantaan erissä ilman, että koko tiedostoa ladataan kerralla keskusmuistiin (RAM).
  - **Paikallinen SQLite / Room DB:** Tehokkaasti indeksoidut kategoriat, kanavat ja suosikit.
  - **AndroidX Paging 3:** Lataa näytölle vain kulloinkin näkyvät kanavat (tasainen 60 fps selailunopeus heikommillakin laitteilla).
  - **Reaaliaikainen haku:** Nopea kanavahaku kymmenientuhansien nimikkeiden joukosta.

- **Soittolistojen tuki:**
  - **M3U / M3U8** -URL-osoitteet ja paikalliset tiedostot.
  - **Xtream Codes API** -kirjautuminen (palvelimen osoite, käyttäjätunnus ja salasana).

- **Tekstitykset & OpenSubtitles:**
  - **Sisäiset striimitekstitykset:** DVB, Teletext, WebVTT, TTML, CEA-608/708.
  - **OpenSubtitles.com REST API v1:** Etsi ja lataa ulkoisia tekstityksiä automaattisesti ohjelman tai elokuvan nimellä.
  - **Tekstityksen viiveen säätö (Sync / Delay):** Hienosäädä ajoitusta suoraan kaukosäätimellä toiston aikana (+/- 0.25 s).

- **Moderni toistomoottori:**
  - **AndroidX Media3 (ExoPlayer):** Täysi HLS-, MPEG-TS- ja DASH-tuki laitteistokiihdytyksellä.

---

## 📥 Asennusohjeet (Sideloading)

Koska sovellus on tällä hetkellä varhaisessa testijakelussa, se asennetaan laitteelle APK-tiedostosta (*sideloading*):

### Tapa 1: Downloader by AFTVnews -sovelluksella (Suositeltu tapa televisiolla)
1. Asenna Google Play Kaupasta televisioosi sovellus **Downloader by AFTVnews**.
2. Avaa television *Asetukset* ➔ *Sovellukset* ➔ *Turvallisuus ja rajoitukset* ➔ *Tuntemattomat lähteet* (tai *Asenna tuntemattomia sovelluksia*) ja anna **Downloaderille** asennusoikeus.
3. Avaa Downloader ja kirjoita osoitekenttään suora latauslinkki:
   ```text
   https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases/latest/download/TeeVee-Player-Android-v0.9.1.apk
   ```
4. Latauksen valmistuttua valitse ruudulta **Install** (Asenna).

### Tapa 2: USB-muistitikulla
1. Lataa uusin `.apk`-tiedosto tietokoneellasi [Releases-sivulta](https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases).
2. Kopioi tiedosto USB-tikulle ja kytke se televisioon.
3. Avaa televisiossa tiedostonhallinta (kuten *AnExplorer* tai *X-plore*) ja klikkaa APK-tiedostoa asentaaksesi sen.

### Tapa 3: ADB-komennolla (Kehittäjille)
```bash
adb connect <television-ip-osoite>:5555
adb install -r TeeVee-Player-Android-v0.9.1.apk
```

---

## 📺 Laitevaatimukset
- **Käyttöjärjestelmä:** Android TV 8.0 (Oreo) tai uudempi (API 26+) / Google TV.
- **Ohjain:** Android TV -kaukosäädin (D-pad-suuntanäppäimet ja OK/Valitse).
- **Testattu:** Chromecast with Google TV (HD & 4K), Xiaomi Mi Box / TV Stick, Sony Bravia & Philips Android TV.

---

## 🔒 Tietoturva ja aitous
Viralliset julkaisutiedostot toimitetaan SHA-256 -tarkistussummilla varustettuina [Releases-sivulla](https://github.com/borgjanne-cmd/TeeVee-Player-Android/releases). Voit aina varmistaa asentamasi tiedoston aitouden.

