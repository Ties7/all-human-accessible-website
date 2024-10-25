# Drop & Heal

Dit is een design van de vragenlijst pagina's voor de Drop & Heal website/webapp uitgewerkt tot html, css en javascript.
De onboarding Readme vind je hier: https://github.com/Ties7/the-client-website/blob/main/README.md



## Inhoudsopgave Readme

  * [Beschrijving](#beschrijving)
  * [Kenmerken](#kenmerken)
  * [Licentie](#licentie)

## Beschrijving

Hier staat de website: https://ties7.github.io/all-human-accessible-website/vragenlijst/intro.html
(bekijk de website in inspect mode of telefoon of maak je desktop scherm horizontaal kleiner aangezien hij nog alleen voor mobile grootte is gemaakt)

Dit is hoe het er op mobile uit ziet:
![image](https://github.com/user-attachments/assets/7960978c-35be-4644-9c0c-45aaa4af43b0)





<!-- In de Beschrijving staat hoe je project er uit ziet, hoe het werkt en wat je er mee kan. -->
<!-- Voeg een mooie poster visual toe 📸 -->
<!-- Voeg een link toe naar Github Pages 🌐-->

## Kenmerken

De website is gebouwd met html, css en javascript.

### HTML
De header wat bestaat uit de h1, quit icon en progressiebar bestaat uit de volgende html:
```
    <section>
        <header>
            <h1>Vragenlijst</h1>
            <a class="quit" href=""><img src="/assets/quit.svg" alt="afsluitenbutton"></a>
        </header>
        <img class="progressionbar" src="/assets/progressionbar2.svg" alt="progressionbar">
    </section>
```
De html wordt wellicht nog iets aangepast aangezien hij nog niet responsive is.

Buttons/antwoord geven:
```
    <div class="buttons">
        <a href="vraag2.html"><button id="verpletterend">Verpletterend</button></a>
        <a href="vraag2.html"><button id="drukkend">Drukkend</button></a>
        <a href="vraag2.html"><button id="zwaar">Zwaar</button></a>
        <a href="vraag2.html"><button id="draaglijk">Draaglijk</button></a>
        <a href="vraag2.html"><button id="licht">Licht</button></a>
    </div>
```
Ik gebruik hier een button in een a, aangezien de pagina wel doorgelinkt moet worden maar uiteindelijk wel de gegeven antwoorden opgeslagen moeten worden. Wellicht dat dit beter kan en dat zal ik de aankomende tijd nog uitzoeken en daarna weer verwerken/aanpassen in de Readme.

### CSS
Voor de buttons die om en om infaden heb ik de volgende css gebruikt:
```
.buttons button {
    opacity: 0;
    transform: translateY(15px);
    animation: fadeIn 0.8s ease forwards;
}

@keyframes fadeIn {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```
De ```.buttons button``` roept de button in de groep/class buttons aan. Door de ```opacity: 0;``` zijn de buttons standaard niet zichtbaar. Door de ```transform: translateY(15px);``` staan de buttons 15px lager.
De ```@keyframes fadeIn``` zegt dat het een animatie is wat in dit geval een fadeIn is. De animatie bepaalt wat er gebeurt tijdens het verloop van de animatie van begin tot eind. ```opacity: 1;``` zorgt ervoor dat het element volledig zichtbaar is aan het einde van de animatie. ```transform: translateY(0);``` zorgt ervoor dat het element weer op zijn oorspronkelijke verticale positie staat.

### Javascript
De javascript achter de fadeIn animatie is het volgende:
```
document.addEventListener("DOMContentLoaded", () => {
    const buttons = document.querySelectorAll(".buttons button");
    buttons.forEach((button, index) => {
        button.style.animationDelay = `${index * 0.4}s`;
    });
});
```
```document.addEventListener("DOMContentLoaded", () => {...})``` zorgt ervoor dat dit pas wordt uitgevoerd wanneer de pagina is geladen.
```const buttons = document.querySelectorAll(".buttons button");``` dit selecteerd alle buttons die in de class .buttons zitten.
```buttons.forEach((button, index) => {...});``` maakt onderscheid tussen alle knoppen, knop 1, knop 2 etc. Dit doet de ```index```
```button.style.animationDelay = `${index * 0.4}s`;``` elke knop krijgt andere animationdelay op basis van de ```index``` van de regel hiervoor. De delay is 0.4s en die word vermenigvuldigd door de index. 
Button 1: 1 * 0.4 = 0.4s
Button 2: 2 * 0.4 = 0.8s
Button 3: 3 * 0.4 = 1.2s   etc...

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
