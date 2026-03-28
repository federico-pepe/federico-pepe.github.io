---
layout: post
title: "Rewire in Ableton Live 11"
date: 2021-03-17 22:05:02 +0000
categories: ["Ableton"]
tags: ["Ableton Live 11", "Audio", "Driver IAC", "Live 11", "Propellerhead", "Rewire", "Steinberg"]
---

Da quando Live 11 è stato rilasciato, sono in molti a lamentarsi per l'eliminazione del Rewire. In realtà questa funzione è stato disabilitata di default ma è possibile riattivarla facendo come segue:

Nel file _Options.txt_ è sufficiente inserire la dicitura `-EnableReWire`

Una volta aggiunta, basta riaprire Ableton Live 11 e, magicamente, il Rewire sarà di nuovo attivo.

## Dove trovo il file Options.txt?

Come indicato nella [documentazione ufficiale](https://help.ableton.com/hc/en-us/articles/209772865-Options-txt-file?fbclid=IwAR1crAxfXQlXyW4drrMwtQk5t0wg5Q3cJcmJ5ocLTAOzC2Htg05B4W4DIic), il file _Options.txt_ si trova nella seguente cartella:

### Windows

```
\Users\[username]\AppData\Roaming\Ableton\Live x.x.x\Preferences\
```

### macOS

```
/Users/[username]/Library/Preferences/Ableton/Live x.x.x/
```

Se il file non è presente, potete crearlo con un normalissimo editor di testo e salvarlo, con nome ed estensioni corretti, nella cartella giusta.

## Cos'è il Rewire?

Il Rewire è una protocollo software sviluppato da **Propellerhead** e **Steinberg** alla fine degli anni '90. L'idea alla base di questa tecnologia era dare la possibilità di trasmettere dati e controlli remoti tra due Digital Audio Workstation. Il protocollo, inserito per la prima volta nel sintetizzatore ReBirth, consentiva la trasmissione di un massimo di 256 tracce audio e di 4080 canali MIDI.

Questa tecnologia viene principalmente utilizzata in questo modo: un sequencer invia dati MIDI ai virtual instrument o soft synth di un'altra DAW e riceve in ingresso il segnalo audio evitando, così, di perdere tempo nella creazione, esportazione e importazioni di file MIDI o audio.

## Perché il Rewire è stato disabilitato in Live 11?

Benché il Rewire sia ancora molto utilizzato è una tecnologia antiquata che, negli ultimi anni, è stato sorpassata da varie alternative più moderne tanto che la stessa Propellerhead ha deciso di interrompere lo sviluppo e il supporto del protocollo alla fine del 2020. Questo, immagino, è il motivo per cui anche Ableton Live ha deciso di disabilitarlo di default nell'ultima versione del programma.

## Come trasmettere MIDI da un'app all'altra?

[![Schermata che rappresenta la finestra Studio MIDI dell'applicazione Configurazione Audio MIDI di macOS. Il driver IAC è selezionato.](/assets/uploads/2021/03/macOS-driver-IAC-1024x751.png)](/assets/uploads/2021/03/macOS-driver-IAC.png)

Se avete la necessità di trasmettere dati MIDI da un'applicazione all'altra su macOS la soluzione ideale è quella di attivare il **Driver IAC** in `Applicazioni / Utility / Configurazione Audio MIDI`. Il driver IAC è, a tutti gli effetti, una scheda MIDI virtuale. Una volta attivato, comparirà come una qualsiasi periferica MIDI all'interno delle nostre DAW.

Su Windows non esiste una scheda MIDI virtuale nativa, per questo è necessario installare [RTP Loop MIDI](http://www.tobias-erichsen.de/software/loopmidi.html) sviluppata da Tobias Erichsen.

## Come trasmettere audio da un'applicazione all'altra.

Per trasmettere l'audio da un'applicazione all'altra è necessario installare sia su Windows che su macOS delle applicazioni di terze parti. Le opzioni principali sono:

- [VoiceMeeter](https://www.vb-audio.com/Voicemeeter/index.htm)&nbsp;(Windows)
- [Jack](https://jackaudio.org/)&nbsp;(Windows eMac)
- [iShowU Audio Capture](https://support.shinywhitebox.com/hc/en-us/articles/204161459-Installing-iShowU-Audio-Capture-Mojave-and-earlier-)&nbsp;(Mac)
- [Soundflower](https://github.com/mattingalls/Soundflower/releases/tag/2.0b2)&nbsp;(Mac)
- [Black Hole](https://github.com/ExistentialAudio/BlackHole)&nbsp;(Mac)
- [Rogue Amoeba Loopback](https://rogueamoeba.com/loopback/)&nbsp;(Mac)
