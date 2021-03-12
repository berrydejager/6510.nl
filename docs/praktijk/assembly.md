---
layout: default
title: Assembly en de taal van de machine
parent: Praktijk
nav_order: 1
---
# Color Utilities
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
In de introductie leerde je dat een microprocessor de taal assembly ‘spreekt’. Dat is niet helemaal correct. Eigenlijk kent een processor enkel machinetaal. Machinetaal, machinecode of simpelweg code is echter voor de meeste mensen — er zijn uitzonderingen — nagenoeg onleesbaar.
Waslijsten machinecode

Afhankelijk van het type processor bestaat een machinetaalinstructie uit een of meerdere bytes. Zo een lijst met instructies voor de 68000-processor zou er als volgt uit kunnen zien.
48E7 FFFE
23FC 0000 0000 0000 007C
23FC 0000 0000 0000 0080
7000
7200
2E3C 0000 0347
2079 0000 007C
1010
43F9 0000 0000
7C60
1219
B200
6606
1011
6000 0018
D3FC 0000 0001
51CE FFEC
33FC 0F00 00DF F180
6000 0024
7C00
2079 0000 0080
1080
06B9 0000 0001 0000 007C
06B9 0000 0001 0000 0080
51CF FFAE
4CDF 7FFF
4E75

Weinigzeggend, niet? Daarom schrijven we instructies voor de processor liever in de mensvriendelijke taal assembly en schakelen vervolgens de hulp in van een tolk – een assembler – om assembly te vertalen naar machinetaal.
Vriendelijk assembly

Laten we een willekeurige assembly-instructie in het wild bekijken:
nop

De instructie NOP is een samentrekking van No OPeration. Een ander woord voor zo een leesbare instructie is mnemonic. Dat betekent ‘geheugensteuntje’ of ‘ezelsbruggetje’. Bijvoorbeeld, met het mnemonic NOP geven we de processor de opdracht om niets te doen¹. Een assembler vertaalt de instructie NOP voor ons naar machinecode: $4E71.

Bekijk het volgende programma eens; een set instructies in assembly zegt je vast meer dan rauwe machinecode. De 68000-processor zal ze regel voor regel uitvoeren. (De regelnummers zijn slechts ter verduidelijking.)
1
2
3
4
5
	
      nop
      nop
lbl1  btst  #6,$bfe001
      bne   lbl1
      rts

De kans bestaat dat je het programma – zonder dat je ooit een regel assembly hebt getypt – enigszins kunt volgen. Zéker met een beknopte uitleg:

    Doe niets;
    Doe niets;
    Test of de zesde bit op geheugenlocatie $bfe001 aanstaat (1);
    Is het voorgaande niet waar – dus staat bit 6 uit (0) – spring dan terug naar de geheugenplaats gemarkeerd met het label ‘lbl1’ (in dit geval de vorige instructie) en ga anders gewoon verder;
    Keer terug naar waar je vandaan komt.

Volg je het? Misschien raadde je het al:

    BTST staat voor Bit TeST
    BNE staat voor Branch if Not Equal
    RTS staat voor Return To Subroutine

    “Tja, ik kan het wel volgen maar het zegt me niets!”

We kleden het programma uit. Weg met die onzinnige NOP’s!
1
2
3
	
lbl1  btst  #6,$bfe001
      bne   lbl1
      rts

Om het programma te kunnen begrijpen, schijnen we licht op die bewuste zesde bit op geheugenadres $bfe001. Deze bit wordt aangezet (1) als de linker muisknop wordt ingedrukt. Dat wordt gedaan door de Amiga-hardware: altijd, automatisch. Lees het programma nu nog eens terug in gewone mensentaal:

    Kijk of de linker muisknop werd ingedrukt.
    Niet? Test dan opnieuw. Ga anders verder.
    Keer terug naar waar je vandaan komt.

Schermafdruk Asm-Pro

Dit kleine programmaatje wacht dus geduldig – tot in eeuwigheid – op het moment dat de gebruiker de linker muisknop indrukt en keert daarna terug. ‘Een kind kan de was doen!’ Maar dan hebben we nog wèl even een wasmachine nodig: de assembler.

Wasmachine-assemblage
Functie van de assembler

De belangrijkste taak van een assembler is het omzetten van assembly naar machinecode voor een specifieke processor. Er is een ruim aantal assemblerprogramma’s beschikbaar voor de Commodore Amiga; tientallen.
(Ooit) populaire assemblers

    HiSoft DevPac
    Asm-Pro
    ASM-One
    Barfly
    PhxAss
    SEKA en MasterSEKA

Veel van die assembler-pakketten kennen – naast het assembleren van broncode – nog andere, extra mogelijkheden.

    Disassembler, monitor
    Debugger
    Generator voor (sinus-)tabellen
    Lezen en schrijven van sectoren op een diskette
    Ondersteuning voor latere CPU’s (tot en met 68060), FPU en MMU
    Macro-ondersteuning
    Automatische machinecode-optimalisatie

In de toekomst zul je waarschijnlijk een voorkeur ontwikkelen voor een bepaald assemblerpakket. Hier, op 6510.nl, zullen we Asm-Pro gebruiken². Asm-Pro is een gedateerd maar volwassen assemblerpakket dat goed werkt op ‘moderne’ klassieke Amiga’s en biedt daarnaast interessante extra mogelijkheden. (Blijf op grote afstand van SEKA. SEKA was populair eind jaren-80 maar bevat een aantal vervelende fouten en genereert daardoor soms incorrecte machinecode.)

Schermafdruk Asm-Pro

Wat nu? Installeer een assembler. Dat is voorlopig je enige en het meest belangrijke wapen. In de volgende twee artikelen wordt het complete proces beschreven van niets tot iets; een uitvoerbaar bestand ofwel een Amiga-executable. De eerste werkelijke modderstappen als ‘coder’.

Lees verder: Asm-Pro: laarzen aan en zwemmen!

¹ Het nut van NOP? Goede vraag. Met deze instructie kun je onder andere machinecode ‘uitlijnen’ zodat de volgende instructie op een even adres begint. Je kunt er mee ‘timen’ – ofwel heel even pauzeren – want het uitvoeren van een NOP duurt precies 4 processorcycli. Softwarekrakers vinden NOP’s ook heel leuk want je kunt er de machinecode die bijvoorbeeld controleert of een dongle aanwezig is mee overschrijven.
² Wanneer jouw Amiga een lagere Kickstart-versie heeft dan 2.04, gebruik dan ASM-One. Deze assembler heeft een versie beschikbaar voor Kickstart 1.3 en de werking is nagenoeg hetzelfde als die van Asm-Pro.