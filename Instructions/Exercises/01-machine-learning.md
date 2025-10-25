---
lab:
  title: Esplorare la funzionalità Machine Learning automatizzato
---

# Esplorare la funzionalità Machine Learning automatizzato

In questo esercizio si userà l'apprendimento automatico automatizzato per eseguire il training e la valutazione di un modello di apprendimento automatico. Si distribuirà e testerà quindi il modello sottoposto a training.

> **Nota**: Questo esercizio è progettato per eseguire i passaggi necessari per eseguire il training e il test di un modello usando***Azure Machine Learning***. Se si ha una sottoscrizione di Azure con autorizzazioni sufficienti, è possibile effettuare il provisioning di un'area di lavoro di Azure Machine Learning e usarla per l'esercizio. Azure Machine Learning, tuttavia, è progettato per soluzioni di apprendimento automatico su scala aziendale che coinvolgono enormi volumi di dati e un ambiente di calcolo basato sul cloud. Alcune operazioni in Azure Machine Learning richiedono il provisioning dell'ambiente di calcolo, che può richiedere molto tempo. Se non si ha accesso ad Azure o se si ha un tempo limitato per completare l'esercizio, viene fornita anche un'app basata su browser denominata***ML Lab*** che include le funzionalità di base di Azure ML usate in questo esercizio ed è possibile usarla per eseguire il training e testare i modelli di apprendimento automatico reali, proprio come si farebbe in Azure ML. Anche se l'interfaccia utente in ML Lab non è*identica* ad Azure Machine Learning, è abbastanza simile per rendere intuitiva la transizione ad Azure Machine Learning. Si noti che l'app ML Lab viene eseguita nel browser, quindi l'aggiornamento della pagina in qualsiasi momento riavvierà l'app.

