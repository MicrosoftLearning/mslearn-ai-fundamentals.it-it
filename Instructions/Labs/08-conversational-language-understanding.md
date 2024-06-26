---
lab:
  title: Usare Comprensione del linguaggio di conversazione con Language Studio
---

# Usare Comprensione del linguaggio di conversazione con Language Studio

Gli utenti hanno aspettative sempre crescenti riguardo alla capacità dei computer di usare l'intelligenza artificiale per comprendere i comandi in linguaggio naturale, vocali o digitati. Ad esempio, è possibile che un sistema di domotica controlli i dispositivi nella propria casa usando comandi vocali, ad esempio "accendi la luce" o "accendi il ventilatore". I dispositivi basati sull'intelligenza artificiale possono comprendere questi comandi e intervenire in modo appropriato.

In questo esercizio, si userà Language Studio per creare e testare un progetto che invia istruzioni a dispositivi come luci o ventilatori. Si useranno le funzionalità del servizio di comprensione del linguaggio di conversazione per configurare il progetto. 

## Creare una risorsa del servizio *Lingua*

È possibile usare molte funzionalità di Lingua di Azure AI con una risorsa di **Lingua** o di **Servizi di Azure AI**. Esistono alcune istanze in cui è possibile usare solo una risorsa di Lingua. Per l'esercizio seguente verrà usata una risorsa di **Lingua**. Se non è già stato fatto, creare una risorsa di **Lingua**nella sottoscrizione di Azure.

1. In un’altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l’account Microsoft associato alla sottoscrizione di Azure.

1. Cliccare sul pulsante **＋ Crea una risorsa** e cercare *Servizio Lingua*. Selezionare **Crea** un piano del **Servizio Lingua**. Verrà visualizzata una pagina in cui *Selezionare funzionalità aggiuntive**. Mantenere la selezione predefinita e fare clic su **Continua per creare una risorsa**. 

1. Nella pagina **Crea Lingua**, configurare l'opzione con le impostazioni seguenti:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: *selezionare l'area geografica più vicina. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2"*.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *F0 o S gratuito se F0 gratuito non è disponibile*
    - **Selezionando questa casella, confermo di aver letto e compreso tutte le condizioni seguenti**: *Opzione selezionata*.

1. Selezionare **Rivedi e crea**, quindi **Crea** e attendere il completamento della distribuzione.


### Creare un'app di comprensione del linguaggio di conversazione

Per implementare la comprensione del linguaggio naturale con la funzionalità di comprensione del linguaggio di conversazione, si crea un'app e quindi si aggiungono entità, finalità ed espressioni per definire i comandi che l'app deve eseguire.

1. In una nuova scheda del browser aprire il portale Language Studio all'indirizzo [https://language.azure.com](https://language.azure.com?azure-portal=true) e accedere usando l'account Microsoft associato alla sottoscrizione di Azure.

