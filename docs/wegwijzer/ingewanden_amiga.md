---
layout: default
title: Ingewanden van Amiga
parent: Wegwijzer
nav_order: 5
---
Het is goed mogelijk dat je inmiddels een Amiga in het wild hebt gezien. Je hebt wat spellen gespeeld en demo’s bekeken. Misschien heb je jezelf een weg gebaand door het besturingssysteem Workbench. Laten we de Amiga open zagen om te kijken wat er in zit. Je wilt vast weten wat er technisch mogelijk is.

We gaan uit van een standaard Amiga 500. De Amiga 500 is de opvolger van de eerste Amiga, de Amiga 1000. Er zijn over de jaren verschillende Amiga-modellen uitgebracht. De Amiga 500 is de meest verkochte: er liggen er nog duizenden te wachten op stoffige zolders tot ze worden herontdekt door de volgende generatie nieuwsgierigen. Daarnaast — en evenzo belangrijk — vrijwel elk spel en demo werd ontworpen met deze populaire ‘500’ in gedachten.

Commodore Amiga 500
Commodore Amiga 500

    Heb ik per sé een Amiga 500 nodig?

Mocht je werken met een andere Amiga dan is dat geen enkel probleem. We zullen er rekening mee houden.
Het binnenwerk

Het kloppende hart van een Amiga 500 is de Motorola 68000-processor. Dat hart klopt iets sneller dan het onze: ruim 7 miljoen keer per seconde! (Ongeveer 7 MHz.) Een enkele hartklop van de processor noemen we een cycle. Voor het uitvoeren van een opdracht, bijvoorbeeld het lezen van een waarde uit het geheugen, heeft de 68000 een aantal hartkloppen — cycles — nodig. De 68000 kan gemiddeld, ruw geschat, een miljoen instructies per seconde uitvoeren.

Motorola 68000
Motorola 68000

Een Amiga 500 heeft standaard 0,5 MB geheugen. Wat is MB? MB is de afkorting voor megabyte. Een halve megabyte is hetzelfde als 524.288 bytes. Dat is een mond vol en daarom worden voor informatie-eenheden vaak de voorvoegsels kilo en mega (en giga en tera) gebruikt.

1 kilobyte (KB) = 1024 bytes
1 megabyte (MB) = 1024 kilobytes
1 gigabyte (GB) = 1024 megabytes

    “1024? Je bedoelt 1000!”

Nee, 1024. In de computerwereld werden (en worden) voorvoegsels als kilo en mega anders gebruikt dan officieel voorgeschreven. Omdat een computer machten van twee gebruikt (juist, binair) en omdat 210 = 1024 zo lekker dicht bij 1000 ligt, werd ooit bedacht dat het handig zou zijn om 1024 bytes een kilobyte te noemen. Na tientallen jaren en het groter worden van de capaciteit van computergeheugens en harddisks is in 1998 een nieuwe standaard voor binaire voorvoegsels geïntroduceerd om deze verwarring tegen te gaan.

1 kibibyte (KiB) = 1024 bytes
1 mebibyte (MiB) = 1024 kibibytes
1 gebibyte (MiB) = 1024 mebibytes

Wanneer je deze termen gebruikt, zullen coders vriendelijk naar je lachen en zich afvragen welk leuk, nieuw, gekleurd speelgoedpaardje je bedoelt.

My Little Pony

Voor echte programmeurs is een kilo 1024. Houd wel in gedachten dat er andere mensen zijn, met name harddiskfabrikanten, die voor een kilo (terecht) 1000 nemen. Schrijf als je dat nodig vindt de volgende reeks getallen op: 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024. Je zult ze binnen afzienbare tijd kunnen dromen.

Jouw standaard Amiga 500 is dus uitgerust met een halve megabyte, ofwel (1024 : 2 =) 512 kilobyte geheugen. De 68000 heeft zodoende een ’geheugenstraat’ tot zijn beschikking met ruim een half miljoen huisadressen, exact (512 × 1024 =) 524.288 bytes.

