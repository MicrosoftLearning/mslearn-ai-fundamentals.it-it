---
lab:
  title: Esplorare il servizio OpenAI di Azure
---

# Esplorare OpenAI di Azure

Il servizio Azure OpenAI offre i modelli di intelligenza artificiale generativi sviluppati da OpenAI alla piattaforma Azure, consentendo di sviluppare potenti soluzioni di intelligenza artificiale che traggono vantaggio dalla sicurezza, dalla scalabilità e dall'integrazione dei servizi forniti dalla piattaforma cloud di Azure.

In questo esercizio si esaminerà il servizio Azure OpenAI e lo si userà per distribuire ed sperimentare modelli di intelligenza artificiale generativi.

Questo esercizio richiederà circa **25** minuti.

## Prima di iniziare

Sarà necessaria una sottoscrizione di Azure approvata per l'accesso al servizio Azure OpenAI sia per i modelli di testo che per i modelli di codice e per i modelli di generazione di immagini DALL-E.

- Per iscriversi per ottenere una sottoscrizione di Azure gratuita, visitare [https://azure.microsoft.com/free](https://azure.microsoft.com/free).
- Per richiedere l'accesso al servizio Azure OpenAI, visitare [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Effettuare il provisioning di una risorsa OpenAI di Azure

Prima di poter usare i modelli OpenAI di Azure, è necessario effettuare il provisioning di una risorsa OpenAI di Azure nella sottoscrizione di Azure.

1. Accedere al [portale di Azure](https://portal.azure.com).
2. Creare una **risorsa OpenAI** di Azure con le impostazioni seguenti:
    - **Sottoscrizione**: *una sottoscrizione di Azure approvata per l'accesso al servizio OpenAI di Azure.*
    - **Gruppo** di risorse: *scegliere un gruppo di risorse esistente o crearne uno nuovo con un nome di propria scelta.*
    - **Area**: Stati Uniti orientali\*
    - **Nome**: *nome univoco di propria scelta*
    - **Piano tariffario**: Standard S0.

    > \* Diverse aree hanno disponibilità e quota diverse per i modelli. In questo esercizio si userà un modello GPT-35-Turbo per la generazione di testo e un modello DALL-E per la generazione di immagini, entrambi supportati negli Stati Uniti orientali.

3. Attendere il completamento della distribuzione. Passare quindi alla risorsa Azure OpenAI distribuita nella portale di Azure.

## Esplorare Azure OpenAI Studio

È possibile distribuire, gestire ed esplorare i modelli nel servizio Azure OpenAI usando Azure OpenAI Studio.

1. Nella pagina Panoramica** per la **risorsa OpenAI di Azure usare il **pulsante Esplora** per aprire Azure OpenAI Studio in una nuova scheda del browser. In alternativa, passare direttamente ad [Azure OpenAI Studio](https://oai.azure.com/).

    Quando si apre Azure OpenAI Studio per la prima volta, dovrebbe essere simile al seguente:

    ![Screenshot di Azure OpenAI Studio.](./media/generative-ai/ai-studio.png)

1. Visualizzare le pagine disponibili nel riquadro a sinistra. È sempre possibile tornare alla home page nella parte superiore. Inoltre, OpenAI Studio offre più pagine in cui è possibile:
    - Sperimentare i modelli in un *playground*.
    - Gestire le distribuzioni e i dati dei modelli.

## Distribuire un modello per la generazione del linguaggio

Per sperimentare la generazione del linguaggio naturale, è prima necessario distribuire un modello.

1. Nella **pagina Modelli** visualizzare i modelli disponibili nell'istanza del servizio Azure OpenAI.
1. Selezionare uno dei **modelli gpt-35-turbo** per i quali lo **stato Distribuibile** è **Sì** e quindi selezionare **Distribuisci**:

    ![Screenshot della pagina Modelli in Azure AI Studio.](./media/generative-ai/deploy-model.png)

1. Creare una nuova distribuzione con le impostazioni seguenti:
    - **Modello**: gpt-35-turbo
    - **Versione** del modello: aggiornamento automatico per impostazione predefinita
    - **Nome** distribuzione: *nome univoco per la distribuzione del modello*
    - **Opzioni avanzate**
        - **Filtro** contenuto: predefinito
        - **Tipo di distribuzione**: Standard
        - **Limite di velocità** dei token al minuto: 5.000\*
        - **Abilita quota** dinamica: abilitata

    > \* Un limite di frequenza di 5.000 token al minuto è più che sufficiente per completare questo esercizio lasciando la capacità per altre persone che usano la stessa sottoscrizione.

## Usare il *playground chat* per lavorare con il modello

Ora che è stato distribuito un modello, è possibile usarlo nel playground di Chat* per generare l'output *del linguaggio naturale dai prompt inviati in un'interfaccia di chat.

1. In [Azure OpenAI Studio](https://oai.azure.com/) passare al **playground chat** nel riquadro sinistro.

    Il playground chat* offre un'interfaccia *chatbot con cui è possibile interagire con il modello distribuito, come illustrato di seguito:

    ![Screenshot del playground chat in Azure OpenAI Studio.](./media/generative-ai/chat-playground.png)

1. **Nel riquadro Configurazione** verificare che la distribuzione del modello sia selezionata.
1. **Nel riquadro Configurazione** assistente selezionare il **modello di messaggio di sistema predefinito** e visualizzare il messaggio di sistema creato da questo modello. Il messaggio di sistema definisce il comportamento del modello nella sessione di chat.
1. **Nella sezione Sessione** di chat immettere il messaggio utente seguente.

    ```
   What is generative AI?
    ```

1. Osservare l'output restituito dal modello, che deve fornire una definizione di intelligenza artificiale generativa.
1. Immettere il messaggio utente seguente come domanda di completamento:

    ```
   What are three benefits it provides?
    ```

1. Esaminare l'output, notando che la sessione di chat ha tenuto traccia dell'input e della risposta precedenti per fornire contesto (quindi interpreta correttamente "it" come riferimento a "intelligenza artificiale generativa") e che fornisce una risposta appropriata in base a ciò che è stato richiesto (dovrebbe restituire tre vantaggi dell'intelligenza artificiale generativa).

## Usare il *playground DALL-E* per generare immagini

Oltre ai modelli di generazione del linguaggio, il servizio Azure OpenAI supporta il modello DALL-E 2 per la generazione di immagini.

> **Nota**: per completare questa sezione dell'esercizio è necessario aver applicato e ricevuto l'accesso alle funzionalità DALL-E nell'applicazione di accesso al servizio OpenAI di Azure.

1. In [Azure OpenAI Studio](https://oai.azure.com/) passare al **playground DALL-E** nel riquadro sinistro.
1. Immettere il prompt seguente:

    ```
    A robot eating spaghetti
    ```

1. Selezionare Genera** e visualizzare **i risultati, che devono essere costituiti da un'immagine in base alla descrizione fornita nel prompt, simile alla seguente:

    ![Screenshot del playgrund DALL-E in Azure OpenAI Studio.](./media/generative-ai/dall-e-playground.png)

1. Generare una seconda immagine modificando il prompt in:

    ```
    A robot eating spaghetti in the style of Rembrandt
    ```
1. Verificare che la nuova immagine soddisfi i requisiti del prompt, in modo simile al seguente:

    ![Screenshot delle immagini generate da DALL-E in Azure OpenAI Studio.](./media/generative-ai/dall-e-results.png)

## Eseguire la pulizia

Al termine dell'operazione con la risorsa OpenAI di Azure, ricordarsi di eliminare la distribuzione o l'intera risorsa nella [portale di Azure](https://portal.azure.com/?azure-portal=true).
