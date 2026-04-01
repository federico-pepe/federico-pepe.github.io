---
layout: post
title: "Processing e Ableton: sincronizzare musica e visual via MIDI"
date: 2017-03-05 14:03:54 +0000
categories: ["Ableton", "Audio"]
tags: ["Albeton Live", "MIDI", "Processing", "Sincronizzazione"]
description: "Come sincronizzare visual generativi in Processing con la musica di Ableton Live via MIDI, usando la libreria The MidiBus e il driver IAC su macOS."
---

Oggi sfrutteremo Processing per creare dei semplici visual sincronizzati con la musica attraverso il protocollo MIDI. Il software musicale che userò per fare gli esempi è Ableton Live 9 ma è possibile&nbsp;usare qualsiasi Digital Audio Workstation in grado di inviare messaggi MIDI. Lo schema delle connessioni, dunque, sarà: Ableton Live gestirà la musica e invierà, attraverso dei messaggi MIDI, delle informazioni che Processing acquisirà in input per generare i visual.

## MIDI e the MidiBus
Perché ho deciso di sfruttare il protocollo **MIDI**? Le ragioni sono molto semplici:
1. è uno standard per le applicazioni musicali
2. è&nbsp;un protocollo flessibile
3. è semplice&nbsp;creare, inviare e monitorare i messaggi MIDI.
4. rende molto semplice la sincronizzazione

