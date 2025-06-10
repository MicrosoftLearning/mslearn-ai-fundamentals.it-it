---
lab:
  title: Esplorare l'IA generativa nel portale Fonderia Azure AI
---

# Esplorare l'IA generativa nel portale di Fonderia Azure AI

L'IA generativa descrive una categoria di funzionalità all'interno dell'intelligenza artificiale che creano contenuto. Le persone interagiscono in genere con l'intelligenza artificiale generativa incorporata in applicazioni per chat. In questo esercizio, verrà messa alla prova l'IA generativa nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti. 

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere eventuali suggerimenti o riquadri di avvio rapido che vengono aperti al primo accesso. 

1. Nel browser, passare a `https://ai.azure.com/managementCenter/allResources` e selezionare **Crea**. Scegliere quindi l'opzione per creare una nuova *risorsa Fonderia Azure AI*.

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

    Attendere la creazione del progetto o dell'hub.

1. Quando il progetto viene creato, verrà visualizzata una pagina *Panoramica* dei dettagli del progetto.

1. Nel menu a sinistra nella schermata selezionare **Playground**.

## Esplorare l'IA generativa nel playground della chat di Fonderia Azure AI

1. Nella pagina Playground di Fonderia Azure AI selezionare **Prova il playground della chat**. Il Playground della chat è un'interfaccia utente che consente di provare a creare un'applicazione di chat con modelli diversi di IA generativa.  

1. Per usare il playground della chat, è necessario associarlo a un modello distribuito. Nel playground Chat, è necessario avere selezionato **gpt-4o**. Se non vengono visualizzate distribuzioni, è necessario selezionare **+ Crea una distribuzione**, cercare **gpt-4o** e quindi selezionare **Conferma** e infine **Distribuisci**.

1. Nel playground della chat è possibile usare il modello distribuito quando viene visualizzato nel menu di selezione *Distribuzione*. Importante, è necessario selezionare **Applica modifiche** dopo aver apportato le modifiche all'*Installazione*. 

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

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.

1. Selezionare la risorsa e poi **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.
