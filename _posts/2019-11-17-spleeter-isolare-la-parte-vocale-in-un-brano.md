---
layout: post
title: "Spleeter: Isolare la parte vocale in un brano"
date: 2019-11-17 16:28:00 +0000
categories: ["Music Technology"]
tags: ["AI", "Deezer", "Music Technology", "Python", "Spleeter", "Tensorflow"]
---

**Aggiornamento al 2 marzo 2021**  
  
Ora è disponibile – in versione beta – un VST sia per Windows che per Mac per utilizzare direttamente Spleeter all'interno della vostra DAW preferita senza bisogno di installare nulla.  
  
Tutte le informazioni sono disponibili a questo link: [https://github.com/diracdeltas/vstSpleeter/releases](https://github.com/diracdeltas/vstSpleeter/releases)

Isolare la parte vocale in un brano musicale è sempre stato un processo lungo, difficile e, spesso, dai risultati incerti.

Negli ultimi anni, grazie soprattutto a nuove tecnologie e all'aumento della potenza di calcolo dei computer, numerose aziende hanno commercializzato software e plugin che garantiscono risultati sempre migliori. Purtroppo siamo ancora lontani dall'avere uno strumento semplice da usare, veloce e in grado di garantire risultati di qualità.

La ricerca o la creazione di _stems_, ovvero le tracce separate partendo da un mix stereo, è un'occupazione che, ancora oggi, porta via a DJ e produttori molte ore di lavoro.

Da oggi le cose potrebbero cambiare grazie a [Spleeter](https://deezer.io/releasing-spleeter-deezer-r-d-source-separation-engine-2b88985e797e): uno strumento rilasciato gratuitamente da [Deezer](https://www.deezer.com) nei giorni scorsi che sfrutta l' **intelligenza artificiale** per separare automaticamente le varie componenti di un brano.

![Spleeter è un software che permette di isolare la traccia vocale da un brano musicale completo.](/assets/uploads/2019/11/spleeter_isolare_voce_e_tracce_da_brano_musicale.jpeg)

I risultati che si ottengono non sono ancora perfetti ma il fatto che Spleeter lavori in completa autonomia e produca degli output in pochissimi minuti è sicuramente un importante passo avanti.

Al momento è possibile separare i brani in 2, 4 oppure 5 stems:

- 2 stems: voce e accompagnamento musicale
- 4 stems: voce, batteria, basso e altre parti
- 5 stems: voce, batteria, basso, piano e altre parti

Per poter utilizzare Spleeter è necessario installare qualche pacchetto sul proprio computer e utilizzare la linea di comando per farlo funzionare. Sono sicuro che nel giro di qualche settimana verrà reso disponibile da qualcuno un programma che integri le funzioni di Spleeter con un'interfaccia grafica semplice da utilizzare.

Per chi fosse curioso di provare Spleeter di seguito troverete le istruzioni passo passo per installare tutto il necessario.

## Installazione su Mac

Per prima cosa è necessario installare [Miniconda](https://docs.conda.io/en/latest/miniconda.html) sul nostro computer. Si tratta di un pacchetto che contiene tutto il necessario per creare un ambiente di sviluppo per far funzionare Spleeter correttamente.

Quando l'installazione è conclusa dobbiamo aprire il Terminale che si trova nella cartella Applicazioni \> Utility.

Verificate che sul vostro computer sia installato Git scrivendo il seguente comando:

```
git --version
```

Se ricevete un errore, dovete procedere con l'installazione di Git: potete scaricare il pacchetto [andando qui](https://git-scm.com). Se, invece, ricevete un output con su scritto qualcosa simile a _git version 2.23.0_ allora potete procedere con l'installazione di Spleeter.

Per prima cosa andate nella cartella documenti con il comando

```
cd ~/Documents
```

E poi lanciate il seguente comando:

```
git clone https://github.com/deezer/spleeter
```

Attendete la fine del download. Una volta completato dovreste vedere una cartella nominata **spleeter** all'interno della cartella Documenti.

Ora creiamo l'ambiente di sviluppo con il seguente comando:

```
conda env create -f spleeter/conda/spleeter-cpu.yaml
```

E, infine, procediamo con l'attivazione

```
conda activate spleeter-cpu
```

Una volta completate tutte le operazioni, ricordatevi di disattivare l'ambiente con il comando

```
conda deactivate
```

## Utilizzare Spleeter per separare la parte vocale da un brano

All'interno della cartella di Spleeter c'è un file mp3 chiamato _audio\_example.mp3._ Lanciando il seguente comando il file verrà analizzato e verranno create 2 stems: una per la parte vocale e una per quella musicale.

```
spleeter separate -i spleeter/audio_example.mp3 -p spleeter:2stems -o output
```

Dentro la cartella Documenti ora troverete una cartella nominata **output** con, al suo interno, una sottocartella **audio\_example** con i file separati.

Per utilizzare il software su altri brani sarà sufficiente copiare il file .mp3 oppure .wav nella cartella _spleeter_ e lanciare il comando qui sopra assicurandosi di scrivere correttamente il nome del file; vi consiglio di rinominare i brani evitando spazi, lettere accentate, ecc...).

Se volete estrarre 4 o 5 stems utilizzate questo comando:

```
spleeter separate -i spleeter/audio_example.mp3 -p spleeter:4stems -o output
```

```
spleeter separate -i spleeter/audio_example.mp3 -p spleeter:5stems -o output
```

## Esempi audio e limitazioni

Ecco un paio di esempi di divisione in due stems

### Tones and I - Dance Monkey

_Parte vocale_

_Accompagnamento musicale_

### Billie Jean - Michael Jackson

_Parte vocale_

_Accompagnamento musicale_

Come indicato sul sito degli sviluppatori: se intendete utilizzare questo strumento su materiale protetto da copyright, assicuratevi di avere tutte le autorizzazioni del caso.
