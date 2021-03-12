---
layout: default
title: In gevecht met de broncode
parent: Praktijk
nav_order: 3
---
# Color Utilities
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
De editor in Asm-Pro is de plaats waar het assembly-programma wordt geschreven. Het is feitelijk gewoon een tekstverwerker: tekst intypen, tekst wijzigen, tekst verwijderen, tekst kopieren en tekst plakken. Bij een tekstverwerker gaat het om de inhoud, niet om de vorm. Maar assembly schrijf je wèl op een bepaalde manier. Net zoals je op een bepaalde manier een zakelijke brief schrijft. Je assembler ziet graag correct gespelde instructies op een verwachte plaats.

Als aankomend assembly-programmeur zul je voorlopig programma’s invoeren die je niet helemaal – of zelfs helemaal niet – snapt. Dat is niet gek want je bent aan het leren. Echter, de assembler moet de broncode wel goed kunnen begrijpen om er machinetaal van te maken. Stel, in je enthousiasme voer je de instructie NOP, die je eerder zag, per ongeluk in als NOOP. Wanneer de assembler tijdens het assembleren jouw NOOP tegenkomt – een onbekende instructie – dan stopt hij direct met assembleren en begroet je met een foutmelding.

    “Dus ik mag geen fouten maken?”

Ezel, steen, drie keer

Maak zoveel mogelijk fouten! Het maken van fouten en het oplossen ervan is een belangrijk onderdeel van het leerproces. Hoe meer fouten je maakt hoe sneller je assembly leert. Echt! Maak ze desnoods opzettelijk. In het begin van je coder-carrière geldt: voer je broncode zoveel mogelijk met de hand in – niet kopiëren dus – en probeer de fouten die je daarbij ongetwijfeld maakt zelf op te lossen.

Voer het volgende programma eens in. (Handmatig, dus niet kopiëren.) Er zitten fouten in – misschien zie je ze al – maar die neem je letterlijk over.
      nop
      noop
lbl1  btst  #6,$bfe001
      beq   lbl2
      rts

Voordat je het programma assembleert, is het verstandig om de broncode op te slaan. Dat kan op een aantal manieren. Via het menu (Project > Write > Source), de opdrachtregel (w) of een sneltoets (Amiga+w). (Vanaf nu geven we opdrachten zoveel mogelijk via de opdrachtregel of commandline, maar voel je vrij om het menu te gebruiken.)

Nú begint het gevecht. Het is de bedoeling dat jij wint van de computer. Assembleer het programma met het commando ‘a’.

>a

Slaine #1
©Simon Bisley
Veldslag 1 – syntax

Dat gaat niet goed en dat verwachtte je waarschijnlijk al. Wanneer je het stukje broncode precies hebt overgenomen, geeft Asm-Pro de volgende foutmelding.
** Illegal Operator
    2  noop

Je weet natuurlijk dat de instructie NOOP niet bestaat. Kijk eens naar de foutmelding: daar staan een paar aanwijzingen. Met ‘Illegal Operator’ omschrijft je assembler het probleem: je hebt een niet-bestaande instructie gebruikt. De foutmelding vermeldt ook het regelnummer waar de fout optrad (2) en de inhoud van die regel. Los het op door NOOP te corrigeren naar NOP.

Schrijf je broncode voor de zekerheid nog eens weg – dit kan gemakkelijk met ‘u’ (update file) – en assembleer opnieuw met het commando ‘a’.

>u
Updating .. SRC:Gevecht.s
File length = 131 (=$00000083)
>a

Nog steeds niet goed. De eerste fout is opgelost maar nu kan Asm-Pro klaarblijkelijk een label niet vinden tijdens het assembleren van regel 4.
** Undefined Symbol
    4  beq lbl2

Terug naar de broncode:
      nop
      nop
lbl1  btst  #6,$bfe001
      beq   lbl2
      rts

Zie je het? Op de vierde regel verwijs je naar een label met de naam ‘lbl2’. Maar label ‘lbl2’ bestaat niet. Dat moet natuurlijk ‘lbl1’ zijn. Wijzig op regel 4 ‘lbl2’ in ‘lbl1’.

Sla de gewijzigde broncode op en assembleer de broncode opnieuw.

En? Als Asm-Pro tijdens het assembleren geen foutmeldingen meer geeft, heb je de eerste slag gewonnen. Je hebt een programma geschreven zonder grammaticale – ofwel syntactische – fouten en zodoende heeft de assembler jouw assembly kunnen omzetten naar machinetaal.

Toch foutmeldingen? Mooi! Probeer die er zelf uit te halen. Concentreer je op het regelnummer dat Asm-Pro aangeeft in de foutmelding. Eén fout tegelijk en geef niet op! Je broncode zou er zo uit moeten zien:
      nop
      nop
lbl1  btst  #6,$bfe001
      beq   lbl1
      rts

