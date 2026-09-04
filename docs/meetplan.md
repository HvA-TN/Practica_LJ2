# Meetplan

## Hoe stel ik een meetplan op?

Voordat je aan een experiment begint, moet duidelijk zijn **wat je wilt onderzoeken, wat je verwacht en hoe je dat gaat meten**. Dat beschrijf je in een meetplan.

Als voorbeeld gebruiken we op deze pagina een klassiek experiment:

> **Bepaling van de valversnelling met een slinger**

![De slinger van Foucault.](assets/periode%201/Pendulum.jpg)

*Figuur: De slinger van Foucault.*

---

## Inleiding

Een experiment begint met de vraag wat je precies wilt weten. Dit leg je vast in de **onderzoeksvraag**. Een goede onderzoeksvraag is concreet en onderzoekbaar en geeft richting aan het experiment.

Voorbeelden zijn:

- *Wat is de valversnelling zoals bepaald met een slinger?*
- *Hoe verandert de elektrische weerstand van een halfgeleider als functie van de temperatuur?*

Een onderzoeksvraag hoeft niet altijd letterlijk als vraag in een verslag te staan. Je kunt het doel van het experiment ook in de lopende tekst verwerken. Een andere mogelijkheid is om een expliciet **onderzoeksdoel** te formuleren.

Je kunt bijvoorbeeld schrijven:

> In dit experiment bepalen we de valversnelling met behulp van een slinger.

of expliciet als onderzoeksvraag:

> Wat is de waarde van de valversnelling zoals bepaald met een slinger?

Beide vormen zijn prima. Ook tijdens een stage of afstudeeropdracht hangt de meest geschikte vorm af van het soort verslag en de afspraken binnen het bedrijf of de onderzoeksgroep.

### Verwachting

Na de onderzoeksvraag beschrijf je wat je op basis van de theorie verwacht. Dit noemen we de **verwachting**.

Een verwachting is meer dan een gok. Je gebruikt natuurkundige theorie of eerdere resultaten om vooraf te voorspellen wat je tijdens het experiment denkt te gaan zien. Dat kan een verwachte waarde zijn, maar bijvoorbeeld ook een lineair, kwadratisch of exponentieel verband.

Het belangrijkste is dat duidelijk wordt **waarom** je een bepaald resultaat verwacht.

### Meetstrategie

Vervolgens beschrijf je hoe je de onderzoeksvraag experimenteel gaat beantwoorden. Dit is de **meetstrategie**.

Hierin hoeft nog niet iedere handeling tot in detail te worden beschreven. Het moet wel duidelijk zijn welke grootheden je gaat meten, wat je varieert, welke omstandigheden je constant houdt en hoe je de meetgegevens uiteindelijk gaat analyseren.

Denk daarbij bijvoorbeeld aan:

- welke grootheden je meet;
- welke grootheid je varieert;
- welke grootheden je constant probeert te houden;
- hoeveel metingen nodig zijn;
- welke meetonzekerheden belangrijk zijn;
- welke grafiek of fit je gaat gebruiken;
- hoe je uit de analyse uiteindelijk de gezochte grootheid bepaalt.

!!! methode "Het meetplan"

    Een meetplan bevat in ieder geval:

    1. **Onderzoeksvraag** — wat wil je onderzoeken?
    2. **Verwachting** — wat verwacht je op basis van de theorie?
    3. **Meetstrategie** — welke metingen en analyse zijn nodig om de onderzoeksvraag te beantwoorden?

---

# Voorbeeld: de slingerproef

We bekijken als voorbeeld een experiment waarin de valversnelling \(g\) wordt bepaald met een eenvoudige slinger met lengte \(L\).

Hetzelfde meetplan kan op verschillende manieren worden opgeschreven. Hieronder zie je eerst een versie waarin de onderzoeksvraag in de tekst is verwerkt en daarna een versie waarin de onderdelen expliciet worden benoemd.

## 1. Onderzoeksvraag verwerkt in de tekst

In dit experiment bepalen we de valversnelling \(g\) met behulp van een slinger. Hiervoor meten we de periode \(T\) van de slinger bij verschillende slingerlengtes \(L\).

