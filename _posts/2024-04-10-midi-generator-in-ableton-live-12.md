---
layout: post
title: "MIDI Generator in Ableton Live 12"
date: 2024-04-10 11:12:23 +0000
categories: ["Ableton Live 12"]
tags: ["Ableton", "Ableton Live 12", "MIDI Generator"]
---

Se anche a voi è capitato di sedervi davanti al computer, aprire la vostra _digital audio workstation_ preferita e non riuscire a produrre nemmeno un'idea interessante, ecco che i **MIDI Generator** di Ableton Live 12 potrebbero esservi d'aiuto.

{% youtube "https://www.youtube.com/watch?v=iPYXKYo4FD0" %}

_Se vi stufate a leggere, potete vedere il video che ho realizzato per il canale YouTube degli Ableton Certified Trainer._

## A cosa servono i MIDI Generator?

I generatori MIDI sono strumenti pensati per produrre, partendo da zero, delle informazioni MIDI.

Come accennavo all'inizio dell'articolo possono essere molto efficaci se stiamo vivendo un momento di blocco creativo così come possono essere strumenti utili per sperimentare e provare idee nuove che difficilmente ci verrebbe naturale scrivere.

I MIDI Generator sono utili anche per velocizzare alcuni processi creativi o la scrittura di parti MIDI complesse da poter poi, eventualmente, mandare a synth esterni o drum machine.

La cosa interessante è che trattandosi semplicemente di informazioni MIDI che vengono generate, le potete utilizzare come volete.

## MIDI Generator di Ableton Live