Il completamento di questo esercizio dovrebbe richiedere circa**35** minuti (meno se si usa l'app ML Lab basata su browser).

## Creare un'area di lavoro

Un'area di lavoro viene usata per riunire tutte le risorse di apprendimento automatico, semplificando la gestione di dati, codice, modelli e altre risorse in un'unica posizione.

1. Aprire il portale per l'ambiente che si vuole usare in questo lab e accedere se richiesto:
    - [Studio di Azure Machine Learning](https://ml.azure.com){:target="_blank"} basato su Azure all'indirizzo`https://ml.azure.com`
    - [ML Lab](https://aka.ms/ml-lab){:target="_blank"} basato su browser all'indirizzo`https://aka.ms/ml-lab`

    > **Suggerimento**: Se studio di Azure Machine Learning si apre in un'area di lavoro esistente, passare alla pagina**Tutte le aree di lavoro**.

1. Creare una nuova area di lavoro con un nome appropriato.

    Se si usa Azure Machine Learning, non è necessario un*hub* per questo esercizio. Scegliere le impostazioni avanzate appropriate in base ai vincoli dei criteri della sottoscrizione di Azure.

1. Dopo aver creato l'area di lavoro, selezionarla per visualizzarne la pagina**Home**.

    L'area di lavoro dispone di più pagine, visualizzate nel riquadro di spostamento a sinistra. È possibile espandere e comprimere questo riquadro usando il menu **&#9776;** nella parte superiore.

## Scarica dati

In questo esercizio si userà un set di dati sulle vendite di gelati per eseguire il training di un modello che prevede la domanda di gelati in un determinato giorno, in base alle caratteristiche stagionali e meteorologiche.

1. In una nuova scheda del browser scaricare**[ml-data.zip](https://aka.ms/mslearn-ml-data)** da`https://aka.ms/mslearn-ml-data` nel computer locale.
1. Estrarre l'archivio**ml-data.zip** scaricato per visualizzare i file in esso contenuti. Si noti che uno di questi file è**ice-cream.csv**, che contiene i dati sulle vendite di gelati necessari per questo esercizio.

## Usare Machine Learning automatizzato per eseguire il training di un modello

Machine Learning automatizzato consente di provare più algoritmi e parametri per eseguire il training di più modelli e identificare quello migliore per i dati.

1. Nel portale visualizzare la pagina**ML automatizzato** (in**Creazione**).

1. Creare un nuovo processo di Machine Learning automatizzato con le impostazioni seguenti, usando**Avanti** come necessario per avanzare tramite l'interfaccia utente:

    > **Suggerimento**: Se nei passaggi seguenti non vengono fornite informazioni esplicite per un'impostazione, usare il valore predefinito.

    **Impostazioni di base**:

    - Assegnare un**nome processo** univoco per il processo di Machine Learning automatizzato

   **Tipo di attività e dati**:

    - Impostare il tipo di attività su**Regressione**.
    - Creare un nuovo asset di dati***tabulari*** denominato**ice-cream**
        - Caricare il file**ice-cream.csv** locale nella risorsa di archiviazione dell'area di lavoro predefinita.
        - Includere<u>solo</u> le colonne seguenti (*Data* è univoco per ogni riga e aggiunge funzionalità predittive autonomamente):
            - **DayOfWeek**
            - **Month**
            - **Temperatura**
            - **Rainfall**
            - **IceCreamsSold**
        - Creare l'asset di dati.
    - Assicurarsi che l'asset di dati**ice-cream** appena creato sia selezionato prima di passare al passaggio successivo

    > **Nota**: Se si usa una sottoscrizione di Azure per cui non si è amministratori, l'accesso basato su chiave alla risorsa di archiviazione potrebbe non essere consentito dai criteri. In questo caso, sarà necessario collaborare con l'amministratore per consentire l'accesso basato su chiave o riconfigurare l'area di lavoro di Azure Machine Learning per usare l'autenticazione Entra ID per accedere alla risorsa di archiviazione. Se non è possibile eseguire questa operazione, usare l'app***ML Lab*** basata su browser per questo esercizio.

    **Impostazioni attività**:

    - Impostare la**colonna di destinazione** (l'etichetta che il modello deve prevedere) su**IceCreamsSold**.
    - Impostare**Impostazioni aggiuntive per la configurazione**:
        - Impostare la**Metrica primaria** sulla metrica da usare per calcolare le prestazioni del modello. In questo esercizio usare il punteggio*R<sup>2</sup>*.
        - Selezionare gli algoritmi del modello da provare (o lasciarli tutti selezionati)
    - Impostare le**Impostazioni di definizione delle funzionalità**:
        - Usare queste impostazioni per personalizzare la definizione delle funzionalità (come vengono preparate le funzionalità dei dati per il training del modello)
    - Impostare**Limiti**:
        - Usare i limiti per terminare il processo di training in anticipo in base a criteri specifici. In questo esercizio impostare i limiti seguenti:
            - **Soglia di punteggio metrica**: 0,9
            - **Timeout dell'esperimento (minuti)**: 15
        
        > **Nota** È importante impostare questi limiti quando si usa Azure Machine Learning, perché l'esecuzione di processi di training per ogni possibile combinazione di algoritmi e definizione delle funzionalità potrebbe richiedere ore.

    **Calcolo**:

    - Usare l'ambiente di calcolo**Serverless**

    **Rivedi**

    - Rivedere le impostazioni e controllarle attentamente. Inviare quindi il processo di training. Viene avviato automaticamente.

1. Attendere il completamento del processo.

    > **Suggerimento**: Se si usa Azure Machine Learning, l'operazione potrebbe richiedere un po' di tempo: questo potrebbe essere il momento giusto per una pausa caffè.

## Esaminare il modello migliore

Al termine del processo di Machine Learning automatizzato, è possibile esaminare il modello migliore sottoposto a training.

1. Nella scheda**Panoramica** della pagina dei dettagli del processo visualizzare le informazioni sul processo e prendere nota del riepilogo del modello migliore.
  
1. Selezionare il**Nome dell'algoritmo** per il modello migliore per visualizzarne i dettagli. Nella pagina dei dettagli del processo figlio visualizzare le schede seguenti:
    - **Panoramica**: Dettagli generali per il processo figlio.
    - **Modello**: Informazioni sul modello sottoposto a training.
    - **Metriche** Metriche di valutazione e visualizzazioni per il modello in base ai dati di test usati durante il processo di training.
    - **Output e log**: Informazioni registrate durante il processo di training.

## Distribuire e testare il modello

1. Nella scheda**Modello** per il modello migliore sottoposto a training dal processo di Machine Learning automatizzato selezionare**Distribuisci** per distribuire il modello in un endpoint in tempo reale.

    Selezionare le opzioni appropriate per**Istanze** e**Macchina virtuale** per l'ambiente di calcolo in cui verrà eseguito l'endpoint distribuito (che può dipendere dalla quota disponibile nella sottoscrizione di Azure) e assegnare nomi appropriati per**endpoint** e**distribuzione**.

1. Attendere la notifica che la distribuzione è stata completata.

    > **Suggerimento**: In studio di Azure Machine Learning la distribuzione degli endpoint può richiedere 5-10 minuti.

## Testare il servizio distribuito

A questo punto è possibile testare il servizio distribuito.

1. Nel menu di spostamento selezionare la pagina**Endpoint** e aprire l'endpoint in tempo reale creato.

1. Nella pagina dell'endpoint visualizzare la scheda**Test**.

1. Nel riquadro**Dati di input per testare l'endpoint** sostituire il codice JSON del modello con i dati di input seguenti:

    ```json
   {
     "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
   }
    ```

1. Fare clic sul pulsante**Test**.

1. Esaminare i risultati dei test, che includono un numero stimato dei noleggi in base alle caratteristiche di input, simile a questo:

    ```JSON
   [
       120.16208168753236
   ]
    ```

    Il riquadro di test ha considerato i dati di input e ha usato il modello sottoposto a training per restituire il numero stimato di noleggi.

## Visualizzare il codice per l'utilizzo del modello

Ora che si dispone di un modello predittivo, gli sviluppatori possono creare applicazioni che lo usano.

1. Nella pagina endpoint in tempo reale visualizzare la**scheda Utilizzo**.
1. Esaminare il codice di esempio per usare il modello.

## Se il tempo lo consente

Per sperimentare ulteriormente l'apprendimento automatico automatizzato, provare a eseguire il training di un modello di**classificazione** basato sul file**penguins.csv** incluso nell'archivio**ml-data.zip** scaricato in precedenza. Usare tutte le colonne di questo set di dati.

Dopo il training e la distribuzione di un modello di classificazione, è possibile testarlo nell'endpoint con il codice JSON seguente:

```json
{
    "input_data": {
    "columns": [
        "CulmenLength",
        "CulmenDepth",
        "FlipperLength",
        "BodyMass"
    ],
    "index": [0],
    "data": [[45.2,13.8,215,4750]]
    }
}
```

## Eliminazione

Se è stato usato Azure Machine Learning per completare questo esercizio, è consigliabile eliminare le risorse create per evitare di accumulare un utilizzo di Azure non necessario.

1. In[Studio di Azure Machine Learning](https://ml.azure.com) nella scheda**Endpoint** selezionare l'endpoint distribuito. Selezionare quindi**Elimina** e confermare l'eliminazione dell'endpoint.

    L'eliminazione delle risorse di calcolo garantisce che alla sottoscrizione non vengano addebitati i costi di calcolo corrispondenti. Verrà tuttavia addebitato un importo ridotto per l'archiviazione dei dati, fintanto che l'area di lavoro di Azure Machine Learning è presente nella sottoscrizione. Se è stata completata l'esplorazione di Azure Machine Learning, è possibile eliminare l'area di lavoro di Azure Machine Learning e le risorse associate.

Per eliminare l'area di lavoro:

1. Nel[portale di Azure](https://portal.azure.com), nella pagina**Gruppi di risorse**, aprire il gruppo di risorse specificato durante la creazione dell'area di lavoro di Azure Machine Learning.
2. Fare clic su**Elimina gruppo di risorse**, digitare il nome del gruppo di risorse per confermare che si vuole eliminarlo e quindi selezionare**Elimina**.