Voor een eenvoudige slinger en voldoende kleine uitwijkhoeken geldt bij benadering:

\[
T = 2\pi \sqrt{\frac{L}{g}}.
\]

De periode neemt dus toe met de wortel van de slingerlengte. Handiger voor de analyse is om deze vergelijking te kwadrateren:

\[
T^2 = \frac{4\pi^2}{g}L.
\]

Volgens het model moet een grafiek van \(T^2\) tegen \(L\) daarom een rechte lijn opleveren. Uit de helling van deze lijn kan vervolgens de valversnelling \(g\) worden bepaald. We verwachten een waarde in de buurt van \(9{,}81\,\mathrm{m/s^2}\).

De relatie voor de periode volgt uit de bewegingsvergelijking van de slinger. Voor kleine hoeken mag daarbij de benadering

\[
\sin(\theta) \approx \theta
\]

worden gebruikt.

Om \(g\) experimenteel te bepalen, meten we de periode voor meerdere bekende slingerlengtes. Voor iedere lengte voeren we meerdere metingen uit, zodat we de spreiding kunnen bepalen en de onzekerheid in de bepaalde periode kunnen verkleinen. Voor iedere lengte bepalen we \(T\) en vervolgens \(T^2\).

Daarna zetten we \(T^2\) uit tegen \(L\) en bepalen we de helling van het lineaire verband. Uit

\[
\text{helling} = \frac{4\pi^2}{g}
\]

volgt uiteindelijk de experimentele waarde van \(g\). Bij de analyse houden we rekening met de meetonzekerheden in zowel de slingerlengte als de periode.

---

## 2. Expliciete onderzoeksvraag

### Onderzoeksvraag

**Wat is de waarde van de valversnelling \(g\) zoals bepaald met een eenvoudige slinger?**

### Verwachting

Voor een eenvoudige slinger met een kleine uitwijkhoek geldt:

\[
T = 2\pi \sqrt{\frac{L}{g}}.
\]

Na kwadrateren volgt:

\[
T^2 = \frac{4\pi^2}{g}L.
\]

We verwachten daarom een lineair verband tussen \(T^2\) en \(L\). Uit de helling van dit verband moet een waarde voor \(g\) volgen die in de buurt ligt van

\[
g \approx 9{,}81\,\mathrm{m/s^2}.
\]

De gebruikte relatie geldt alleen binnen de kleine-hoekenbenadering,

\[
\sin(\theta) \approx \theta,
\]

dus tijdens het experiment moet de uitwijkhoek voldoende klein worden gehouden.

### Meetstrategie

We meten de periode \(T\) van de slinger voor meerdere bekende slingerlengtes \(L\). Voor iedere lengte wordt de periode meerdere keren bepaald. Daarmee kunnen we de spreiding in de metingen bepalen en een onzekerheid aan de bepaalde periode toekennen.

Voor iedere slingerlengte bepalen we vervolgens \(T^2\). Deze waarden worden uitgezet tegen \(L\). Volgens de theorie moet dit een lineair verband geven:

\[
T^2 = \frac{4\pi^2}{g}L.
\]

Met een lineaire fit bepalen we de helling \(a\). De valversnelling volgt dan uit

\[
g = \frac{4\pi^2}{a}.
\]

De onzekerheid in de helling wordt gebruikt om ook een onzekerheid in de bepaalde waarde van \(g\) te berekenen. Tot slot vergelijken we de experimenteel bepaalde waarde met de verwachte waarde.

---

!!! voorbereiding "Checklist voor je eigen meetplan"

    Controleer voordat je begint met meten of uit je meetplan duidelijk wordt:

    1. **Wat wil ik bepalen of onderzoeken?**
    2. **Wat verwacht ik op basis van de theorie?**
    3. **Welke theoretische relatie gebruik ik?**
    4. **Welke grootheden moet ik meten en welke moet ik variëren?**
    5. **Welke grafiek, fit of andere analyse heb ik nodig?**
    6. **Hoe volgt het antwoord op mijn onderzoeksvraag uit die analyse?**
    7. **Welke meetonzekerheden spelen daarbij een belangrijke rol?**