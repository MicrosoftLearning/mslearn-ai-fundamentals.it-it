---
lab:
  title: Esplorare le funzionalità del servizio Voce nel portale Fonderia di Azure AI
---

# Esplorare le funzionalità del servizio Voce nel portale Fonderia di Azure AI

Il servizio **Voce di Azure AI** trascrive il parlato in testo e il testo in parlato ascoltabile. È possibile usare Voce di Azure AI per creare un'applicazione in grado di trascrivere le note della riunione o generare un testo dalla registrazione dei colloqui.

In questo esercizio, verrà utilizzato Voce di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per trascrivere l'audio usando le esperienze try-it-out predefinite. 

## Creare un progetto nel portale Fonderia Azure AI

Per iniziare, creare un progetto Fonderia Azure AI.

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page di Fonderia Azure AI con l'opzione Crea un agente selezionata.](./media/azure-ai-foundry-home-page.png)

1. Nella home page, selezionare **+ Crea un agente**.

1. Nella procedura guidata **Crea un agente**, immettere un nome valido per il progetto. 

1. Selezionare **Opzioni avanzate** e specificare le impostazioni seguenti:
    - **Risorsa di Fonderia Azure AI**: *mantenere il nome predefinito*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Area**: selezionare una delle seguenti posizioni:
        * Stati Uniti orientali
        * Francia centrale
        * Corea centrale
        * Europa occidentale
        * Stati Uniti occidentali

1. Selezionare **Crea** e rivedere la configurazione. Attendere il completamento del processo di configurazione.

    >**Nota**: se viene visualizzato un errore di autorizzazione, selezionare il pulsante **Correggi** per aggiungere le autorizzazioni appropriate per continuare.

1. Quando il progetto viene creato, per impostazione predefinita viene visualizzato il playground Agenti nel portale Fonderia Azure AI, simile al seguente:

    ![Screenshot dei dettagli di un progetto di Azure AI nel portale Fonderia di Azure AI.](./media/ai-foundry-project-2.png)
 
1. Nel menu a sinistra nella schermata selezionare **Playground**.

1. Nella pagina *Playground* selezionare il riquadro **playground Voce** per provare alcune funzionalità di Voce di Azure AI.

## Esplorare il riconoscimento vocale nel playground Voce di Fonderia Azure AI

Ora verrà provato il *riconoscimento vocale* nel playground Voce di Fonderia Azure AI. 

1. Nella pagina *Voce* scorrere verso il basso e selezionare **Trascrizione in tempo reale** in *Prova funzionalità di riconoscimento vocale*. Si verrà portati a *Playground Voce*. 

1. Selezionare [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) per scaricare **speech.zip**. Apri la cartella . 

1. In *Carica file*, selezionare **Sfoglia file** e passare alla cartella in cui è stato salvato il file. Selezionare **WhatAICanDo.m4a** quindi **Apri**.

    ![Ricerca dei file](media/recognize-synthesize-speech/browse-files-speech.png)

1. Il servizio Voce trascrive e visualizza il testo in tempo reale. Se si dispone di audio nel computer, è possibile ascoltare la registrazione mentre il testo viene trascritto.

1. Esaminare l'output, che dovrebbe essere stato riconosciuto e trascritto correttamente in testo.

In questo esercizio sono stati provati i servizi Voce di Azure AI nel playground Voce di Fonderia Azure AI. È stata quindi usata la trascrizione in tempo reale per trascrivere una registrazione audio. È stato possibile visualizzare la trascrizione del testo generata durante la riproduzione del file audio.

## Eseguire la pulizia

Se non si prevede di eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Voce. Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Voce](https://azure.microsoft.com/services/cognitive-services/speech-services).