1. Se viene richiesto di scegliere una risorsa del servizio Lingua, selezionare le impostazioni seguenti:
    - **Directory di Azure**: *la directory di Azure contenente la sottoscrizione*.
    - **Sottoscrizione di Azure**: *La tua sottoscrizione di Azure*.
    - **Risorsa della lingua**: *La risorsa del servizio Lingua creata in precedenza.*

   Se ***non*** viene chiesto di scegliere una risorsa Lingua, è possibile che nella sottoscrizione siano presenti più risorse di questo tipo e in tal caso:
    1. Nella barra in alto della pagina selezionare **Impostazioni (&#9881;)**.
    2. Nella pagina **Impostazioni** visualizzare la scheda **Risorse**.
    3. Selezionare la risorsa del servizio Lingua appena creata, poi selezionare **Cambia risorsa**.
    4. Nella parte superiore della pagina, selezionare **Language Studio** per tornare alla relativa home page.

1. Nella parte superiore del portale scegliere **Comprensione del linguaggio di conversazione** dal menu **Crea nuovo**.

1. Nella finestra di dialogo **Crea un progetto**, nella pagina **Immettere informazioni di base**, immettere i dati seguenti quindi selezionare **Avanti**:
    - **Nome**: *creare un nome univoco*
    - **Linguaggio principale delle espressioni**: *Inglese*
    - **Enable multiple languages in project** (Abilita più lingue nel progetto): *non selezionare*
    - **Descrizione**: `Simple home automation`

    > **Suggerimento**: Prendere nota del *nome del progetto* che verrà usato in un secondo momento.

1. Nella pagina **Rivedi e termina**, selezionare **Crea**.

### Creare finalità, espressioni ed entità

Una *finalità* è un'azione che si intende eseguire. Si può ad esempio voler accendere una luce o spegnere un ventilatore. In questo caso, si definiscono due finalità, rispettivamente per attivare un dispositivo e per disattivarne un altro. Per ogni finalità si specificano quindi *espressioni* di esempio che indicano il tipo di linguaggio usato per definire la finalità.

1. Nel riquadro **Definizione dello schema**, assicurarsi che l'opzione **Intenti** sia selezionata, quindi selezionare **Aggiungi**, aggiungere un intento con il nome `switch_on` (minuscolo) e selezionare **Aggiungi intento**.

    ![Selezionare Aggiungi in Intenti nel riquadro Definizione dello schema.](media/conversational-language-understanding/build-schema.png)

    ![Aggiungere l'intento switch_on e quindi selezionare Aggiungi intento.](media/conversational-language-understanding/add-intent.png)

1. Selezionare la finalità **switch_on**. Verrà visualizzata la pagina **Etichettatura dei dati**. Nell'elenco a discesa **Intento** selezionare **switch_on**. Accanto all'intento **switch_on**, digitare l'espressione `turn the light on` e premere **INVIO** per includere l'espressione nell'elenco.

    ![Aggiungere un'espressione al set di training digitando "attiva la luce" in Espressione.](media/conversational-language-understanding/add-utterance-on.png)

1. Il servizio Lingua richiede almeno cinque esempi di espressioni diverse per ogni finalità in modo da eseguire un training sufficiente del modello linguistico. Aggiungere altri cinque esempi di espressione per la finalità **switch_on**:  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

1. Nel riquadro **Etichettatura delle entità per il training** sul lato destro della schermata selezionare **Etichette** e quindi selezionare **Aggiungi entità**. Digitare `device` (minuscolo), selezionare **Elenco** e selezionare quindi **Aggiungi entità**.

    ![Aggiungere un'entità selezionando Etichette nel pannello Etichettatura delle entità per il training e quindi selezionare Aggiungi entità.](media/conversational-language-understanding/add-entity.png)

    ![Digitare il dispositivo in Nome entità e selezionare Elenco, quindi selezionare Aggiungi entità.](media/conversational-language-understanding/add-entity-device.png)

1. Nell'espressione ***avvia il ventilatore*** evidenziare la parola "ventilatore". Nell'elenco visualizzato selezionare **dispositivo** nella casella *Search for an entity* (Cerca un'entità).

    ![Evidenziare la parola ventilatore nell'espressione e selezionare dispositivo.](media/conversational-language-understanding/switch-on-entity.png)

1. Eseguire la stessa procedura per tutte le espressioni. Etichettare il resto delle espressioni relative al *ventilatore* o alla *luce* con l'entità **dispositivo**. Al termine, verificare di avere le espressioni seguenti e selezionare **Salva modifiche**:

    | **finalità** | **espressione** | **entità** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | Attiva il ventilatore      | Dispositivo: *selezionare il ventilatore* |
    | switch_on   | Apri la luce    | Dispositivo: *selezionare la luce* |
    | switch_on   | Accendi la luce | Dispositivo: *selezionare la luce* |
    | switch_on   | Avvia il ventilatore     | Dispositivo: *selezionare il ventilatore* |
    | switch_on   | Accendi il ventilatore   | Dispositivo: *selezionare il ventilatore* |
    | switch_on   | Attiva la luce   | Dispositivo: *selezionare la luce* |

    ![Al termine, selezionare Salva modifiche.](media/conversational-language-understanding/save-changes.png) 

1. Nel riquadro a sinistra, selezionare **Definizione dello schema** e verificare che l'intento **switch_on** sia nell'elenco. Selezionare quindi **Aggiungi** e aggiungere un nuovo intento denominato `switch_off` (minuscolo).

    ![Tornare alla schermata Definizione dello schema e aggiungere un intento switch_off.](media/conversational-language-understanding/add-switch-off.png) 

1. Selezionare l'intento **switch_off**. Verrà visualizzata la pagina **Etichettatura dei dati**. Nell'elenco a discesa **Intento** selezionare **switch_off**. Accanto all'intento **switch_off**, aggiungere l'espressione `turn the light off`.

1. Aggiungere altri cinque esempi di espressione per la finalità **switch_off**:
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. Etichettare la parola *luce* o *ventilatore* con l'entità **dispositivo**. Al termine, verificare di avere le espressioni seguenti e selezionare **Salva modifiche**:  

    | **finalità** | **espressione** | **entità** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | Disattiva il ventilatore    | Dispositivo: *selezionare il ventilatore* | 
    | switch_off   | Chiudi la luce  | Dispositivo: *selezionare la luce* |
    | switch_off   | Spegni la luce | Dispositivo: *selezionare la luce* |
    | switch_off   | Arresta il ventilatore | Dispositivo: *selezionare il ventilatore* |
    | switch_off   | Spegni il ventilatore | Dispositivo: *selezionare il ventilatore* |
    | switch_off   | Spegni la luce | Dispositivo: *selezionare la luce* |

### Eseguire il training del modello

Ora si è pronti a usare le finalità e le entità definite per eseguire il training del modello linguistico di conversazione per l'app.

1. Sul lato sinistro di Language Studio selezionare **Training jobs** (Processi di addestramento), quindi selezionare **Start a training job** (Avvia un processo di addestramento). Usare le seguenti impostazioni:
    - **Train a new model** (Addestra un nuovo modello): *selezionare l'opzione e scegliere un nome di modello*
    - **Training mode** (Modalità di addestramento): Standard training (free) (Addestramento standard - gratuito)
    - **Data Splitting** (Suddivisione dei dati): *selezionare Automatically split the testing set from the training data (Suddividi automaticamente il set di test dai dati di addestramento), lasciare le percentuali predefinite*
    - Selezionare **Esegui training** nella parte inferiore della pagina.

1. Attendere il completamento del training.

### Distribuire e testare il modello

Per usare il modello sottoposto a training in un'applicazione client, è necessario distribuirlo come endpoint a cui le applicazioni client possono inviare nuove espressioni, in base alle quali verranno previste le finalità e le entità.

1. Sul lato sinistro di Language Studio, selezionare **Deploying a model**.

1. Selezionare il nome del modello e fare clic su **Aggiungi distribuzione**. Usare queste impostazioni:
    - **Creare o selezionare un nome di distribuzione esistente**: *selezionare Creare un nuovo nome di distribuzione. Aggiungere un nome univoco*.
    - **Assegnare il modello sottoposto a training al nome della distribuzione**: *selezionare il nome del modello sottoposto a training*.
    - Selezionare **Distribuisci**

    > **Suggerimento**: Prendere nota del *nome della distribuzione* che verrà usato in un secondo momento. 

1. Quando il modello è stato distribuito, fare clic su **Test delle distribuzioni** sul lato sinistro della pagina, quindi selezionare il modello distribuito in **Nome distribuzione**.

1. Immettere il testo seguente e quindi selezionare **Run the test** (Esegui il test):

    `switch the light on`

    ![Testare il modello selezionando il modello distribuito, quindi immettendo testo e selezionando Esegui il test.](media/conversational-language-understanding/test-model.png) 

    Esaminare il risultato restituito, notando che include la finalità prevista (che dovrebbe essere **switch_on**) e l'entità prevista (**dispositivo**) con un punteggio di attendibilità che indica la probabilità calcolata dal modello per la finalità e l'entità previste. La scheda JSON mostra l'attendibilità comparativa per ogni finalità potenziale (quella con il punteggio di attendibilità più alto è la finalità stimata)

1. Deselezionare la casella di testo e testare il modello con le espressioni seguenti in *Immettere il testo, caricare un file o usare uno dei testi di esempio*:
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

È stato configurato correttamente un progetto di linguaggio di conversazione e sono state definite entità, intenti ed espressioni definite. Si è visto come eseguire il training e la distribuzione di un modello in Language Studio. È stato inoltre testato con entrambe le espressioni definite e con alcune che non sono state definite in modo esplicito, ma che il modello è stato in grado di determinare.

> **NOTA**: La comprensione del linguaggio di conversazione fornisce l'intelligenza per interpretare l'intenzione dell'input, non esegue alcuna azione, ad esempio accendere la luce o il ventilatore. Lo sviluppatore deve compilare un'applicazione che usa il modello di comprensione del linguaggio di conversazione per determinare l'intento dell'utente e quindi automatizzare l'azione appropriata.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata. 1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questa app mostra solo alcune delle funzionalità di comprensione del linguaggio di conversazione del servizio Lingua. Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la pagina [Comprensione del linguaggio di conversazione](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview).
