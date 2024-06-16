---
lab:
  title: Esplorare Speech Studio
---

# Esplorare Speech Studio

Il servizio **Voce di Azure AI** trascrive il parlato in testo e il testo in parlato ascoltabile. È possibile usare Voce di Azure AI per creare un'applicazione in grado di trascrivere le note della riunione o generare un testo dalla registrazione dei colloqui.

In questo esercizio, si proveranno le funzionalità di Voce di Azure AI con Azure AI Speech Studio. 

## Creare una risorsa per *Voce di Azure AI*

È possibile usare il servizio Voce creando una risorsa **Voce** o una risorsa **Servizi di Azure AI**.

In questo esercizio, si creerà una risorsa di Voce di Azure AI, a meno che non si disponga già di una risorsa da usare.

1. In un'altra scheda del browser, aprire [Azure AI Speech Studio](https://speech.microsoft.com/), accedendo con l’account Microsoft.

1. Selezionare **Impostazioni** quindi **Crea una risorsa.** Eseguire la configurazione con le seguenti impostazioni:
    - **Nome della nuova risorsa**: *Immetti un nome univoco*.
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Area**: *Selezionare un'[area supportata](https://learn.microsoft.com/azure/ai-services/speech-service/regions)*.
    - **Piano tariffario**: *FO gratuito (se disponibile, in caso contrario selezionare S0 Standard).*
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
1. Selezionare **Crea risorsa**. Attendere che la risorsa sia stata creata, quindi selezionare **Usa risorsa**. Viene visualizzata la pagina Introduzione al riconoscimento vocale.

## Esplorare il riconoscimento vocale in Speech Studio

1. Selezionare [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) per scaricare **speech.zip**. Apri la cartella . 

1. Nella pagina Introduzione al riconoscimento vocale, in *Riconoscimento vocale* individuare *Conversione della voce in testo scritto in tempo reale*. Selezionare **Prova la conversione della voce in testo scritto in tempo reale**.

    ![Introduzione al riconoscimento vocale](media/recognize-synthesize-speech/try-out-speech-to-text.png)

1. In *Scegli file audio*, selezionare **Sfoglia file** e passare alla cartella in cui è stato salvato il file. Selezionare **WhatAICanDo.m4a** quindi **Apri**.

    ![Ricerca dei file](media/recognize-synthesize-speech/browse-files-speech.png)

1. Il servizio Voce trascrive e visualizza il testo in tempo reale. Se si dispone di audio nel computer, è possibile ascoltare la registrazione mentre il testo viene trascritto.
1. Esaminare l'output, che dovrebbe essere stato riconosciuto e trascritto correttamente in testo.

    > **Nota** Se viene visualizzato un messaggio di errore, attendere alcuni minuti prima di riprovare. La risorsa Voce per il primo uso richiede un po' di tempo.

In questo esercizio è stata creata una risorsa di Voce di Azure AI in Speech Studio. È stato quindi usato il servizio di conversione della voce in testo scritto in tempo reale per trascrivere una registrazione audio. È stato possibile visualizzare la trascrizione del testo generata durante la riproduzione del file audio.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Voce. Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Voce](https://azure.microsoft.com/services/cognitive-services/speech-services).
