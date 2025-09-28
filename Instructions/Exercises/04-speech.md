---
lab:
  title: Esplorare Voce nel portale Fonderia Azure AI
---

# Esplorare Voce nel portale Fonderia Azure AI

Voce di Azure AI trascrive il parlato in testo e trasforma il testo in parlato ascoltabile. È possibile usare Voce di Azure AI per creare un'applicazione in grado di trascrivere appunti di riunioni o generare un testo dalla registrazione di colloqui oppure per supportare un assistente IA interattivo in grado di rispondere a comandi e query vocali.

In questo esercizio si userà Voce di Azure AI nel Portale Fonderia Azure AI, la piattaforma Microsoft per la creazione di applicazioni intelligenti, per esplorare le principali funzionalità di Voce di Azure AI. 

Questo esercizio richiede circa **15** minuti.

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page del Portale Fonderia Azure AI.](./media/ai-foundry-portal.png)

1. Scorrere fino alla fine della pagina e selezionare il riquadro **Esplora i Servizi di Azure AI**.

    ![Screenshot del riquadro Esplora i Servizi di Azure AI.](./media/ai-services.png)

1. Nella pagina Servizi di Azure AI selezionare il riquadro **Voce**.

    ![Screenshot del riquadro Voce.](./media/speech.png)

1. Nella pagina **Voce** selezionare **Vai al playground Voce**. Quindi, quando richiesto, creare un nuovo progetto con le impostazioni seguenti:
    - **Nome progetto**: *Immettere un nome valido per il progetto.*
    - **Impostazioni avanzate**:
        - **Sottoscrizione**: *la sottoscrizione di Azure usata*
        - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
        - **Area**: *Selezionare una delle aree **consigliate di Fonderia AI***
        - **Fonderia AI o Azure OpenAI** *Creare una nuova risorsa di Fonderia Azure AI con un nome valido*

1. Selezionare **Crea**. Attendere la creazione del progetto. L'operazione potrebbe richiedere alcuni minuti.

1. Al termine della creazione del progetto, si verrà indirizzati al playground **Voce** (in caso contrario, nel riquadro attività a sinistra selezionare **Playground** e aprire il playground Voce da lì).

    Il playground Voce è un'interfaccia utente che consente di provare alcune funzionalità di Voce di Azure AI.  

## Esplorare il riconoscimento vocale nel playground Voce di Fonderia Azure AI

Ora verrà provato il *riconoscimento vocale* nel playground Voce di Fonderia Azure AI.

1. In una nuova scheda del browser scaricare **[speech.zip](https://aka.ms/mslearn-speech-files)** da `https://aka.ms/mslearn-speech-files` in una nuova scheda del browser. Dopo aver scaricato il file, estrarlo in una cartella locale. 

1. Tornare alla pagina Voce del Portale Fonderia Azure AI e nella scheda **Riconoscimento vocale** selezionare **Trascrizione in tempo reale**.

1. In **Carica file** selezionare **Sfoglia file** e caricare **WhatAICanDo.m4a** dalla cartella scaricata ed estratta.

    Il servizio Voce trascrive e visualizza il testo in tempo reale. Se si dispone di audio nel computer, è possibile ascoltare la registrazione mentre il testo viene trascritto.

    ![Screenshot dell'interfaccia di Trascrizione in tempo reale nel playground Voce.](./media/real-time-transcription.png)

1. Esaminare l'output. 

    >*Suggerimento*: Per visualizzare l'output completo, potrebbe essere necessario ridurre al minimo il riquadro *Configura*. Per ridurre al minimo, selezionare l'icona a destra dell'intestazione *Configura*.

    Sotto **Testo** nell'output è possibile visualizzare la trascrizione dell'audio in testo.

## Esplorare la sintesi vocale nel playground Voce di Fonderia Azure AI

Vediamo ora come Voce di Azure AI può generare un parlato udibile da un testo.

1. Nel playground Voce selezionare la scheda **Sintesi vocale** e assicurarsi che sia selezionato **Raccolta voce**.
1. Visualizzare le voci disponibili e selezionarne una (ad esempio *Ava Multilingual*).
1. Nel riquadro **Dettagli voce** selezionare la scheda **Prova**. Immettere quindi un testo (ad esempio, `The rain in Spain stays mainly in the plain`) e usare il pulsante **Riproduci** per sintetizzare il parlato dal testo.

    ![Screenshot dell'interfaccia di Raccolta voce nel playground Voce.](./media/voice-gallery.png)

    Il testo viene pronunciato usando la voce selezionata. È possibile provare altre voci per confrontare l'output parlato.

## Eseguire la pulizia

Se non si prevede di eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare **Elimina gruppo di risorse** e **immettere il nome del gruppo di risorse** per confermare. Il gruppo di risorse viene quindi eliminato.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Voce. Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Voce](https://azure.microsoft.com/services/cognitive-services/speech-services).
