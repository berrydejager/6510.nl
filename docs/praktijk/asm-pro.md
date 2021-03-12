---
layout: default
title: Asm-Pro, laarzen aan en zwemmen!
parent: Praktijk
nav_order: 2
---
# Color Utilities
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
Als je terug in 1990 op een Amiga-copyparty rondwandelde, werd je omringd door monitors waarop steeds dezelfde programmaschermen zichtbaar waren. Op de eerste plaats natuurlijk X-Copy; na een party was iedereen nog wekenlang zoet met stapels versbeschreven diskettes. Verder zag je mensen die logo’s en letters – fonts – tekenden met Deluxe Paint en anderen maakten muziek met een Soundtracker-kloon. Naast al die jonge kunstenaars die tuurden naar omhoogscrollende noten en ingezoomde pixels was nog een andere levensvorm aanwezig: de coder.

The Avengers
The Avengers

Op de monitor van de coder kon je een nauwelijks te volgen stroom bedrijvigheid zien. De coder bewoog met enorme snelheid door een berg (bij voorkeur ongedocumenteerde) broncode en toverde regelmatig met een interval van nog geen tien seconden een oerlelijk scherm met nietszeggende pixelstructuren, flikkerende horizontale balken of Guru Meditations naar voren om direct daarna weer terug te keren en door te typen. Geen pauze. Maar… met een beetje geluk kon je zo af en toe iets moois in wording aanschouwen. De coder had voor dit interessante schouwspel slechts twee gereedschappen nodig: volharding en een assembler.

Jíj hebt dat nu ook; zo’n assembler. This is it. The point of no return. Omhels je geliefden, kijk nog eens goed om je heen, markeer het moment en start Asm-Pro.

    “Kom maar op met die nietszeggende pixelstructuren en flikkerende horizontale balken!”

Asm-Pro scherm

Nee. Asm-Pro bouwt graag de spanning nog even op. Met welk type scherm wil je werken? Wij stellen het scherm in op 640 × 256 pixels. Jij kiest zelf een schermtype. Zorg ervoor dat je de tekst op dat scherm gemakkelijk kunt lezen.

Asm-Pro scherm

Vervolgens vraagt Asm-Pro of je wat geheugen wilt reserveren voor onder andere je broncode. Natuurlijk wil je dat. Het is niet nodig om je volslagen Amiga-geheugen beschikbaar te stellen. Voorlopig is 100 tot 200 kilobyte ruim voldoende. Als jouw toekomstige kunstwerk – jouw broncode – meer ruimte nodig heeft dan merk je dat vanzelf. Weliswaar kun je in dit scherm geheugen tot op de byte nauwkeurig reserveren maar dat is leuk voor later. Gebruik de standaard instellingen.

Je assembler wacht op instructies. Welkom! Dit is het dan: je tweede huis voor de rest van je leven!

Asm-Pro scherm
De ‘command line’ of opdrachtregel

Laten we eerst wat rondkijken. Zoals een blinde in de handen klapt om een onbekende ruimte in zich op te nemen, tik je minimaal tien keer op de Escape-toets. (Doe maar.) En nòg een aantal keer, steeds sneller… Zie je wat er gebeurt? De Escape-toets schakelt tussen twee belangrijke onderdelen van Asm-Pro: de opdrachtregel – te herkennen aan het ‘groter dan’-teken – en de editor, een tekstverwerker.

Asm-Pro scherm
De editor

In de editor schrijf en bewerk je de broncode, je assembly-programma. En met de opdrachtregel – of command line – geef je opdrachten aan de assembler. Opdrachten als ‘assembleer mijn broncode’, ‘toon de inhoud van geheugenplaats $30000’ of ‘geef de uitkomst van de som 826 + %0110’.

Eerst werpen we een blik op de opdrachtregel. Schakel zonodig met de Escape-toets van de editor naar de command line en typ de volgende (vetgedrukte) opdracht achter de prompt (>).

>a
Pass 1..
Pass 2..
No errors
>

Met de opdracht ‘a’ vraag je Asm-Pro om de broncode in de editor te assembleren, dus om te zetten naar machinetaal. Asm-Pro heeft dat zojuist gedaan. Er stond geen broncode in de editor en zodoende is niets in assembly met succes omgezet naar niets in machinetaal.

Er zit een rekenmachine in je assembler. Gebruik het commando ‘?’ om een willekeurige berekening uit te voeren.

>? 50+15
$00000041         65 "...A" %00000000.00000000.00000000.01000001
>

Asm-Pro geeft je de som van 50 en 15 in een aantal verschillende smaken: hexadecimaal ($00000041), decimaal (65), ASCII (de waarde 65 staat klaarblijkelijk voor de letter ‘A’) en binair (%01000001). Handig, niet? Probeer ook eens de volgende opdrachten:

? $1000
? %1001+%0110
? 0-1
? 3*3
? 64/2

Als je niet bekend bent met andere programmeertalen is het fijn te weten dat ‘*’ staat voor vermenigvuldigen en ‘/’ voor delen.

Je kunt je muis grotendeels links laten liggen (of rechts) terwijl je met Asm-Pro werkt. Bekijk het menu maar eens; achter de meeste functies vind je een letter of lettercombinatie. Het is dus niet nodig om alle mogelijke commandline-opdrachten te kennen. Degene die je het meest gebruikt, blijven vlug ‘hangen’.

Asm-Pro scherm

Toer gerust nog even rond in Asm-Pro maar let op bij het betreden van het ‘Disk’-menu: je zou per ongeluk sectoren van een diskette kunnen overschrijven. Wellicht is het ook raadzaam om voorlopig niets te wijzigen in het ‘Preferences’-menu zodat je steeds dezelfde resultaten ziet als hier beschreven. In het volgende artikel verplaatsen we ons naar de editor en zetten we een werkend assembly-programma op.

Lees verder: In gevecht met de broncode