Per questioni di spazio, non mi dilungherò in questo post sulla spiegazione di come funziona questo protocollo; trattandosi di uno standard sviluppato negli anni '80, ci sono numerose risorse on-line che vi permettono di approfondire.
### Libreria: the MidiBus
Anche se Java [supporta nativamente](http://docs.oracle.com/javase/1.5.0/docs/api/javax/sound/midi/package-summary.html) il MIDI attraverso il pacchetto java.sound.midi, per&nbsp;lavorare con questi tipi di messaggi in&nbsp;Processing consiglio di&nbsp;[installare una libreria](https://blog.federicopepe.com/2016/05/librerie-di-processing/). ![Processing Contribution Manager MIDI Bus](/assets/uploads/2017/03/Processing-Install-The-Midi-Bus-1024x931.png)Aprite Processing, andate nel menu&nbsp;_Tool \> Add new tool._ Nel pannello&nbsp;_Libraries **&nbsp;** _digitate MIDI, selezionate [**The Midi Bus**](http://www.smallbutdigital.com/themidibus.php) e cliccate sul pulsante&nbsp;_Install_ in basso a destra.
### macOS: IAC Driver
Di norma per inviare&nbsp;e ricevere messaggi MIDI è necessario dotarsi di una scheda e dei relativi cablaggi. Nel nostro caso, però, dovendo inviare e ricevere messaggi tra due applicazioni&nbsp;possiamo&nbsp;sfruttare lo **IAC Driver** : una scheda virtuale&nbsp;che ci permette di gestire tutte le connessioni internamente al computer. **Nota** : Per Windows esistono delle applicazioni da installare che hanno la stessa funzione del driver IAC. Con una veloce ricerca su Google ho trovato&nbsp;**[LoopBe1](http://nerds.de/en/loopbe1.html)**&nbsp;e [**MIDI Yoke**](http://www.midiox.com/myoke.htm)&nbsp;che non ho provato personalmente ma sono consigliate su diversi forum. Per configurare lo IAC Driver su macOS aprite&nbsp;_Applicazioni \> Utility \> Configurazione MIDI Audio.&nbsp;_Cliccate su&nbsp;_Finestra \> Mostra Studio MIDI_ ⌘2 ![Studio MIDI macOS IAC Driver](/assets/uploads/2017/03/macOS-Configurazione-MIDI-Audio-1024x760.png)Fate doppio click su&nbsp; **IAC Driver** e mettete la spunta su&nbsp;_Il dispositivo è acceso_. ![mac OS accendere IAC Driver](/assets/uploads/2017/03/OSX-IAC-Driver-acceso-969x1024.png)Ora che abbiamo attivato il canale di comunicazione interno per inviare e ricevere messaggi MIDI,&nbsp;possiamo procedere con Processing.
## Ricezione messaggi MIDI in Processing
Apriamo un nuovo sketch e verifichiamo subito che Processing veda lo IAC Driver.
```
/*
 * Processing e Ableton: sincronizzare musica e visual via MIDI
 * Federico Pepe, 05.03.2017
 * http://blog.federicopepe.com/processing
*/

import themidibus.*;

void setup() {
  size(100, 100);
  background(0);

  MidiBus.list(); 
}

void draw() {
  
}
```
Con queste poche righe di codice abbiamo importato la libreria all'interno del nostro programma e attraverso il comando `Midibus.list()` possiamo verificare nella console tutte le periferiche MIDI attive. Questo è il risultato che ottengo lanciando il programma sul mio Mac. Ovviamente potrebbe cambiare sul vostro; l'importante è che sia presente IAC Bus.
```
Available MIDI Devices:
----------Input----------
[0] "IAC Bus 1"
[1] "Real Time Sequencer"
----------Output----------
[0] "Gervill"
[1] "IAC Bus 1"
[2] "Real Time Sequencer"
```

### Progetto Ableton Live: invio del messaggio
Apriamo Ableton Live e creiamo un nuovo progetto. Apriamo le preferenze e verifichiamo che il driver IAC sia selezionato come scheda sia per l'input che per l'output. ![Ableton Live 9 MIDI Preferences](/assets/uploads/2017/03/Ableton-Live-9-Preferenze-MIDI-880x1024.png)Nella prima traccia MIDI nella parte di input/output selezioniamo&nbsp; **MIDI To** \>&nbsp; **IAC Driver**. In questo modo tutti i messaggi che saranno presenti su questa traccia saranno inviati come output al driver e, di conseguenza, saranno ricevuti da Processing. [![Ableton MIDI Out Tracks](/assets/uploads/2017/03/Ableton-9-MIDI-Out-IAC-Driver-1024x619.png)](/assets/uploads/2017/03/Ableton-9-MIDI-Out-IAC-Driver.png) Creiamo una Clip MIDI nel primo slot contenente&nbsp;un C3 lungo 1/4. Assicuriamoci che la clip sia il loop quando premiamo il tasto&nbsp;_play_ su di essa. [![MIDI Clip](/assets/uploads/2017/03/Ableton-Live-MIDI-Clip-1024x619.png)](/assets/uploads/2017/03/Ableton-Live-MIDI-Clip.png)
## Ricezione del messaggio
Torniamo su Processing e modifichiamo il nostro programma come segue:
```
/*
 * Processing e Ableton: sincronizzare musica e visual via MIDI
 * Federico Pepe, 05.03.2017
 * http://blog.federicopepe.com/processing
*/

import themidibus.*;

MidiBus myBus;

void setup() {
  size(100, 100);
  background(0);

  MidiBus.list(); 
  
  myBus = new MidiBus(this, 0, 1);
}

void draw() {
  
}

void noteOn(int channel, int pitch, int velocity) {
  println();
  println("Note On:" + " Channel: "+channel + " Pitch: "+pitch + " Velocity: "+velocity);
  println("--------");
}
```
Rispetto al codice scritto in precedenza, abbiamo aggiunto e inizializzato un oggetto di tipo MidiBus: `myBus = new MidiBus(this, 0, 1);`. In questa fase è fondamentale inserire i parametri corretti: il primo è il&nbsp;_parent_ a cui la libreria è collegata, il secondo è l'_input_ e l'ultimo&nbsp;l'_output._ I dati sono facilmente individuabili grazie al comando&nbsp;_.list()_ dato in precedenza. Abbiamo, infine, aggiunto una funzione che è presente all'interno della libreria: **noteOn()** e&nbsp;che restituisce i valori MIDI: canale, pitch e velocity di tutte le note ricevute.
### Verifichiamo il funzionamento
Facciamo partire la nostra clip su Ableton Live e avviamo il nostro sketch su Processing. Se in console appare un messaggio come quello qui di seguito, siamo riusciti nel nostro intento:
```
Available MIDI Devices:
----------Input----------
[0] "IAC Bus 1"
[1] "Real Time Sequencer"
----------Output----------
[0] "Gervill"
[1] "IAC Bus 1"
[2] "Real Time Sequencer"

Note On: Channel: 0 Pitch: 60 Velocity: 127
--------
```
Processing sta&nbsp;ricevendo tramite IAC Driver un messaggio Note On con i seguenti parametri:
- Canale: 0
- Pitch: 60 (che corrisponde al C3)
- Velocity: 127

Adesso, se andiamo a modificare la clip su Ableton inserendo nuovi messaggi, possiamo verificare che anche questi siano ricevuti da Processing.
## Creare i visual
A questo punto non ci resta che sviluppare in Processing i nostri visual&nbsp;sfruttando i parametri MIDI&nbsp;inviati da Ableton. Nell'esempio molto semplice&nbsp;che trovate di seguito, viene disegnato&nbsp;un quadrato al centro dello schermo la cui dimensione dipende dal valore di pitch ricevuto via MIDI.&nbsp;In aggiunta a quanto visto in questo post, sfrutto la funzione _noteOff()_ per&nbsp;impostare la grandezza del quadrato a 0. Di certo non è il metodo più elegante ma di sicuro funziona.
```
/*
 * Processing e Ableton: sincronizzare musica e visual via MIDI
 * Federico Pepe, 05.03.2017
 * http://blog.federicopepe.com/processing
*/

import themidibus.*;

MidiBus myBus;

int size;

void setup() {
  size(400, 400);
  background(0);

  MidiBus.list(); 
  
  myBus = new MidiBus(this, 0, 1);
}

void draw() {
  background(0);
  rectMode(CENTER);
  rect(width/2, height/2, size, size);
}

void noteOn(int channel, int pitch, int velocity) {
  println();
  println("Note On:" + " Channel: "+channel + " Pitch: "+pitch + " Velocity: "+velocity);
  println("--------");
  size = pitch;
}

void noteOff(int channel, int pitch, int velocity) {
  size = 0;
}
```
Ed ecco il risultato: 

{% youtube "https://www.youtube.com/watch?v=eqFHk1\_AN84" %}
