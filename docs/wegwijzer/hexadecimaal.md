---
layout: default
title: Hexadecimaal
parent: Wegwijzer
nav_order: 3
---
In het vorige artikel heb je je kunnen wentelen in het binaire talstelsel. Het is geen probleem als dit nieuwe concept nog wat ongemakkelijk voelt; het decimale stelsel heb je tenslotte ook niet binnen een uur geleerd.

Je zult die bits snel genoeg met andere ogen gaan bekijken; het worden getallen, programma’s, beeld en geluid. Kijk eens! We gooien er nog een talstelsel overheen!

Goed. Een byte bestaat dus uit acht binaire cijfers: acht bits. Het grootste decimale getal dat je in een byte kunt opslaan is 255. Ga zelf maar na: %11111111 = 128+64+32+16+8+4+2+1 = 255.

Om grotere getallen op te slaan zijn natuurlijk meer bits nodig. Een computer doet dat door groepjes te maken van meerdere bytes. Zo kan een groep van twee bytes (2×8 = 16 bits) al maximaal %11111111 11111111 = 65535 bevatten. Het opslaan van grotere getallen zorgt al snel voor een riante reeks bits. Indrukwekkend, maar ook bijzonder slecht leesbaar – laat staan te onthouden – voor mensen.

Hier komt het hexadecimale talstelsel om de hoek kijken. In het hexadecimale stelsel is slechts een enkel cijfer nodig om vier bits (%0000) weer te geven. Zodoende zijn slechts twee hexadecimale cijfers nodig om een byte weer te geven.
Semi-leesbaar

Het hexadecimale talstelsel heeft het grondtal 16. (Bij decimaal en binair is dat respectievelijk 10 en 2.) Het aantal mogelijkheden per cijfer is dus 16. We gaan tegen een probleem aanlopen. Let op wanneer we in de drie talstelsels tegelijk van 0 tot 15 tellen. (Een ‘$’ geeft een hexadecimaal getal aan.)

 0 = %0000 = $0
 1 = %0001 = $1
 2 = %0010 = $2
 3 = %0011 = $3
 4 = %0100 = $4
 5 = %0101 = $5
 6 = %0110 = $6
 7 = %0111 = $7
 8 = %1000 = $8
 9 = %1001 = $9
10 = %1010 = ?
11 = %1011 = ?
12 = %1100 = ?
13 = %1101 = ?
14 = %1110 = ?
15 = %1111 = ?

Er zijn niet genoeg hexadecimale cijfers! Hoe schrijven we de waardes 10, 11, 12, 13, 14 of 15 op een enkele cijferpositie? We lenen gewoon wat letters van het alfabet: de letters A tot en met F. Zo kunnen we verder tellen tot 15:

10 = %1010 = $A
11 = %1011 = $B
12 = %1100 = $C
13 = %1101 = $D
14 = %1110 = $E
15 = %1111 = $F

Er zijn dus 16 hexadecimale cijfers: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E en F.

Het ontleden van hexadecimale getallen gebeurt natuurlijk op dezelfde wijze als beschreven in het vorige artikel. Slechts het grondtal wijzigt naar 16 (0-F), hieronder aangegeven in rode inkt.

Hexadecimaal met grondtal 16

Een getal als $3E8 omrekenen naar decimaal gaat als volgt:

3 × 162 =  3 × 256 = 768
E × 161 = 14 × 16  = 224
8 × 160 =  8 × 1   = 8

$3E8 = 768 + 224 + 8 = 1000
Praktisch nut

Het is duidelijk dat er minder cijfers nodig zijn voor de hexadecimale schrijfwijze dan de binaire schrijfwijze: $3E8 versus %1111101000. Dit loont zich vooral bij grotere getallen. Er is nog een ander voordeel. Je kunt vrij eenvoudig converteren tussen binair en hexadecimaal.

Je kunt per groepje van vier bits converteren naar hexadecimaal en vice versa. We nemen als voorbeeld het getal %11000011.

Binair getal

We verdelen deze byte in twee groepjes van vier bits en rekenen elk groepje apart om van binair naar hexadecimaal. Gebruik daarvoor rustig de tabel hierboven.

Binair getal gegroepeerd in nibbles

%1100 = $C
$0011 = $3

Dus %11000011 = $C3.

Met wat oefening kun je op deze wijze redelijk snel en zonder veel rekenen een binair getal als %1011010111011111 omrekenen naar hexadecimaal.

1011 0101 1101 1111
  B    5    D    F

Of andersom:

$D021 = %1101 0000 0010 0001
           D    0    2    1

$FE = %1111 1110
         F    E

Eenvoudig, niet? Zowel binaire als hexadecimale notatie krijg je vanzelf in de vingers door er mee te werken. Natuurlijk kun je het omrekenen naar verschillende talstelsels overlaten aan… de computer. Hetzij een rekenmachine, een applicatie op je mobiele apparaat of dat grote ding op het bureau. Probeer – zeker wanneer binair en hexadecimaal nieuw voor je zijn – te begrijpen hoe deze talstelsels werken door ‘met de hand’ om te rekenen.
Wie tot $F kan tellen…

En dat was het. Het converteren naar andere talstelsels is de eerste en meest belangrijke heuvel die je neemt nu je leert programmeren in assembly. Werkelijk! De volgende lessen spreken meer tot de verbeelding. Binnenkort kunnen we stap-voor-stap gaan bouwen.

Lees verder: C64 versus Amiga: choose your warrior!