Zoals je ziet, is de broncode ingedeeld in kolommen. Dit voorkomt verwarring voor zowel mens als machine. Labels (zoals ‘lbl1’) starten aan het begin van de regel; in de eerste kolom. Mnemonics – instructies – in de tweede. Voor een mnemonic staat dus altijd minimaal een tab of een spatie. Zo kan de assembler een instructie nooit verwarren met een label en het maakt je programma beter leesbaar.

In een vorig artikel hebben we al beschreven wat dit programma zou moeten doen: wachten tot de linker muisknop wordt ingedrukt en dan terugkeren.

Het machinetaalprogramma staat klaar in het geheugen, ergens. Met het commando ‘j’ laat je de machinecode door de processor uitvoeren. De ‘j’ staat voor ‘jump’. Ben je er klaar voor?

>j

En? Werkte het?

Vast niet. Je programma werd weliswaar uitgevoerd maar wachtte niet op de muisknop en keerde direct terug. Wanneer de processor klaar is met het uitvoeren van een programma en ‘terugspringt’ – in dit geval naar Asm-Pro – plaatst Asm-Pro een indrukwekkende lijst gegevens op het scherm en is daarna weer gereed voor nieuwe opdrachten.

Asm-Pro scherm
Stoer ogend overzicht van de processorstatus

    “Waarom werkt het niet?”

Die vraag zul je jezelf nog vaak stellen! Maak je klaar voor de volgende ronde; het gevecht is nog niet gewonnen!

Slaine #2
©Simon Bisley
Veldslag 2 – semantiek

De syntactische fout heeft een broer (of zus): de semantische fout. Die ligt wat minder aan de oppervlakte en heeft te maken met de uitvoering van je programma en de betekenis van de instructies. De assembler helpt je niet. Dit type fouten los je op met kennis en ervaring. Kennis en ervaring die je krijgt door… het oplossen van semantische fouten! De processor voert jouw instructies correct uit maar er wordt uiteindelijk niet gewacht op de muisknop. Het programma doet dus niet wat het moet doen. We lopen de instructies na en kijken waar het mis gaat.
      nop
      nop
lbl1  btst  #6,$bfe001
      beq   lbl1
      rts

Aan de eerste twee NOP-instructies zal het niet liggen. Zoals gevraagd, voert de processor niets uit, twee keer. Ook de RTS aan het eind doet zijn werk. Het programma keert tenslotte terug naar Asm-Pro. Dan blijven er nog twee regels over:
lbl1  btst  #6,$bfe001
      beq   lbl1

De eerste instructie, BTST, test of de zesde bit op geheugenlocatie $bfe001 ‘gezet’ is (%1). Daarmee ‘bekijk’ je de stand van de linker muisknop; neem dat maar aan. (Later geven we overzichten van al die leuke geheugenlocaties.)

Dan blijft er nog één instructie over: BEQ oftewel Branch if EQual. Hier gaat het vermoedelijk mis. Als het antwoord van de eerdere bit-test gelijk is aan waar (equal) – dus als de muisknop inderdaad is ingedrukt – springt de processor naar de instructie die wordt gemarkeerd door het label ‘lbl1’ en test dus opnieuw. In het andere geval – de muisknop was waarschijnlijk nog niet ingedrukt toen je het programma startte – gaat de processor naar de volgende instructie: RTS. Dat is het: er moet alleen opnieuw getest worden als de uitkomst van de bit-test niet waar is – dus als de muisknop niet is ingedrukt. Vervang de BEQ voor een BNE oftewel Branch if Not Equal.

Het eindresultaat ziet er als volgt uit.
      nop
      nop
lbl1  btst  #6,$bfe001
      bne   lbl1
      rts

Test het programma opnieuw. Sla het zonodig op met ‘u’, assembleer het opnieuw met ‘a’ en voer het uit met ‘j’ (update file, assemble, jump).

Als goed is, gebeurt er ogenschijnlijk niets. Maar eigenlijk controleert je programma – honderdduizenden keren per seconde – of je de muis al hebt ingedrukt. Op het moment dat je dat doet, keert jouw machinecode-programma terug naar Asm-Pro. Indrukwekkend! Je hebt zojuist je eerste in assembly geschreven machinecode-programma gemaakt. Je hebt gewonnen van de computer. En zo hoort het¹. Victorie!

Slaine #3
©Simon Bisley

Misschien is niet alles even helder. Dat kan, want je bent in het diepe geworpen. Het maakt ook niets uit. Op dit moment is het proces belangrijker dan het programma zelf.
Punt op de ‘i’

We maken een Amiga-executable bestand van jouw machinecode met het commando ‘wo’.

>wo
Sorting relo-area..
Writing hunk length..
Writing hunk data..
File length = 56 (=$00000038)

Alsjeblieft, jouw stukje werk op disk: 56 bytes! Wanneer je die (nog steeds) overbodige NOP-instructies verwijdert, wordt het zelfs nòg kleiner.

Dit is een belangrijk moment. De fundering is gestort en we kunnen ons nu volledig storten op de inhoud. Let’s make things!

¹ Computers zijn ooit uitgevonden om de mens te dienen.