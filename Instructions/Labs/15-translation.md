---
lab:
  title: Esplorare Traduttore per Azure AI
---

# Esplorare Traduttore per Azure AI

> **Nota:** per completare questo lab è necessaria una [sottoscrizione di Azure](https://azure.microsoft.com/free?azure-portal=true) in cui si ha accesso amministrativo.

L'intelligenza artificiale (IA) può contribuire a semplificare la traduzione tra le lingue, aiutando a rimuovere le barriere alla comunicazione tra paesi e culture diverse.

Per testare le funzionalità del servizio Traduttore per Azure AI, è possibile osservarne il funzionamento direttamente nel portale di Azure. Gli stessi principi e funzionalità sono applicabili a soluzioni reali, ad esempio siti Web o app per smartphone.

## Creare una risorsa per *Traduttore*

È possibile usare il servizio Traduttore creando una risorsa **Traduttore** o una risorsa **Servizi di Azure AI**.

Per questo esercizio, creare una risorsa **Traduttore** nella sottoscrizione di Azure.

1. In un'altra scheda del browser, aprire il portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com?azure-portal=true), eseguendo l'accesso con l'account Microsoft.

1. Fare clic sul pulsante  **&#65291;Crea una risorsa** e cercare *Traduttore*. Selezionare **Crea**. Verrà visualizzata una pagina per creare una risorsa Traduttore. Eseguire la configurazione con le seguenti impostazioni:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: *scegliere una qualsiasi area disponibile*.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: Standard S0.

1. Esaminare e creare la risorsa e attendere il completamento della distribuzione. Passare quindi alla risorsa distribuita.

## Esplorare il servizio Traduttore 

È possibile esplorare le funzionalità del servizio Traduttore nel portale di Azure. 

1. Nel portale di Azure, nella risorsa distribuita, esaminare la pagina *Panoramica*.

    ![Screenshot della pagina Panoramica per la risorsa Traduttore.](media/use-translator/translator-azure-portal.png)

1. Nella sezione *Prova* della pagina di panoramica, sotto la sezione *Da: rilevamento automatico*, digitare il testo `Welcome to Azure AI Fundamentals`. Notare il JSON che appare in corrispondenza della sezione *Visualizza richiesta*. 

1. Nella sezione *Visualizza risposta*, visualizzare il JSON. Dietro le quinte, è stata inviata una *richiesta* al servizio Traduttore. La *risposta* include la lingua di origine rilevata con un punteggio di attendibilità, la traduzione traslitterata usando l'alfabeto della lingua di destinazione e il relativo codice lingua. 

1. La demo nella sezione *Prova* visualizza l'aspetto di una semplice applicazione di traduzione con un'interfaccia utente. Nel caso della demo, non appena viene digitato il testo, viene inviata una richiesta al servizio Traduttore. Come è possibile effettuare questa richiesta? Consultare la scheda *Codice di esempio*. Qui vengono mostrati esempi di codice in diversi linguaggi di programmazione che potrebbero essere usati per effettuare la richiesta. 

1. Identificare le righe degli esempi di codice in cui è necessario includere la **Chiave** e l'**Endpoint** del servizio Traduttore. Con la chiave e l'endpoint, è possibile inviare una richiesta al servizio Traduttore e ricevere una risposta come quella visualizzata nella demo. 

1. Passare al menu di sinistra. In *Gestione risorse* selezionare *Chiavi ed endpoint*. Nel caso di creazione di un'applicazione, qui è possibile trovare la chiave e l'endpoint. 

## Eliminazione

1. Eliminare la risorsa dopo averla usata. 

## Altre informazioni

Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Traduttore](https://learn.microsoft.com/en-us/azure/ai-services/translator/translator-overview).
