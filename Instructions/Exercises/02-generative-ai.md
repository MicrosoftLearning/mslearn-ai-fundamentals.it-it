---
lab:
  title: Esplorare l'IA generativa nel portale Fonderia Azure AI
---

# Esplorare l'IA generativa nel portale di Fonderia Azure AI

L'IA generativa descrive una categoria di funzionalità all'interno dell'intelligenza artificiale che creano contenuto. Le persone interagiscono spesso con l'IA generativa incorporata in applicazioni per chat. In questo esercizio, verrà messa alla prova l'IA generativa nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti. 

Questo esercizio richiede circa **20** minuti.

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page del Portale Fonderia Azure AI.](./media/ai-foundry-portal.png)

1. Nella sezione **Esplorare modelli e funzionalità** cercare `gpt-4o`. Nei risultati della ricerca selezionare quindi il modello **gpt-4o** per visualizzarne i dettagli.

    ![Screenshot della pagina dei dettagli di gpt-4o.](./media/gpt-4o-details.png)

1. Selezionare **Usa questo modello**.

1. Nella procedura guidata **Crea un progetto**, immettere un nome valido per il progetto. Espandere quindi **Opzioni avanzate** per specificare le impostazioni seguenti per il progetto:
    - **Risorsa di Fonderia Azure AI**: *Immettere un nome valido per la risorsa di Fonderia AI.*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Area**: Selezionare una delle aree **consigliate per Fonderia AI** \*
    
    \**Le distribuzioni di modelli sono limitate dalle quote a livello di area. Se si seleziona un'area in cui è disponibile una quota insufficiente, potrebbe essere necessario selezionare un'area alternativa per una nuova risorsa in un secondo momento.*

1. Selezionare **Crea**. Attendere la creazione del progetto. L'operazione potrebbe richiedere alcuni minuti.

    Se viene richiesto di distribuire il modello in un'area diversa, usare le impostazioni predefinite per farlo.

## Esplorare l'IA generativa nel playground della chat di Fonderia Azure AI

1. Dopo aver creato il progetto, nel riquadro attività a sinistra selezionare **Playground**. 

    >*Suggerimento*: Se necessario, espandere il menu per leggerne il contenuto facendo clic sull'icona "Espandi" in alto.

1. Nella pagina Playground di Fonderia Azure AI selezionare **Prova il playground della chat**. Chiudere eventuali suggerimenti o riquadri di avvio rapido aperti.

    Il Playground della chat è un'interfaccia utente che consente di provare a creare un'applicazione di chat con modelli diversi di IA generativa.

    ![Screenshot della pagina dei dettagli di gpt-4o.](./media/chat-playground.png)

    >*Suggerimento*: Se non viene visualizzato il riquadro **Configurazione**, espandere le dimensioni della finestra nella schermata del playground della chat.  

1. Per usare il playground della chat, è necessario associarlo a un modello distribuito. Nel riquadro **Configurazione** del playground della chat assicurarsi che sia selezionato il modello **gpt-4o** distribuito in precedenza. 

    >*Nota*: È necessario selezionare **Applica modifiche** ogni volta che si apportano modifiche nel riquadro **Configurazione**.

1. Nel riquadro **Configurazione** prendere nota delle istruzioni e del contesto predefiniti per il modello, che dovrebbero essere simili ai seguenti:

    `You are an AI assistant that helps people find information.`

    Questi tipi di istruzioni vengono comunemente definite *richieste di sistema* e vengono usate per fornire indicazioni e vincoli per le risposte del modello.

1. Esaminare il riquadro *Cronologia chat*, che contiene alcune richieste di esempio che consentono di iniziare a lavorare e una casella di ricerca per immettere richieste personalizzate. 

1. Provare a generare una risposta usando un prompt con un obiettivo specifico. Nella casella di chat, immettere il prompt seguente:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Esaminare la risposta. Occorre notare che la risposta specifica ricevuta può variare in base alla natura dell'IA generativa.

1. Vediamo un altro prompt. Immettere gli elementi seguenti:

    ```prompt
    Where's a good location in the city to stay?
    ```

1. Esaminare la risposta, che dovrebbe fornire alcuni posti dove alloggiare a Parigi. Si noti che la sessione di chat mantiene il contesto dalle richieste precedenti, quindi sa che "la città" in questione è Parigi.

1. Eseguire l'iterazione in base alle richieste e alle risposte precedenti per perfezionare il risultato. Immettere il prompt seguente:

    ```prompt
    Can you give me more information about dining options near the first location?
    ```

1. Esaminare la risposta, che dovrebbe fornire opzioni di pranzo vicino a una posizione dalla risposta precedente. 

1. Ora, verrà fornita un'origine per motivare la risposta in un ambito specifico di informazioni Immettere gli elementi seguenti: 

    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Esaminare la risposta, che dovrebbe fornire informazioni in base al sito Web fornito. 

1. Provare ora ad aggiungere il contesto per aumentare al massimo la pertinenza della risposta. Immettere il prompt seguente: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Esaminare la risposta e il ragionamento per la risposta.  

1. Tentare ora di impostare aspettative chiare per la risposta. Immettere il prompt seguente:

    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Esaminare la risposta, che dovrebbe fornire un elenco numerato di attrazioni da vedere a Parigi.

## Visualizzare il codice client

1. Nella parte superiore della pagina del playground della chat selezionare **Visualizza codice**.
1. Esaminare gli esempi di codice forniti per più linguaggi di programmazione, SDK e opzioni di autenticazione.

    Questi esempi di codice consentono agli sviluppatori di iniziare rapidamente a creare applicazioni client che chattano con il modello distribuito.

1. Chiudere la finestra del codice di esempio.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare **Elimina gruppo di risorse** e **immettere il nome del gruppo di risorse** per confermare. Il gruppo di risorse viene quindi eliminato.
