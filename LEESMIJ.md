# Een dag in gedichten

Een kleine digitale dichtbundel van Paul van der Kleij.
Een kaft en tien gedichten, met voor iedere bladzijde een eigen achtergrond,
tekstbestand en pianobestand. Alles werkt met gewone HTML, CSS en JavaScript;
er zijn geen externe lettertypen, libraries, trackers of buildstappen.

## 1. De bestanden

De hele vormgeving en techniek staan in `index.html`.
Voor het invullen hoef je alleen de bestanden in de drie mappen te vervangen.

```text
een-dag-in-gedichten/
  index.html
  .nojekyll
  LEESMIJ.md
  afbeeldingen/
    kaft.jpg
    gedicht-01.jpg
    gedicht-02.jpg
    gedicht-03.jpg
    gedicht-04.jpg
    gedicht-05.jpg
    gedicht-06.jpg
    gedicht-07.jpg
    gedicht-08.jpg
    gedicht-09.jpg
    gedicht-10.jpg
  gedichten/
    kaft.txt
    gedicht-01.txt
    gedicht-02.txt
    gedicht-03.txt
    gedicht-04.txt
    gedicht-05.txt
    gedicht-06.txt
    gedicht-07.txt
    gedicht-08.txt
    gedicht-09.txt
    gedicht-10.txt
  muziek/
    kaft.mp3
    gedicht-01.mp3
    gedicht-02.mp3
    gedicht-03.mp3
    gedicht-04.mp3
    gedicht-05.mp3
    gedicht-06.mp3
    gedicht-07.mp3
    gedicht-08.mp3
    gedicht-09.mp3
    gedicht-10.mp3
```

De MP3-placeholders bevatten **zes seconden stilte**, op herhaling. Er is dus
nog geen piano te horen. Ze zijn geldige MP3-bestanden die je kunt vervangen.
De JPG-placeholders zijn effen kleurvlakken. De TXT-bestanden zijn voorbeeldteksten.
De inhoud voor het eerste gedicht staat dus in drie bestanden met dezelfde basisnaam:
`gedicht-01.txt`, `gedicht-01.jpg` en `gedicht-01.mp3`.

## 2. Je gedichten invullen

Open bijvoorbeeld `gedichten/gedicht-01.txt` in een gewone teksteditor.
Gebruik deze indeling:

```text
De titel van je eerste gedicht

Dit is de eerste regel.
Dit is de tweede regel.

Hier begint een nieuwe strofe.
    Ook inspringing blijft bewaard.
```

De eerste regel is de titel. Een lege regel erna mag, maar hoeft niet.
Alles daarna is de tekst van het gedicht. Interne lege regels en inspringing
blijven behouden. Langere regels breken op een smal scherm zo nodig af.
Een lang gedicht kun je binnen de bladzijde omhoog en omlaag scrollen.

Sla op als **platte tekst in UTF-8**. Geen Word- of RTF-bestand hernoemen naar TXT.
Bestandsnamen moeten precies gelijk blijven: kleine letters, streepjes en
nummers met een voorloopnul. Pas op dat je editor niet `.txt.txt` toevoegt.
HTML-code in een gedicht wordt als gewone tekst getoond, niet uitgevoerd.

## 3. De kaft

De drie regels in `gedichten/kaft.txt` zijn achtereenvolgens de titel,
de ondertitel en de auteursnaam. Gebruik hier geen extra lege regels:

```text
Een dag in gedichten
Tien gedichten voor woorden en piano
Paul van der Kleij
```

Je naam staat klein rechtsonder op de kaft. De titel wordt ook in de
inhoudskeuze en de tabtitel gebruikt. De vaste metadescription bovenin de HTML
kun je desgewenst later aanpassen voor de uiteindelijke titel.

De kaft heeft daarnaast `afbeeldingen/kaft.jpg` en `muziek/kaft.mp3`.
Bij het allereerste bezoek is de kaft stil. De klik op 'Open het boek' start
de muziek van gedicht 01, niet de kaftmuziek. De kaftmuziek speelt wanneer je
naar de kaft terugbladert, of op de kaft zelf op de ronde afspeelknop klikt.

## 4. Achtergrondafbeeldingen vervangen

Vervang bijvoorbeeld `afbeeldingen/gedicht-01.jpg` door je eigen echte JPEG,
met exact die bestandsnaam. Een PNG alleen hernoemen naar JPG is niet voldoende:
exporteer daadwerkelijk als JPEG.

Een staande afbeelding van ongeveer 1200 x 1600 pixels is een praktisch
startformaat, geen vereiste. Het beeld vult de hele bladzijde; de randen kunnen
op verschillende schermen iets worden afgesneden. Zet belangrijke details dus
niet helemaal tegen de rand. Houd bestanden bij voorkeur compact.

Over gedichtafbeeldingen ligt een lichte laag zodat de tekst leesbaar blijft.
De kaft heeft een donkere laag. Bovenin de CSS kun je dit aanpassen:

```css
--poem-wash: .87;  /* lager = meer afbeelding, minder lichte laag */
--cover-wash: .12; /* hoger = donkerdere laag */
```

