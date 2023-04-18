> _Fork_ deze deeltaak en ga aan de slag. De instructie vind je in: [docs/INSTRUCTIONS.md](docs/INSTRUCTIONS.md)

# Performance Audit Flevosap

![image](https://user-images.githubusercontent.com/74552944/232764859-8d443f16-df03-4981-939a-4bfd9e8fa853.png)

## Conent audit
Voor de performance audit heb ik de website van Flevosap getest op performance. De site bevat achtergrondinformatie en heel wat plaatjes over het bedrijf van flevosap.

![image](https://user-images.githubusercontent.com/74552944/232764859-8d443f16-df03-4981-939a-4bfd9e8fa853.png)

[Website Flevosap](https://flevosap.nl/)

**GETEST OP : 18-04-2023**

![image](https://user-images.githubusercontent.com/74552944/232778515-31a43ce4-813d-4f17-850a-1a8d6699dfdd.png)


### Netwerk test
* Er zijn 114 request gedaan met een _load_ tijd van 1.54 secondes maar een _finish_ tijd van 25.57 secondes.
* _Load_ is het tijdstempel van de laadgebeurtenis: geactiveerd wanneer een resource en de afhankelijke resources zijn geladen. De reactietijd voor een website betekent in het algemeen de Load tijd, omdat dat waarneembaar is voor de gebruiker en op dit punt kan de gebruiker zien dat de browser is voltooid en de pagina klaar is op het scherm.
* _Finish_ is het tijdstempel van de laatste resource, dus het verandert telkens wanneer een nieuw verzoek wordt gedaan. De Finish tijd in Chrome Devtools bevat de asynchroon laden (niet -blokkerende) objecten/-elementen op de pagina die kunnen blijven downloaden na de ONLOAD -gebeurtenis voor de pagina is geladen.

![image](https://user-images.githubusercontent.com/74552944/232778382-4e2ce818-ccc5-4219-b8c5-ae446e0f74c7.png)


### First Contentful Paint (FCP)
_Eerste weergave met content (FCP) geeft de tijd aan waarbinnen de eerste tekst of afbeelding wordt weergegeven._

![image](https://user-images.githubusercontent.com/74552944/232781948-eacf8aa4-1081-4f08-abc7-53ac5fff0e1a.png)

#### Aanbeveling
* Verwijder bronnen die de weergave blokkeren
* Eerste reactietijd van server verkorten

#### Diagnostische gegevens
* Zorg ervoor dat tekst zichtbaar blijft tijdens het laden van weblettertypen


### Largest Contentful Paint (LCP)
_Grootste weergave met content (LCP) geeft het tijdstip aan waarop de grootste tekst of afbeelding is weergegeven._

![image](https://user-images.githubusercontent.com/74552944/232782703-97e43d1b-437f-42a0-a812-319e479f954b.png)

#### Aanbeveling
* Verwijder bronnen die de weergave blokkeren
* Afbeelding voor Grootste weergave met content (LCP) vooraf laden
* Eerste reactietijd van server verkorten
* Beperk niet-gebruikt JavaScript

#### Diagnostische gegevens
* Zorg ervoor dat tekst zichtbaar blijft tijdens het laden van weblettertypen
* Vermijd enorme netwerkpayloads


### Total Blocking Time (TBT)
_Som van alle perioden tussen Eerste tekenbewerking met content (FCP) en Tijd tot interactief, als de taaklengte langer duurt dan 50 ms, aangegeven in milliseconden._

![image](https://user-images.githubusercontent.com/74552944/232783517-48ae407e-f64e-4a9d-82d0-748aeb76dbe5.png)

#### Diagnostische gegevens
* De impact van code van derden beperken
* Primaire threadbewerkingen minimaliseren
* Verkort de JavaScript-uitvoeringstijd


### Cumulative Layout Shift (CLS)
_Cumulatieve indelingsverschuiving (CLS) meet de beweging van zichtbare elementen binnen de viewport._

![image](https://user-images.githubusercontent.com/74552944/232784154-5f8e8921-9c80-4937-a000-d20c6d095825.png)

#### Diagnostische gegevens
* Grote indelingsverschuivingen vermijden

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