De Motorola 68000 is gebruikt in veel apparaten: computers, synthesizers, wasmachines. Amiga’s hebben ook speciaal voor Commodore Amiga ontworpen custom chips. Deze chips dragen de interessante namen Agnus, Denise en Paula en voeren specialistische taken uit.

Agnus zorgt ervoor dat zowel de processor als de custom chips toegang hebben tot hetzelfde geheugen. Ze¹ huisvest ook de Blitter en de Copper. De Blitter kan onder andere snel gegevens kopiëren in het geheugen, lijnen trekken, vlakken vullen en de Copper beheert het monitorsignaal: uitermate handig.

Denise is de videoprocessor. Het grafische scherm van de Amiga is maximaal 320 of 640 pixels² (beeldpunten) breed en 256 pixels hoog. Lo-res (320) toont maximaal 32 verschillende kleuren op het scherm en hi-res (640) maximaal 16. Er kan gekozen worden uit een palet van 4096 kleuren. Denise ondersteunt ook een interlace-modus waarbij de verticale resolutie wordt verdubbeld van 256 naar 512 pixels. Het gevolg van deze verdubbeling is een irritant flikkeren van het scherm. Overscan-modus zorgt voor een maximale resolutie van 704 bij 288 pixels. (Dat is 576 pixels hoog in interlaced-modus.) De Amiga kan deze modussen door elkaar gebruiken. Er bestaan meer video-modi zoals HAM, EHB en dual-playfield waar we, net als sprites (acht stuks!), later op in gaan.

Paula verzorgt onder andere het geluid. Ze kent vier onafhankelijke audio-kanalen: twee voor links en twee voor rechts, stereo dus. Ze speelt 8-bit samples af: klinkt mooi!
De besturingssoftware

Een ander belangrijk aspect van de Amiga is het besturingssysteem. De besturingssoftware van de Amiga bestaat eigenlijk uit twee delen: Kickstart en Workbench. Kickstart is bij het aanschakelen van de Amiga 500 direct beschikbaar. Het bevindt zich namelijk in het ROM-geheugen. ROM is geheugen dat enkel kan worden gelezen, niet geschreven. De Kickstart-software controleert direct na het inschakelen de goede werking van de hardware, stelt de custom chips in en initialiseert een aantal onderdelen van het besturingssysteem. Daarna kijkt Kickstart of er opslagsystemen beschikbaar zijn waarvan opgestart kan worden, zoals een harddisk³. Dit proces noemen we booten. Wanneer er geen harddisk wordt gevonden, vraagt Kickstart de gebruiker om een Workbench-diskette.

Insert Kickstart disk

Die vraagt hoeft niet per sé beantwoord te worden met de Workbench. Op de diskette kan net zo goed een spel, demo of eigen werk staan. Kickstart bevat ook belangrijke software-bibliotheken van het besturingssysteem. Let op. Kickstart, dat wordt een verhaal op zich.

Workbench is de grafische gebruikersinterface van Amiga. Moderne varianten als Mac OS en Windows kennen gelijkenis met de Workbench. De gebruiker kan met Workbench programma’s starten, met bestanden werken, schermvoorkeuren instellen, enzovoorts.

De systemen die een Amiga vormen zitten vernuftig in elkaar. Zowel de hardware als de software. Dat gold medio jaren tachtig en dat is nog steeds het geval. We geven hierboven slechts een globaal overzicht van de mogelijkheden. Commodore Amiga bracht het fenomeen custom chips als volgt.

Advertentie Commodore Amiga

Dat doen wij ook. We laten de mogelijkheden aan jouw fantasie over. Net zoals wij dat voelden eind jaren tachtig. Onderschat het nut van je fantasie niet: natuurlijk zijn de hardware-eigenschappen een feit, maar het plafond ligt al veel hoger. Honderden verschillende kleuren in hi-res, 14-bit geluid afspelen. Mogelijk. Je fantasie is de werkelijke limiet.

Wat kan ik met 32 verschillende kleuren op een scherm? Ik kan de Amiga laten spreken? Hoe doen ze dat? Als ik nou eens…

Lees verder: Assembly en de taal van de machine.