De kaft heeft lichte letters, de gedichten donkere letters. Kies beelden die
hierbij passen. De achtergronden zijn decoratief; zet noodzakelijke informatie
altijd in de TXT-bestanden. Als een JPG ontbreekt, blijft een rustige basiskleur
zichtbaar in plaats van een kapotte pagina.

## 5. Pianomuziek vervangen

Exporteer je opname als MP3 en vervang het bestand voor het juiste gedicht.
Gebruik echte MP3-bestanden, niet WAV-bestanden met een andere extensie.
Een instelling van bijvoorbeeld 160-192 kbit/s is een praktisch startpunt.
Stem de volumes van je opnamen op elkaar af.

Bij het omslaan stopt het vorige stuk en begint het nieuwe stuk bij het begin.
Er speelt altijd maar een bestand tegelijk. Het huidige stuk herhaalt zich
zolang de lezer op dezelfde bladzijde blijft. Voor een vloeiend herhaalpunt
kun je je opname zelf netjes op een muzikaal passende plek monteren.

De ronde knop pauzeert en hervat de muziek. Bewust pauzeren blijft ook tijdens
het bladeren gelden; de lezer moet daarna zelf de muziek weer inschakelen.
Er is geen volumeschuif: de lezer gebruikt het volume van het eigen apparaat.

Browsers en apparaatinstellingen kunnen afspelen zonder aanvullende bevestiging
tegenhouden. De code probeert muziek direct binnen de bladermuisklik te starten,
vraagt niet om verborgen toestemming en toont zo nodig een duidelijke melding
met een afspeelknop. Afspelen kan dus niet in iedere browserinstelling worden
afgedwongen. Een ontbrekende MP3 blokkeert het lezen niet.

## 6. Lezen en bladeren

- Klik of tik op de bladzijde: de volgende pagina.
- Gebruik 'Vorige' of de linkerpijl op het toetsenbord: terug.
- Gebruik 'Volgende' of de rechterpijl: vooruit.
- Met 'Inhoud' spring je naar een bepaalde pagina.
- Na gedicht 10 brengt de volgende klik je terug naar de kaft.
- Met focus op het boek werken ook Enter en de spatiebalk.

Tekst selecteren en in een lang gedicht scrollen slaan niet bewust een pagina
om. Tijdens een omslag worden extra bladermuisklikken genegeerd. Bij een
apparaatvoorkeur voor minder beweging wordt de animatie overgeslagen.

## 7. Lokaal bekijken

Dubbelklikken op `index.html` laat wel de vormgeving en ingebouwde
voorbeeldteksten zien, maar losse TXT-bestanden laden via `fetch()` niet
betrouwbaar vanaf een `file://`-adres. Daarom is er een duidelijke lokale
voorbeeldmodus. Open de site via een webserver om je eigen teksten te zien.

Met Python 3 geinstalleerd: open een terminal **in deze projectmap** en voer uit:

```bash
python -m http.server 8000 --bind 127.0.0.1
```

Op sommige systemen heet het commando `python3` of `py` in plaats van `python`.
Open daarna dit adres in je browser:

```text
http://localhost:8000
```

Stop de testserver met Ctrl+C. Hiervoor is geen Python-code in de website
nodig; Python verzorgt alleen de lokale testserver. Als je Python niet gebruikt,
kun je ook rechtstreeks op GitHub Pages testen.

## 8. Publiceren op GitHub Pages

1. Maak op GitHub een openbare repository, bijvoorbeeld `een-dag-in-gedichten`.
2. Upload de **inhoud** van deze map. `index.html` moet direct in de hoofdmap
   van de repository staan, naast `afbeeldingen`, `gedichten` en `muziek`.
   Upload niet alleen de ZIP. Laat de mappenstructuur intact.
3. Neem ook het lege bestand `.nojekyll` mee. Het is normaal dat het bestand
   geen inhoud heeft. Het kan op je computer verborgen zijn.
4. Ga naar Settings > Pages > Build and deployment.
5. Kies bij Source: Deploy from a branch.
6. Selecteer de branch `main` en de map `/ (root)`, en klik op Save.
7. Gebruik het websiteadres dat GitHub daarna op de Pages-instellingen toont.

Voorbeeld van het uiteindelijke adres:

```text
https://jouwgebruikersnaam.github.io/een-dag-in-gedichten/
```

De site gebruikt relatieve paden, zodat hij ook in een GitHub-projectmap werkt.
Er is geen database, npm-installatie, betaalde speler of API-sleutel nodig.
Vervang later de bestanden in dezelfde mappen en commit/upload de wijzigingen.
Laad na het publiceren zo nodig de website opnieuw zonder browsercache.

Een openbare repository en de gepubliceerde bestanden zijn publiek te lezen
of te downloaden. Er is geen betaalmuur of kopieerbeveiliging ingebouwd.

## 9. Technische documentatie

GitHub Pages - publicatiebron instellen:
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

MDN - beperkingen rond automatisch afspelen:
https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Autoplay

MDN - play() en foutafhandeling:
https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play

MDN - muziek herhalen met loop:
https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loop

MDN - lokale bestanden en fetch():
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS/Errors/CORSRequestNotHttp
