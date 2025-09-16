---
lab:
  title: Esplorare Voce nel portale Fonderia Azure AI
---

# Esplorare Voce nel portale Fonderia Azure AI

Il servizio **Voce di Azure AI** trascrive il parlato in testo e il testo in parlato ascoltabile. È possibile usare Voce di Azure AI per creare un'applicazione in grado di trascrivere le note della riunione o generare un testo dalla registrazione dei colloqui.

In questo esercizio, verrà utilizzato Voce di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per trascrivere l'audio usando le esperienze try-it-out predefinite. 

Questo esercizio richiede circa **15** minuti.

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere eventuali suggerimenti o riquadri di avvio rapido che vengono aperti al primo accesso. 

1. Nel browser passare a `https://ai.azure.com/managementCenter/allResources` e selezionare **Crea nuovo**. Scegliere quindi l'opzione per creare una nuova **risorsa di Fonderia Azure AI**.

1. Nella procedura guidata *Crea un progetto*, immettere un nome valido per il progetto.

1. Espandere *Opzioni avanzate* per specificare le impostazioni seguenti per il progetto:
    - **Sottoscrizione**: sottoscrizione di Azure.
    - **Gruppo di risorse**: creare o selezionare un gruppo di risorse
    - **Area**: selezionare una delle seguenti posizioni:
        * Stati Uniti orientali
        * Francia centrale
        * Corea centrale
        * Europa occidentale
        * Stati Uniti occidentali

    Selezionare **Crea**. Attendere la creazione del progetto. L'operazione potrebbe richiedere alcuni minuti.

1. Quando il progetto viene creato, verrà visualizzata una pagina *Panoramica* dei dettagli del progetto.
 
1. Nel menu a sinistra nella schermata selezionare **Playground**.

    >*Nota*: Espandere il menu per leggerne il contenuto facendo clic sull'icona "Espandi" in alto.

1. Nella pagina Playground di Fonderia Azure AI selezionare **Prova il playground Voce**. Il playground Voce è un'interfaccia utente che consente di provare alcune funzionalità di Voce di Azure AI.

## Esplorare il riconoscimento vocale nel playground Voce di Fonderia Azure AI

Ora verrà provato il *riconoscimento vocale* nel playground Voce di Fonderia Azure AI. 

1. Nella pagina *Voce* scorrere verso il basso e selezionare **Trascrizione in tempo reale**.

1. Scaricare **speech.zip** aprendo l'URL `https://aka.ms/mslearn-speech-files` in una nuova scheda del browser. L'uso dell'URL dovrebbe scaricare automaticamente una cartella nel computer. 

1. Passare alla cartella *Download* nel computer, quindi identificare la cartella scaricata. Fare clic con il pulsante destro del mouse sulla cartella scaricata. Selezionare *Estrai tutto*. Selezionare quindi *Estrai* per decomprimerne il contenuto. La cartella decompressa verrà visualizzata sullo schermo. Chiudere la cartella decompressa. Si noti che la cartella decompressa si trova ora anche nella cartella *Download*.    

1. In *Carica file* nel portale Voce di Fonderia Azure AI selezionare **Esplora file**. Spostarsi nella cartella decompressa. Selezionare **WhatAICanDo.m4a** quindi **Apri**.

    ![Ricerca dei file](media/recognize-synthesize-speech/browse-files-speech.png)

1. Il servizio Voce trascrive e visualizza il testo in tempo reale. Se si dispone di audio nel computer, è possibile ascoltare la registrazione mentre il testo viene trascritto.

1. Esaminare l'output. 

    >*Nota*: Per visualizzare l'output completo, potrebbe essere necessario ridurre al minimo il riquadro *Configura*. Per ridurre al minimo, selezionare l'icona a destra dell'intestazione *Configura*.

1. Sotto *Testo* nell'output è possibile visualizzare la trascrizione dell'audio in testo. 

In questo esercizio sono stati provati i servizi Voce di Azure AI nel playground Voce di Fonderia Azure AI. È stata quindi usata la trascrizione in tempo reale per trascrivere una registrazione audio. È stato possibile visualizzare la trascrizione del testo generata durante la riproduzione del file audio.

## Eseguire la pulizia

Se non si prevede di eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Voce. Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Voce](https://azure.microsoft.com/services/cognitive-services/speech-services).
