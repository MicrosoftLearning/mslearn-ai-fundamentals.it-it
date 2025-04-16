---
lab:
  title: Esplorare le funzionalità del servizio Voce nel portale Fonderia di Azure AI
---

# Esplorare le funzionalità del servizio Voce nel portale Fonderia di Azure AI

Il servizio **Voce di Azure AI** trascrive il parlato in testo e il testo in parlato ascoltabile. È possibile usare Voce di Azure AI per creare un'applicazione in grado di trascrivere le note della riunione o generare un testo dalla registrazione dei colloqui.

In questo esercizio, verrà utilizzato Voce di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per trascrivere l'audio usando le esperienze try-it-out predefinite. 

## Creare un progetto nel portale Fonderia Azure AI

1. In una scheda del browser passare a [Fonderia Azure AI](https://ai.azure.com?azure-portal=true).

1. Accedi con il tuo account. 

1. Nella home page del portale Fonderia Azure AI, selezionare **Crea un progetto**. In Fonderia Azure AI, i progetti sono contenitori che consentono di organizzare il lavoro.  

    ![Screenshot della home page di Fonderia Azure AI con Crea un progetto selezionato.](./media/azure-ai-foundry-home-page.png)

1. Nel riquadro *Crea un progetto* verrà visualizzato un nome di progetto generato, che è possibile mantenere così com'è. A seconda che in passato sia stato creato un hub, verrà visualizzato un elenco di *nuove* risorse di Azure da creare o un elenco a discesa di hub esistenti. Se viene visualizzato l'elenco a discesa degli hub esistenti, selezionare *Crea nuovo hub*, creare un nome univoco per l'hub e selezionare *Avanti*.  
 
    ![Screenshot del riquadro Crea un progetto con nomi generati automaticamente per hub e progetto.](./media/azure-ai-foundry-create-project.png)

> **Importante**: per completare il resto del lab, è necessario eseguire il provisioning di una risorsa Servizi di Azure AI in una posizione specifica.

1. Nello stesso riquadro *Crea un progetto* selezionare **Personalizza** e una delle **Posizioni** seguenti: Stati Uniti orientali, Francia centrale, Corea centrale, Europa occidentale o Stati Uniti occidentali per completare il resto del lab. Quindi, selezionare **Crea**. 

1. Prendere nota delle risorse create: 
- Servizi di Azure AI
- Hub di Azure per intelligenza artificiale
- Progetto Azure per intelligenza artificiale
- Account di archiviazione
- Key vault
- Gruppo di risorse  
 
1. Dopo aver creato le risorse, verrà visualizzata la pagina *Panoramica* del progetto. Nel menu a sinistra nella schermata selezionare **Servizi di intelligenza artificiale**.
 
    ![Screenshot del menu a sinistra nella schermata del progetto con Servizi di intelligenza artificiale selezionato.](./media/azure-ai-foundry-ai-services.png)  

1. Nella pagina *Servizi di intelligenza artificiale* selezionare il riquadro *Voce* per provare le funzionalità Voce di Azure AI.

    ![Screenshot del riquadro Voce selezionato nella pagina Servizi di intelligenza artificiale.](./media/speech-tile.png)

## Esplorare il riconoscimento vocale nel playground Voce di Fonderia Azure AI

Ora verrà provato il *riconoscimento vocale in tempo reale* nel playground Voce di Fonderia Azure AI. 

1. Nella pagina *Voce* scorrere verso il basso e selezionare **Riconoscimento vocale in tempo reale** in *Prova funzionalità di riconoscimento vocale*. Si verrà portati a *Playground Voce*. 

1. Selezionare [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) per scaricare **speech.zip**. Apri la cartella . 

1. In *Carica file*, selezionare **Sfoglia file** e passare alla cartella in cui è stato salvato il file. Selezionare **WhatAICanDo.m4a** quindi **Apri**.

    ![Ricerca dei file](media/recognize-synthesize-speech/browse-files-speech.png)

1. Il servizio Voce trascrive e visualizza il testo in tempo reale. Se si dispone di audio nel computer, è possibile ascoltare la registrazione mentre il testo viene trascritto.

1. Esaminare l'output, che dovrebbe essere stato riconosciuto e trascritto correttamente in testo.

In questo esercizio sono stati provati i servizi Voce di Azure AI nel playground Voce di Fonderia Azure AI. È stato quindi usato il servizio di conversione della voce in testo scritto in tempo reale per trascrivere una registrazione audio. È stato possibile visualizzare la trascrizione del testo generata durante la riproduzione del file audio.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Voce. Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Voce](https://azure.microsoft.com/services/cognitive-services/speech-services).
