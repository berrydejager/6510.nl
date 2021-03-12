---
layout: default
title: Binair, bits en bytes
parent: Wegwijzer
nav_order: 2
---
Geluid is (altijd) analoog en computers verwerken informatie digitaal. Wat analoog betekent, leggen audiofielen en degenen die ooit een langspeelplaat hebben vastgehouden je met liefde uit. Wij nemen digitaal voor onze rekening.

Als je in de Van Dale de woorden digitaal en analoog opzoekt, vind je een tegenstelling:

    digitaal: werkend op basis van het binaire stelsel;
    analoog: niet werkend op basis van het binaire stelsel.

Grappig. Blader je vervolgens terug naar het woord binair dan lees je dat een binair cijfer zich in het binaire stelsel bevindt. Nóg grappiger. Maar ja, binair? Dat gaan we onderzoeken want computers en het binaire talstelsel zijn onlosmakelijk met elkaar verbonden. Computers werken enkel met nullen en enen.

Setje nullen en enen
Bron: Michael O’Donnell
Wie tot tien kan tellen…

Om het binaire talstelsel inzichtelijk te maken, kunnen we het best eerst kijken naar het talstelsel dat wordt gebruikt door de meeste mensen: het decimale stelsel.

Deci betekent tien en ons decimale — tientallige — stelsel is dus gebaseerd op tien cijfers: 0 tot en met 9. De plaats van het cijfer in een getal geeft de decimale grootheid ervan aan. Anders gezegd: het cijfer uiterst rechts geeft het aantal eenheden aan, het cijfer links daarvan het aantal tientallen, het cijfer links daarvan het aantal honderdtallen enzovoort. Dat illustreren we met een voorbeeld.

Het willekeurige decimale getal 1.409 kunnen we als volgt ontleden:

    1 duizendtal;
    4 honderdtallen;
    0 tientallen;
    9 eenheden.

Dat kunnen we ook schrijven als:

1 × 1000
4 × 100
0 × 10
9 × 1

Wanneer we hetzelfde noteren met machtsverheffingen¹, schrijven we:

1 × 103
4 × 102
0 × 101
9 × 100

Bekijk het volgende figuur. Boven de (genummerde) hokjes staan de waarden van de cijferposities.

Decimaal getal ontleed

We zijn zó bekend met het decimale talstelsel dat we in een oogopslag zien uit welke onderdelen een getal als 1.409 bestaat. We hoeven een decimaal getal niet eerst te ontleden.
Binair is twee

Computers rekenen echter niet met tien cijfers. Een computer werkt op elektriciteit en gebruikt schakelaars – enorm veel – die elk uit of aan kunnen staan; ze staan elk op 0 of 1. Het talstelsel waar computers mee werken is dan ook gebaseerd op die twee cijfers, 0 en 1: het binaire talstelsel. Binair betekent tweevoudig. Twee is een stuk minder dan tien! Toch kunnen we met slechts twee cijfers getallen maken. Dat gaat als volgt.

Als voorbeeld nemen we het binaire getal %11101. Het procentteken geeft aan dat het om een binair getal gaat.

Binaire getallen ontleden we op dezelfde wijze als decimale getallen. We wijzigen slechts het grondtal – het aantal mogelijke waarden per cijferplaats – van 10 (decimaal, 0-9) naar 2 (binair, 0-1). Het nieuwe grondtal 2 geven we voor de duidelijkheid aan met rode inkt.

We hebben het (binaire) getal %11101 ingevuld.

Binair getal ontleed

En ontleden het op dezelfde wijze als een decimaal getal.

1 × 24
1 × 23
1 × 22
0 × 21
1 × 20

Laten we de machtsverheffingen alvast uitrekenen; dat leest eenvoudiger.

Binair getal ontleed

En zo krijgen we:

1 × 16
1 × 8
1 × 4
0 × 2
1 × 1

16 + 8 + 4 + 0 + 1 = 29

Het getal %11101 luidt in decimale notatie 29, dus %11101 = 29
Decimaal naar binair

Laten we nu een decimaal getal omrekenen naar binair, bijvoorbeeld 25. Gebruik het onderstaande figuur.

Lege byte

We nemen de macht van twee die het dichtst onder 25 ligt. Dat is 16 (24). We houden dan nog 9 over (want 25-16=9). In 9 past 8 (23) met 1 over. 4 (22) past niet in 1. 2 (21) past niet in 1. 1 (20) wel!

Op een rij:

1 × 16
1 × 8
0 × 4
0 × 2
1 × 1

16 + 8 + 0 + 0 + 1 = 25

Dus 25 = %11001.

Byte met de waarde 25
Bits en bytes

In het binaire talstelsel kan elke cijferpositie – elk ‘hokje’ – dus een 0 of een 1 bevatten; uit of aan. Zo een hokje noemen we een bit: een samentrekking van ‘binary digit’. In de figuren zijn steeds acht van deze bits getekend. Dat is niet toevallig: een groep van acht bits noemen we een byte, afgeleid van ‘by eight’ (per acht).

Deze termen kun je als volgt gebruiken:

Lege byte

In het getal %11001 – zoals je hierboven ziet – staan bits 4, 3 en 0 aan en bits 7, 6, 5, 2 en 1 uit. In deze byte is de waarde 25 opgeslagen.

Zo kan een computer bijvoorbeeld de vorm van de letter ‘A’ opslaan; een afbeelding!

Karaktermatrix naar binair
Bron: Robin Alan Sherer
Oefeningen

Probeer zelf de volgende vragen te beantwoorden.

    Hoeveel is %11110000
    Hoeveel is %00001111
    Wat is het hoogste getal dat je in een byte kunt opslaan?
    Wat is het laagste getal dat je in een byte kunt opslaan?
    Hoeveel is 64 in binair?
    Wat is jouw leeftijd in binair?

Dit is waarschijnlijk het hoofdstuk dat het minst tot de verbeelding spreekt. Als je het nog niet helemaal snapt is dat geen probleem; het is niet noodzakelijk om uit het hoofd te kunnen rekenen van decimaal naar binair. We gaan het binaire stelsel vanaf nu wèl gewoon gebruiken; door die nullen en enen in de praktijk te zien, krijgen ze vanzelf ‘waarde’. Let maar eens op…

Lees verder: Hexadecimaal