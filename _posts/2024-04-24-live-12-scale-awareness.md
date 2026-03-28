---
layout: post
title: "Live 12: Scale Awareness"
date: 2024-04-24 12:41:09 +0000
categories: ["Ableton Live 12"]
tags: ["Ableton", "Ableton Live 12", "Editor MIDI", "Meld", "Scale Awareness"]
---

La scale awareness non è una novità vera e propria di Ableton Live 12 ma si tratta di un importante aggiornamento della funzionalità **_Tonalità e scale_** che era stata aggiunta in Live 11.

Come per i [Generatori MIDI](https://blog.federicopepe.com/2024/04/midi-generator-in-ableton-live-12/) ho fatto un video che ho caricato sul canale YouTube degli Ableton Certified Trainer me se, come me, preferite leggere una spiegazione invece che guardarla, potete proseguire con questo articolo.

{% youtube "https://www.youtube.com/watch?v=nolUMZt1BZk" %}

## Cos'è la scale awareness?

Spiegata in modo semplice, la **scale awareness** è la possibilità di impostare una tonalità e una scala musicale per il progetto di Live su cui state lavorando o per ciascuna clip in modo indipendente.

[![Uno screenshot di Live 12 che mostra il menu di selezione della scala nella toolbar aperto.](/assets/uploads/2024/04/Live-12-Scale-Awareness-Toolbar-325x1024.png)](/assets/uploads/2024/04/Live-12-Scale-Awareness-Toolbar.png)

In Live 12 troviamo un nuovo menu nella toolbar che ci permette di selezionare la tonalità e una delle tantissime scale disponibili che derivano dal sistema di armonia occidentale oppure da altre tradizioni musicali. Attenzione di non confondere la scelta di una scala con i [_Tuning System_ di cui ho parlato in un altro video](https://youtu.be/DfnKm97U2Qw?si=lEI24NP11MruFg7p).

## Visuale nell'editor MIDI

[![](/assets/uploads/2024/04/Ableton-Live-12-Scale-Awareness-Editor-MIDI-1024x421.png)](/assets/uploads/2024/04/Ableton-Live-12-Scale-Awareness-Editor-MIDI.png)

Quando creiamo una nuova clip, di default verranno impostate la tonalità e la scala che sono selezionate nella toolbar ma, nel pannello delle impostazioni della clip in basso a sinistra è possibile impostare una scala diversa o, cliccando sul pulsante con il simbolo del bemolle e diesis, disabilitare la scale awareness.

### Highlight Scale

Sempre nell'editor MIDI è stata aggiunta una spunta _Highlight Scale_ che fa in modo che vengano evidenziate le note che fanno parte della scala/tonalità selezionata.

### Fold to scale

Come in Live 11 possiamo cliccare sul pulsante _Scale_ per eliminare dalla visualizzazione le note che non fanno parte della scala/tonalità selezionata nella clip.

Entrambe queste funzionalità possono essere utili per chi non è molto pratico con la teoria musicale o per chi, semplicemente, vuole avere dei riferimenti visivi in fase di composizione.

## Scale awareness negli effetti MIDI

Come dicevo all'inizio, fino a qui nulla di particolarmente nuovo rispetto a Live 11 ma le cose cominciano ad essere interessanti considerando l'aggiornamento degli effetti MIDI.

[![Uno screenshot che mostra una catena di MIDI FX (Chord, Arpeggiator, Pitch, Random e Scale) di Ableton Live 12 con attivo il pulsante di Scale Awareness](/assets/uploads/2024/04/Scale-Awareness-MIDI-FX-Ableton-Live-12-1024x181.png)](/assets/uploads/2024/04/Scale-Awareness-MIDI-FX-Ableton-Live-12.png)

Come potete vedere nell'immagine qui sopra, gli effetti che agiscono sulle note in termini di pitch quindi Chord, Arpeggiator, Pitch, Random e Scale, sono stati tutti aggiornati e presentano la possibilità di attivare la funzione scale awareness su ciascuno di essi indipendentemente.

Da notare il cambiamento dei termini: da _ **st** _, abbreviazione di _semitono_, quando si abilita la scale awareness la didascalia diventa **_sd_** ovvero _scale degree_.

[![](/assets/uploads/2024/04/Chord-Scale-Awareness-disabled.png)](/assets/uploads/2024/04/Chord-Scale-Awareness-disabled.png)
_Scale Awareness disabilitata_

[![](/assets/uploads/2024/04/Chord-Scale-Awareness-enabled.png)](/assets/uploads/2024/04/Chord-Scale-Awareness-enabled.png)
_Scale Awareness abilitata_

Ecco che, ad esempio, se in Chord voglio creare un accordo maggiore in Live 11 avrei dovuto impostare +4st (3a maggiore) e +7st (5a giusta) mentre in Live 12 avendo selezionato una scala maggiore, sarà sufficiente settare gli shift a +2sd e +4sd.

Attenzione, però, perché se nell'impostazione con i semitoni, tutti gli accordi suonati, indipendentemente dalla nota di partenza sono tutti accordi maggiori, con la scale awareness attiva verranno suonati gli accordi armonizzati della scala selezionata.

Facciamo un esempio: se imposto come scala C major e setto Chord a +2sd e +4sd come nell'immagine qui sopra:

- Se suono la nota C, verranno aggiunte le note E e G rispettivamente 2 e 4 gradi della scala oltre la nota suonata. L'accordo risultante sarà C maggiore.
- Se suono la nota D, verranno aggiunte le note F e A ovvero un accordo di D minore.
- Se suono la nota E, verranno aggiunte le note G, e B ovvero E minore
- ... e così via.

Personalmente penso che questa sia una delle cose più interessanti legate alla _scale awareness._

Sfruttando gli effetti MIDI e impostando tonalità e scale particolari potrete esplorare facilmente accordi e armonizzazioni che non siete soliti usare o che difficilmente vi verrebbe naturale scegliere in fase di composizione.

## Generatori e Trasformazioni MIDI in Live 12 seguono scala e tonalità

I nuovi strumenti nell'editor MIDI ovvero generatori e trasformazioni seguono tutti l'impostazione di scale awareness se, ovviamente, è stata abilitata all'interno della clip.

Potete quindi generare nuove idee oppure modificare parti MIDI esistenti non dovendovi preoccupare che il sistema generi note fuori tonalità.

## Meld: il primo synth scale aware

Oltre a tutte le novità di cui abbiamo parlato riguardo tutta la parte MIDI, un aspetto interessante è che Meld, il nuovo sintetizzatore aggiunto in Live 12, è il primo strumento scale aware.

Su Meld ho in programma di scrivere un articolo dettagliato ma come potete vedere nell'immagine, alcuni macro oscillatori e i due filtri _plate resonator_ e _membrane resonator_ presentano il simbolo bemolle/diesis e, quindi, possono seguire la tonalità e la scala che abbiamo impostato.

[![](/assets/uploads/2024/04/Meld-Synth-scale-Aware-Live-12-1024x640.png)](/assets/uploads/2024/04/Meld-Synth-scale-Aware-Live-12.png)

In attesa dell'articolo o del video su Meld vi invito a sperimentare per provare a capire come utilizzare al meglio queste funzionalità nel synth.
