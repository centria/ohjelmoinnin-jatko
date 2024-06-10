---
title: 'TMC-Ohjeet'
nav_order: 9999
hidden: false
---

# Esivaatimukset

Voidaksesi tehdä tehtävät, sinun tulee asentaa muutama ohjelmisto koneellesi, sekä luoda käyttäjätunnus MOOC.fi -palveluun.

## .NET
Sinulla tarvitsee olla `.NET` (kutsutaan myös nimellä `Dotnet`) asennettuna. Voit asentaa sen täältä: [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download). 

<Note>Käytössä on dotnet 6.0, mutta sen tuki loppuu. Syksyllä käytössä 8.0!</Note>

## Visual Studio Code (VSCode)

Käytämme `Visual Studio Code` -tekstieditoria. Löydät ohjeet esimerkiksi [täältä](https://www.mooc.fi/installation/vscode/#VSCoden-asentaminen) tai suoran asennuslinkin [tästä](https://code.visualstudio.com/download)

## C# ja TMC Plugin

Kun olet asentanut VSCoden, sinun tulee asentaa `Test My Code` eli `TMC` -laajennuksen siihen. Ohjeet löydät [täältä](https://www.mooc.fi/installation/vscode/#TestMyCode-asentaminen)

Tarvitset myös `C#` -laajennuksen: [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)


# Kuinka tehtäviä tehdään

## Rekisteröityminen MOOC.fi -palveluun

Asennettuasi kaiken tarvittavan, sinun tulee ladata tehtävät koneellesi. Sitä varten tarvitset `MOOC.fi tilin`. Voit lukea ohjeet [täältä](https://www.mooc.fi/installation/vscode/#mooc.fi-tunnuksen-luominen). Seuraa ohjeita vaiheeseen `Kirjautuminen ohjelmointiympäristöön` asti.

<Note>
Rekisteröidy korkeakoulun (tai koulun) sähköpostiosoitteella, jos sinulla on sellainen!

Rekisteröidy samalla sähköpostiosoitteella sekä MOOC.fi -palveluun, että avoimeen ammattikorkeakouluun, jos haluat opintopisteitä!
</Note>

### Centrian opiskelijat

Kun sinulla on tili luotuna, valitse VSCodessa oikea organisaatio ja kurssi:
- Organisaation valinta: *Centria University of Applied Sciences*
- Oikea kurssi riippuu toteutuksesta, jolla olet, kuten *Advanced Programming in C# Fall XX* tai *Advanced Programming in C# Spring XX*, missä XX on lukukausi.
    - Oikea nimi löytyy myös Itslearningista.

### Avoin yliopisto ja vapaa oppiminen

Kun sinulla on tili luotuna, valitse VSCodessa oikea organisaatio ja kurssi:
- Organisaation valinta: *Centria University of Applied Sciences*
- Kurssin valinta: *OPEN XX-XX Advanced Programming in C#* missä XX-XX on lukuvuosi.

## Tehtävien tekeminen

Löydät jokaisen osion tehtävät aina luvun lopusta. Kaikissa luvuissa ei ole tehtäviä.

Voit seurata [näitä ohjeita](https://www.mooc.fi/installation/vscode/#ensimm%C3%A4isen-teht%C3%A4v%C3%A4n-tekeminen) (tiettyyn pisteeseen asti) tehtävien tekemiseen.


<Note>
Tässä kohtaa voit törmätä bugiin (virheeseen), ja tehtävät eivät tule näkyviin.

Tässä tapauksessa, valitse uudelleen Extensions-valikosta TMC-laajennus, ja ota se käyttöön (Enable).

Tämän jälkeen VSCode kysyy, luotatko laajennukseen ja tiedostoihin, vastaa molempiin KYLLÄ (YES).
</Note>


## Tehtävien ajaminen

<Note>
Valitettavasti osuus "Lähdekoodin ajaminen" ei toimi vielä C#:lla

Meidän täytyy ajaa tehtävät manuaalisesti, jos haluamme niin tehdä.
</Note>

Visual Studio Codessa,
* Klikkaa **oikealla hiiren napilla** tiedostoa `Program.cs` ja valitse `Open in integrated terminal`.
* Aja ohjelma kirjoittamalla `dotnet run` auenneelle komentoriville ja paina `Enter`.

![Dotnet run](https://github.com/centria/ohjelmoinnin-jatko/raw/master/src/images/dotnet-run.png)


<Note>
Dollarin merkki kuvissa EI ole osa komentoa!
</Note>


## Tehtävien testaaminen

[Seuraa näitä ohjeita](https://www.mooc.fi/installation/vscode/#l%C3%A4hdekoodin-testaaminen)

## Tehtävien lähettäminen palvelimelle

Vain lähettämällä tehtävät palvelimelle, tehtävistä saa pisteitä, ja kurssilla pääsee etenemään. [Seuraa näitä ohjeita](https://www.mooc.fi/installation/vscode/#teht%C3%A4v%C3%A4n-l%C3%A4hett%C3%A4minen-palvelimelle).

## Pistetilanteen tarkistaminen

Voit tarkastaa oman pistetilanteesi kirjautumalla osoitteessa [https://tmc.mooc.fi](tmc.mooc.fi) olevaan verkkopalveluun. Verkkopalveluun kirjaudutaan MOOC.fi-tunnuksilla.

## Virheitä materiaalissa?

Löysitkö virheen tiedoissa? Tai kirjoitusvirheen? Lähetä meille parannusehdotus [GitHubissa](https://github.com/centria/ohjelmoinnin-jatko/tree/master/src/content) ja auta meitä parantamaan materiaalia!