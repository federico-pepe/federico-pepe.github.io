---
layout: post
title: "Ottimizzare le performance di Ableton Live 11"
date: 2021-06-20 15:28:06 +0000
categories: ["Ableton"]
tags: ["Ableton Live 11", "CPU", "Live 11", "Performance"]
description: "Guida pratica per ottimizzare Ableton Live 11: buffer size, sample rate, bit depth, freeze delle tracce, SSD, indicizzazione e tutti i consigli per evitare audio dropouts."
---

Ottimizzare le performance di Ableton Live 11 è uno step importantissimo per evitare che il computer vada in overload o si creino delle interruzioni dell'audio. Dato che molti utenti lamentano un peggioramento delle prestazioni rispetto alle versioni precedenti, ho pensato potesse essere utile condividere alcuni suggerimenti per aiutare a migliorare le prestazioni di Live 11.

## Requisiti minimi

Per prima cosa assicuratevi che il vostro computer, Mac o PC, rispetti i requisiti minimi indicati sul sito di Ableton.

### macOS

- OS X 10.13 o successivio&nbsp;[(maggiori informazioni su macOS Big Sur)](https://help.ableton.com/hc/articles/115001261150)
- processore Intel® Core™ i5&nbsp;[(maggiori informazioni sui Mac con chip M1)](https://help.ableton.com/hc/articles/360019434680)
- 8 GB RAM
- risoluzione display: 1280x800
- scheda audio compatibile con Core Audio

### Windows

- Windows 10 (Build 1909 o successiva)
- processore Intel® Core™ i5 o AMD multi-core.
- 8 GB RAM
- risoluzione display 1366x768
- scheda audio compatibile con i driver ASIO per supportare Ableton Link (consigliato anche per ottimizzare le performance audio)

A prescindere dalla piattaforma è consigliabile avere almeno 3 GB di spazio libero sull'hard disk (consigliati 8 GB) per l'installazione e fino a 76 GB per installare eventuali contenuti aggiuntivi.

### Verifica degli aggiornamenti

Tra i passaggi preliminari verificate che Ableton Live sia aggiornato all'ultima versione disponibile: potete farlo dal menu **Aiuto \> Controlla aggiornamenti**. Controllate, inoltre, che i driver della vostra scheda audio siano anch'essi aggiornati all'ultima versione.

Se siete su Windows assicuratevi che i driver della vostra scheda grafica siano aggiornati e che, nelle preferenze del consumo di energia, sia impostato "High Performance". Per una guida dettagliata (in inglese) di come ottimizzare il vostro computer per la produzione audio potete dare un'occhiata a [questo lungo articolo](https://aka.ms/Win10AudioTweakGuide).

Infine verificate che eventuali plug-in aggiuntivi che avete installato sul vostro computer siano aggiornati alla loro ultima versione.

## Meter CPU

[![Uno screenshot che mostra il meter della CPU in Live 11](/assets/uploads/2021/06/Ableton-Live-11-Meter-CPU.png)](/assets/uploads/2021/06/Ableton-Live-11-Meter-CPU.png)
_Il nuovo meter della CPU in Live 11_

Una delle novità di Live 11 è il miglioramento del meter delle prestazioni. In questo indicatore troviamo **esclusivamente il carico del processamento dell'audio**. L'impatto di altri processi come, ad esempio, l'interfaccia grafica di Live o il rendering grafico delle finestre di plug-in esterni non sono compresi in questa indicazione.

Per avere un'idea chiara dell'impatto che Live ha sul vostro sistema è necessario aprire **Monitoraggio Attività** su Mac o il **Task Manager** su Windows.

Nel caso in cui Live consumi più risorse rispetto a quelle a disposizione, si accenderà l'indicatore accanto alla percentuale di utilizzo e verrà visualizzato il testo "CPU".

![Screenshot che mostra l'indicatore CPU attivo su Live 11](/assets/uploads/2021/06/Live-11-sovraccarico-CPU.png)

Quando succede, è possibile sentire dei problemi di audio come crack, pop e silenzi. Questi problemi vengono chiamati _audio dropouts_.

Come indicato nel primo screenshot, è possibile **disattivare l'indicazione di sovraccarico della CPU** ed è consigliabile impostare il misuratore affinché mostri il valore medio e non quello corrente.

## Impatto sulle prestazioni delle singole tracce

In Live 11 è possibile attivare l'indicazione di impatto delle prestazioni della singole tracce cliccando sul piccolo tasto "C" in basso a destra del canale master.

[![Uno screenshot del mixer di Live 11 con selezionato l'indicatore dell'impatto delle prestazioni delle singole tracce.](/assets/uploads/2021/06/Impatto-delle-prestazioni-Live-11-1024x152.png)](/assets/uploads/2021/06/Impatto-delle-prestazioni-Live-11.png)
_Mixer di Live 11 con attivato l'indicatore delle prestazioni delle singole tracce_

Una volta selezionato, si attiverà sotto ciascun canale un indicatore che segnala l'impatto delle singole tracce sul carico totale. Nello screenshot qui sopra la traccia 24 è quella che sta consumando il maggior numero di risorse.

## Meter utilizzo disco

Lo stesso indicatore che ci segnala un eventuale sovraccarico della CPU può accendersi e mostrare la scritta "Disk". In questo caso ci segnala che Ableton non è stato in grado di leggere in tempo i file dall'hard disk.

Per evitare questo genere di problemi è **consigliabile utilizzare un disco SSD interno** in cui salvare tutti i file. Generalmente gli hard disk meccanici e gli hard disk esterni sono più lenti, soprattuto se la connessione è inferiore a USB 3.0

Come regola generale, lo spazio libero sull'hard disk dovrebbe essere sempre almeno il 10% dello spazio totale. Resta sottinteso che più spazio abbiamo a disposizione, meglio è.

## Ottimizzare il buffer size

È importante conoscere bene alcune voci presenti all'interno del pannello delle preferenze di Ableton Live per ottimizzare al meglio le prestazioni.

Uno dei parametri più importanti è la **dimensione del Buffer**. Una delle cause principali degli _audio dropouts_ è un'impostazione errata di questo parametro. Impostare un buffer size più grande è una soluzione per evitare interruzioni dell'audio.

[![Screenshot che mostra il pannello delle preferenze di Ableton Live 11](/assets/uploads/2021/06/Pannello-preferenze-audio-Live-11-934x1024.png)](/assets/uploads/2021/06/Pannello-preferenze-audio-Live-11.png)

Attenzione, però: **aumentare il livello del buffer introduce latenza**. Maggiore sarà il valore impostato, più alto sarà il ritardo che percepirete quando starete monitorando o registrando una traccia audio o MIDI.

È buona regola impostare la dimensione del buffer in base all'attività che stiamo svolgendo: quando registriamo o stiamo suonando scegliamo valori più piccoli mentre quando siamo mixando o producendo possiamo impostare valori più elevati.

Per esperienza personale posso dirvi che il range ottimale è tra 128 e 1024 samples ma impostatelo sempre ad orecchio trovando il valore ottimale tra la latenza ed eventuali overload di sistema.

## Impostare la frequenza di campionamento

La frequenza di campionamento è un altro parametro che può impattare sul consumo generale della CPU. Sempre nello stesso pannello delle preferenze possiamo impostare questo valore.

Anche in questo caso, più alta sarà la frequenza di campionamento, maggiore il consumo delle risorse. È importante sottolineare che **utilizzare un sample rate più alto non rende necessariamente migliore il nostro audio**.

Se abbiamo un campione registrato a 48kHz e chiediamo a Live di riprodurlo a 96k non avremmo alcun miglioramento della qualità ma, viceversa, il nostro computer dovrà impiegare più risorse per convertire l'audio.

Personalmente consiglio di lasciare il sample rate impostato a 44100.

## Scegliere correttamente la Bit Depth

Il bit depth indica la quantità potenziali di informazione audio contenuta in un sample digitale. Registrare l'audio a una risoluzione di bit più alta permette di avere un range dinamico maggiore e più dettagli. Purtroppo, però, risoluzioni più elevate implicano file di dimensioni più grande e, quindi, maggiore spazio occupato sull'hard disk.

Leggere un file a 32 bit richiede una maggiore quantità di banda per il trasferimento dei dati rispetto a un file a 16 bit.

![Screenshot che mostra il dettaglio di una clip audio in Live 11](/assets/uploads/2021/06/Pannello-dettaglio-clip-audio.png)
_Dettaglio di una clip audio selezionata. L'audio è stato registrato a 44.1 kHz e 24 bit_

Selezionando una clip audio è possibile notare l'indicazione sia della frequenza di campionamento che la profondità di bit con cui quella clip è stata registrata.

Per cambiare il bit depth di default è necessario aprire il pannello delle preferenze e cliccare sulla tab _Record Warp Launch_.

È consigliabile selezionare un valore di **24 bit** ed evitare di avere, all'interno di uno stesso progetto, file con risoluzioni differenti. Per convertire un file alla frequenza di campionamento e alla profondità di bit del vostro progetto è possibile fare un freeze della traccia o consolidare la clip audio.

Se state mantenendo inalterata la tonalità delle vostre clip audio è possibile disattivare "Alta Qualità" nelle preferenze audio di default o cliccando sul tasto HiQ nelle singole clip per disattivare questa feature che prevede un maggiore consumo della CPU.

## Ottimizzare l'indexing dei file

Quando apriamo Live per la prima volta o aggiungiamo una cartella nella sezione _Places_ del browser Live inizierà l'indicizzazione dei contenuti: un processo esterno a Live che possiamo monitorare nel task manager che, però, determina un maggiore utilizzo della CPU.

[![Dettaglio del browser di Ableton Live 11. Un cerchio accanto alla scritta Places indica che è in atto l'indicizzazione della libreria.](/assets/uploads/2021/06/Ableton-Live-11-Indexing-Library-Contents.png)](/assets/uploads/2021/06/Ableton-Live-11-Indexing-Library-Contents.png)
_Il cerchio accanto a "Places" indica che la libreria sta procedendo con l'indicizzazione_

Un consiglio per ottimizzare e velocizzare questo processo è quello di evitare di usare cartelle nel cloud come, ad esempio, su Google Drive o Dropbox per salvare i vostri file perché questo rallenta l'indicizzazione.

Evitate anche di aggiungere cartelle molto grandi (come Desktop o Download) oppure l'intero hard disk.

## Ultimi consigli

Seguendo tutti questi consigli dovreste essere in grado di ottimizzare il vostro computer per utilizzare Live 11 al meglio. Rimangono solo un paio di consigli:

1. Se su una traccia avete caricato uno strumento virtuale molto pensante o una catena di tanti effetti diversi potrebbe essere il caso di _freezare_ temporaneamente la traccia per ridurre il carico del processamento audio in real-time. Questa funzione è temporanea e permette in qualsiasi momento di fare _unfreeze_.
2. Utilizza gli effetti in send / return invece che aprire più istanze dello stesso effetto su tracce separate.
3. Per evitare l'overload del disco puoi caricare alcuni file sulla RAM premendo l'apposito pulsante. Il computer riesce ad accedere più facilmente e più velocemente ai dati presenti in memoria rispetto a quelli sull'hard disk.
4. L'utilizzo del Warp con l'algoritmo Complex o Complex Pro aumenta il carico della CPU. Come suggerito in precedenza, una volta trovata l'impostazione giusta, è consigliabile consolidare l'audio.
5. Disabilità input e output inutilizzati della tua scheda audio.
6. Assicurati di utilizzare un unico formato di plug-in esterni in uno stesso progetto. Evita di aprire contemporaneamente lo stesso plug-in in formato AU, VST e VST3.
