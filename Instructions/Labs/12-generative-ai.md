---
lab:
  title: Esplorare l'IA generativa nel portale Fonderia Azure AI
---

# Esplorare l'IA generativa nel portale di Fonderia Azure AI

L'IA generativa descrive una categoria di funzionalità all'interno dell'intelligenza artificiale che creano contenuto. Le persone interagiscono in genere con l'intelligenza artificiale generativa incorporata in applicazioni per chat. In questo esercizio, verrà messa alla prova l'IA generativa nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti. 

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

## Esplorare l'IA generativa nel playground della chat di Fonderia Azure AI

1. Nella pagina Playground di Fonderia Azure AI selezionare **Prova il playground della chat**. Il Playground della chat è un'interfaccia utente che consente di provare a creare un'applicazione di chat con modelli diversi di IA generativa.  

1. Per usare il playground della chat, è necessario associarlo a un modello distribuito. Nel playground della chat, selezionare **Crea una distribuzione**. Cercare e selezionare **gpt-4**. 

1. Nella finestra *Distribuisci modello* mantenere la denominazione e la selezione predefinite e selezionare **Distribuisci**. La distribuzione del modello potrebbe richiedere alcuni minuti. È possibile controllare lo stato della distribuzione selezionando *Modelli ed endpoint* nel menu a sinistra in *Asset personali*.
1. Nel playground della chat è possibile usare il modello distribuito quando viene visualizzato nel menu di selezione *Distribuzione*. Assicurarsi che il modello distribuito sia selezionato. Importante, è necessario selezionare **Applica modifiche** dopo aver apportato le modifiche all'*Installazione*. 

1. Considerare i modi seguenti per migliorare le risposte di un assistente di ia generativa:
    - Iniziare con un obiettivo specifico per l'operazione che si vuole che venga eseguita dall'assistente
    - Eseguire l'iterazione in base alle richieste e alle risposte precedenti per perfezionare il risultato
    - Fornire un'origine per radicare la risposta in un ambito specifico di informazioni
    - Aggiungere contesto per ottimizzare l'adeguatezza e la pertinenza della risposta
    - Impostare aspettative chiare per la risposta

1. Provare a generare una risposta usando un prompt con un obiettivo specifico. Nella casella di chat, immettere il prompt seguente:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Rivedere la risposta. **Nota**: la risposta specifica ricevuta può variare in base alla natura dell'IA generativa.
 
1. Vediamo un altro prompt. Immetti gli elementi seguenti:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Esaminare la risposta, che dovrebbe fornire alcuni posti dove alloggiare a Parigi.

1. Eseguire l'iterazione in base alle richieste e alle risposte precedenti per perfezionare il risultato. Immettere la richiesta seguente:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Esaminare la risposta, che dovrebbe fornire opzioni di pranzo vicino a una posizione dalla risposta precedente. 

1. Ora, verrà fornita un'origine per motivare la risposta in un ambito specifico di informazioni Immetti gli elementi seguenti: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Esaminare la risposta, che dovrebbe fornire informazioni in base al sito Web fornito. 

1. Provare ora ad aggiungere il contesto per aumentare al massimo la pertinenza della risposta. Immettere la richiesta seguente: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Esaminare la risposta e il ragionamento per la risposta.  

1. Tentare ora di impostare aspettative chiare per la risposta. Immettere la richiesta seguente:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Esaminare la risposta, che dovrebbe fornire un elenco numerato di attrazioni da vedere a Parigi.

1. Al termine, è possibile chiudere la finestra del browser.