[![Uno screenshot dell'editor MIDI di Ableton Live 12 con una freccia rossa che indica il pannello dei MIDI Generator.](/assets/uploads/2024/04/MIDI-Generator-Ableton-Live-12.png)](/assets/uploads/2024/04/MIDI-Generator-Ableton-Live-12.png)

I generatori si trovano all'interno dell'editor MIDI di Live 12 nell'ultimo pannello a destra (o in basso se preferite una disposizione verticale).

Cliccando sul menu a tendina potete vedere che sono inclusi quattro generatori creati da Ableton: _Rhythm, Seed, Shape e Stacks_, due generatori nella categoria Max for Live: _Euclidean_ e _Max MIDI Generator_ e, se avete già installato altri generatori li troverete nella cartella User, ma di questo parleremo alla fine dell'articolo.

Prima di approfondire nel dettaglio ciascun generatore concentriamoci sui punti in comune. Tutti presentano due pulsanti sotto l'interfaccia: il tasto _Generate_ che, se attivo, genererà all'interno della clip le informazioni MIDI non appena muoverete un parametro qualsiasi.

Se disattivate _Generate_ potete usare il tasto _Apply_, il tasto con la freccia verso destra accanto a generate, per scrivere la parte MIDI all'interno della clip.

In alto a sinistra trovate il tasto _Reset_ che permette di riportare allo stato iniziale il generator se avete mosso alcuni parametri.

### Rhythm

[![Uno screenshot del MIDI Generator Rhythm in Ableton Live 12](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Rhythm.png)](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Rhythm.png)

Rhythm è un generatore di pattern ritmici. L'utilizzo più comune probabilmente sarà per creare delle parti di batteria ma non limitatevi solo a quello. Potete usarlo anche su strumenti melodici per generare, ad esempio, linee di basso.

Se sulla traccia MIDI avete caricato un Drum Rack nel menu a tendina all'interno dell'interfaccia troverete l'elenco degli strumenti per cui è possibile creare un pattern. Se, come me, pensate che usare questo dropdown sia scomodo, potete tenere premuto Alt/Option e cliccare sulla nota nel piano roll per selezionarla automaticamente.

La parte principale di Rhythm sono le tre manopole:

- _Steps_ determina il numero delle note generate all'interno del pattern.
- _Pattern_ permette di modificare il pattern ritmico generato
- _Density_ aumenta o diminuisce la densità ovvero la quantità di note che verranno generate.

_Step duration_ indica la divisione ritmica di ciascuno step. Al di là delle classiche divisioni musicali dalla battuta a 1/128 ci sono due opzioni: _Grid_ che segue la suddivisione della griglia impostata e _Fit_ che genererà note in base alla porzione di tempo selezionata nella clip.

[![Uno screenshot che mostra un semplice pattern di batteria generato con Rhythm](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Rhythm-Pattern-1024x275.png)](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Rhythm-Pattern.png)
_Un semplice pattern di batteria generato con Rhythm_

_Split_ indica la probabilità espressa in percentuale che le note generate vengano suddivise ulteriormente in due step di uguale durata.

_Shift_ sposta il pattern degli step verso sinistra, se impostato con valori positivi, o verso destra se con valori negativi.

Infine troviamo l'impostazione della _Velocity_ con cui possiamo scegliere il valore di velocity di base (numero a sinistra) e il valore di velocity della nota accentata (numero a destra).

Sulla destra impostiamo il numero di note generate prima che venga aggiunta una nota accentata e, tramite le due frecce, possiamo decidere quale nota del pattern vogliamo che venga accentata.

### Seed

[![Uno screenshot che mostra nel dettaglio il MIDI Generator Seed](/assets/uploads/2024/04/MIDI-Generator-Seed-Ableton-Live-12.png)](/assets/uploads/2024/04/MIDI-Generator-Seed-Ableton-Live-12.png)

Seed è il secondo generatore di Ableton pensato per generare dei gruppi di note. Con il primo slider stabiliamo il range dalla nota più bassa a quella più alta. Con il secondo controllo definiamo un intervallo di lunghezze che può andare da 1/128 a un'intera battuta e, infine, con l'ultimo slider decidiamo un range di velocity.

Abbiamo poi due ulteriori controlli per determinare il numero di voci ovvero di note che possono suonare contemporaneamente, come fossero degli accordi, per capirci e _density_ per stabilire la quantità totale di note generate.

[![Uno screenshot di Ableton Live 12. La vista dettagliata è aperta e mostra una clip MIDI di 4 battute in cui sono state generate delle note usando Seed. Anche il pannello delle velocity è aperto per mostrare le variazioni create sempre da seed.](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Seed-1024x576.png)](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Seed.png)
_Un tipico risultato che si ottiene utilizzando il generatore Seed_

La cosa importante da sottolineare a questo punto, che sarà valida anche per i due successivi generatori, è che i MIDI Generator seguono l'impostazione di scala e tonalità ovvero la _scale awareness_ impostata nel progetto o nella clip. Questo significa che tutte le idee generate con Seed, Shape e Stacks saranno sempre in tonalità.

### Shape

[![Uno screenshot di Ableton Live 12 che mostra il MIDI Generator Shape nel suo stato di default](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Shape.png)](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-Shape.png)

Shape un generatore MIDI pensato principalmente per generare delle linee melodiche. Nel menu a tendina sono disponibili varie forme di partenza: _flat, up, down, up & down, down & up, arc up, arc down, bounce up e bounce down,_ ma, per quanto mi riguarda, la cosa più divertente è andare con il mouse direttamente nell'interfaccia e disegnare la forma che ci interessa.

[![Uno screenshot di Ableton Live 12 in cui si vede nel dettaglio il MIDI Generator Shape impostato in modalità Utente con un disegno personalizzato della forma.](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Shape-User-generated-Shape.png)](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Shape-User-generated-Shape.png)

Il generatore si completa con un'impostazione del range del pitch e quattro manopole: _Rate_ per definire la lunghezza minima delle note, _Tie_, espresso in percentuale, che stabilisce la probabilità con cui una nota o una pausa venga allungata fino al raggiungimento della nota successiva. Come sempre abbiamo _Density_ per stabilire la quantità di note che vogliamo siano generate e _Jitter_ che crea delle variazioni randomiche della forma generata.

### Stacks

[![](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Stacks.png)](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Stacks.png)

Stacks è, insieme a Rhythm, il mio MIDI Generator preferito e permette di creare degli accordi o delle progressioni di, massimo, quattro accordi.

Nell'interfaccia è presente una forma che possiamo cliccare e trascinare con il mouse verso l'alto e verso il basso per generare accordi diversi. Come mostrato nell'immagine, nella barra di stato in basso viene indicato che il tipo di accordo che viene generato in base, ovviamente, ai parametri impostati nel generatore e la scala e la tonalità della clip.

[![Uno screenshot di Live 12 che mostra nel dettaglio il MIDI Generator Stacks e la status bar che indica: Chord: C E G B - Cmaj7 - Scale Degrees: 1 3 5 7](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Stacks-With-status-Bar.png)](/assets/uploads/2024/04/Ableton-Live-MIDI-Generator-Stacks-With-status-Bar.png)

In questo esempio, la clip è impostata in tonalità di C Major e la forma selezionata genera un accordo di settima maggiore (Cmaj7) con i gradi 1, 3, 5 e 7 della scala.

Con i pulsanti + e - sulla destra dell'interfaccia possiamo aggiungere altri accordi all'interno della stessa clip. Con la manopola _Root_ selezioniamo la fondamentale dell'accordo e con _Inversion_ il rivolto che desideriamo.

Completano le opzioni _Duration_ con il quale impostiamo la durata di ciascun accordo e _Offset_ per spostare orizzontalmente rispetto alla griglia la posizione di ciascun accordo.

## MIDI Generator in Max for Live

Come accennavo all'inizio uno dei punti di forza dei MIDI Generator è la possibilità di creare, se ne siamo capaci, o di aggiungere altri generatori fatti in Max fo Live da sviluppatori di terze parti.

Basta scaricare il file .amxd e trascinarlo all'interno della nostra libreria utente.

[![Screenshot di Live 12 che mostra il menu a tendina per la scelta dei generator aperto con un generatore aggiunto chiamato Phase Pattern che compare nella categoria User](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-in-Max-for-Live.png)](/assets/uploads/2024/04/Ableton-Live-12-MIDI-Generator-in-Max-for-Live.png)
_I generatori aggiunti compariranno nella categoria User come, in questo caso, il Phase Pattern_

Dal 5 marzo, giorno in cui è stato rilasciato Live 12 ufficialmente, erano disponibili già diversi generatori creati da sviluppatori di terze parti.

Vi segnalo, nello specifico, un bundle di 12 generatori creati da Philip Meyer che potete acquistare direttamente [sul suo Gumroad](https://philipmeyer.gumroad.com/l/midi-tools-bundle) e che, magari, approfondiremo in un articolo in futuro.

JEKYLLYOUTUBE\_LpA66peATgPLACEHOLDER
