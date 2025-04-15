---
lab:
  title: Esplorare l'IA generativa nel portale Fonderia Azure AI
---

# Esplorare l'IA generativa nel portale Fonderia Azure AI

L'IA generativa descrive una categoria di funzionalità all'interno dell'intelligenza artificiale che creano contenuto. Le persone interagiscono in genere con l'intelligenza artificiale generativa incorporata in applicazioni per chat. In questo esercizio, verrà messa alla prova l'IA generativa nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti. 

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
 
1. Dopo aver creato le risorse, verrà visualizzata la pagina *Panoramica* del progetto. Nel menu a sinistra nella schermata selezionare **Playground**.
 
    ![Screenshot del menu a sinistra nella schermata del progetto con Servizi di intelligenza artificiale selezionato.](./media/azure-ai-foundry-playgrounds.png)  

## Esplorare l'IA generativa nel playground della chat di Fonderia Azure AI

1. Nella pagina Playground di Fonderia Azure AI selezionare **Prova il playground della chat**. Il playground della chat è un'interfaccia utente che consente di provare a creare un'applicazione di chat con modelli diversi di intelligenza artificiale generativa.  

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