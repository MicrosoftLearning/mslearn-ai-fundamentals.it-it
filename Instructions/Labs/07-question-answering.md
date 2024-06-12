---
lab:
  title: Usare la risposta alle domande con Language Studio
---

# Usare il modello di risposte alle domande con Language Studio

In questo esercizio si userà Language Studio per creare ed eseguire il training di una knowledge base di domande e risposte che verranno usate da un bot dei servizi clienti. Il contenuto della knowledge base proviene da una pagina di domande frequenti esistente dal sito Web di Margie's Travel, un'agenzia di viaggi fittizia. Si userà quindi Language Studio per vedere come funziona quando viene usato dai clienti.

Quando si implementa un bot, il primo passaggio consiste nel creare una knowledge base di coppie di domande e risposte. Viene usato insieme alle funzionalità di elaborazione del linguaggio naturale predefinite in modo che il bot possa interpretare le domande e trovare la risposta più appropriata per l'utente.

Il linguaggio di intelligenza artificiale di Azure include *funzionalità di risposta alle* domande, che verranno usate per creare una knowledge base. Le knowledge base possono essere create immettendo manualmente coppie di domande e risposte o da un documento o da una pagina Web esistente. Margie's Travel vuole usare il documento di domande frequenti esistenti.

La funzionalità di risposta alle domande del servizio di linguaggio consente di creare rapidamente una knowledge base, immettendo coppie di domande e risposte o da un documento o una pagina Web esistente. Può quindi usare alcune capacità di elaborazione del linguaggio naturale predefinite per interpretare le domande e trovare le risposte appropriate.

## Creare una *risorsa lingua*

Per usare la risposta alle domande, è necessaria una **risorsa Lingua** .

1. In un'altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l'account Microsoft associato alla sottoscrizione di Azure.

1. Fare clic sul **&#65291; Creare un pulsante di risorsa** e cercare *Servizio* di linguaggio. Selezionare **Crea** un **piano di servizio** linguistico. Verrà visualizzata una pagina in **Selezionare funzionalità** aggiuntive. Usare le seguenti impostazioni:
    - **Selezionare Funzionalità** aggiuntive:
        - **Funzionalità predefinite**: *mantenere le funzionalità predefinite*.
        - **Funzionalità personalizzate**: *selezionare Risposta personalizzata alle domande*.
     - Selezionare **Continua per creare la risorsa Creazione di una risorsa**
    ![del servizio linguistico con risposte alle domande personalizzate abilitate.](media/create-a-bot/create-language-service-resource.png)

1. Nella pagina **Crea Lingua** specificare le impostazioni seguenti:
    - **Dettagli del progetto**
        - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
        - **Gruppo di risorse**: *selezionare un gruppo di risorse esistente o crearne uno nuovo*.
    - **Dettagli dell'istanza**
        - **Area**: *selezionare un'area. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2"*      
        - **Nome**: *specificare un nome univoco per la risorsa Lingua*.
        - **Piano tariffario**: S (1.000 chiamate al minuto).
    - **Risposta personalizzata alle domande**
        - **Area di Ricerca di Azure**: *qualsiasi località disponibile*.
        - **Piano tariffario** di Ricerca di Azure: F gratuito (3 indici) - (*se questo livello non è disponibile, selezionare Basic*)
    - **Avviso sull'IA responsabile**
        - **Selezionando questa casella, dichiaro di conoscere e confermare tutti i termini indicati nei nostri principi di intelligenza artificiale responsabile**: *selezionata*.

1. Selezionare **Rivedi e crea** e quindi crea****. Attendere il completamento della distribuzione del servizio Lingua che supporterà la knowledge base della funzionalità di risposta alla domanda personalizzata.

    > **Nota:** se è già stato effettuato il provisioning della risorsa **Ricerca cognitiva di Azure** di livello gratuito, la quota potrebbe non consentire di crearne un'altra. In questo caso, selezionare un livello diverso da **Gratuito F**.

## Crea un nuovo progetto

1. In una nuova scheda del browser aprire il portale Language Studio all'indirizzo [https://language.azure.com](https://language.azure.com?azure-portal=true) e accedere usando l'account Microsoft associato alla sottoscrizione di Azure.
1. Se viene richiesto di scegliere una risorsa del servizio Lingua, selezionare le impostazioni seguenti:
    - **Directory di** Azure: *directory di Azure contenente la sottoscrizione*.
    - **Sottoscrizione di** Azure: *sottoscrizione di* Azure.
    - **Risorsa lingua: risorsa** lingua creata in precedenza *. *

    Se ***non*** viene chiesto di scegliere una risorsa Lingua, è possibile che nella sottoscrizione siano presenti più risorse di questo tipo e in tal caso:
    1. Nella barra in alto se la pagina selezionare **Impostazioni (&#9881;)**.      
    1. Nella pagina **Impostazioni** visualizzare la scheda **Risorse**.
    1. Selezionare la risorsa di lingua appena creata e selezionare **Cambia risorsa**.
    1. Nella parte superiore della pagina selezionare **Language Studio** per tornare alla home page di Language Studio.

1. Nella parte superiore del portale di Language Studio scegliere **Risposta personalizzata alle domande** dal menu **Crea nuovo**.

    ![Risposta personalizzata alle domande](media/create-a-bot/create-custom-question-answering.png)

1. Nella pagina **Scegli l'impostazione della lingua per la risorsa *nome della risorsa*** selezionare **Seleziona la lingua quando si crea un progetto in questa risorsa** e fare clic su **Avanti**.
  ![Si vuole selezionare la lingua](media/create-a-bot/create-project.png)

1. Nella pagina **Enter basic information** (Immetti informazioni di base) immettere i dati seguenti e fare clic su **Avanti**:
    - **Risorsa Lingua**: *scegliere la risorsa Lingua*.  
    - **Risorsa Ricerca di Azure**: *scegliere la risorsa Ricerca di Azure*.
    - **Nome**: `MargiesTravel`
    - **Descrizione**: `A simple knowledge base`
    - **Lingua di origine**: inglese
    - **Risposta predefinita quando non viene restituita** alcuna risposta: `No answer found`
1. Nella **pagina Rivedi e fine** selezionare **Crea progetto**.
1. Verrà visualizzata la pagina **Gestisci origini**. Seleziona **&#65291; Aggiungere l'origine** e selezionare **URL**.
1. Nella **casella Aggiungi URL** selezionare **+ Aggiungi URL**. Digitare quanto segue e selezionare **Aggiungi tutto**:
    - **Nome** URL: `MargiesKB`
    - **URL**: `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/natural-language/margies_faq.docx`
    - **Classifica struttura file**: *Rilevamento automatico*
1. Selezionare **Aggiungi tutto.**  

 ![Aggiungere URL](media/create-a-bot/add-url.png)

## Modificare la knowledge base

La knowledge base si basa sui dettagli nel documento delle domande frequenti e su alcune risposte predefinite. È possibile aggiungere coppie di domande e risposte personalizzate per integrare questi dati.

1. Espandere il pannello sinistro e selezionare **Modifica knowledge base**. Selezionare **+** quindi per aggiungere una nuova coppia di domande.
1. **Nella finestra di dialogo Aggiungi una nuova coppia** di risposte alla domanda digitare** **`Hello`e nel **tipo di `Hi`risposta** , quindi selezionare **Fine**.
1. Espandere **Domande** alternative e selezionare **+ Aggiungi domanda** alternativa. `Hiya`Immettere quindi come formulazione alternativa per "Hello".
1. Nella parte superiore del **riquadro Coppie** di risposte alle domande selezionare **Salva** per salvare la knowledge base.

## Eseguire il training e il test della knowledge base

Ora che è stata creata una knowledge base, è possibile testarla.

1. Nella parte superiore del **riquadro Coppie** di risposte alle domande selezionare **Test** per testare la knowledge base.
1. Nella parte inferiore del riquadro di test immettere il messaggio `Hi`. La risposta *Hi* deve essere restituita.
1. Nella parte inferiore del riquadro di test immettere il messaggio `I want to book a flight`. Dovrebbe essere restituita una risposta appropriata dalle domande frequenti.

    > **Nota:** la risposta include una *risposta breve* oltre a un *passaggio di risposta* più dettagliato: il passaggio di risposta mostra il testo completo nel documento delle domande frequenti per la domanda più simile, mentre la risposta breve viene estratta in modo intelligente dal passaggio. È possibile controllare se la risposta breve proviene dalla risposta usando la casella di controllo **Visualizza risposta breve** nella parte superiore del riquadro di test.

1. Provare un'altra domanda, ad esempio `How can I cancel a reservation?`
1. Al termine del test della Knowledge Base, selezionare **Test** per chiudere il riquadro test.

## Creare un bot per la knowledge base

La knowledge base offre un servizio back-end che le applicazioni client possono usare per rispondere alle domande tramite una qualche forma di interfaccia utente. In genere, queste applicazioni client sono bot. Per rendere la knowledge base disponibile per un bot, è necessario pubblicarla come servizio accessibile tramite HTTP. È quindi possibile usare il servizio Azure Bot per creare e ospitare un bot che usa la knowledge base per rispondere alle domande dell'utente.

1. Nel pannello sinistro selezionare **Distribuisci knowledge base**.
1. Nella parte superiore della pagina selezionare **Distribuisci**. Una finestra di dialogo chiederà se si vuole distribuire il progetto. Seleziona **Distribuisci**.

 ![Distribuire la Knowledge Base.](media/create-a-bot/deploy-knowledge-base.png)

1. Dopo aver distribuito il servizio, selezionare **Crea un bot**. Verrà aperto il portale di Azure in una nuova scheda del browser, dove è possibile creare un bot per app Web nella sottoscrizione di Azure in uso.
1. Nella portale di Azure creare un **bot** app Web. È possibile che venga visualizzato un messaggio di avviso per verificare che l'origine del modello sia attendibile. Non è necessario eseguire alcuna azione per il messaggio. Continuare aggiornando le impostazioni seguenti:

    - **Dettagli del progetto**
        - **Sottoscrizione**: *la sottoscrizione di Azure usata*
        - **Gruppo di risorse**: *gruppo di risorse contenente la risorsa Lingua*
    - **Dettagli istanza**
        - **Posizione del gruppo di risorse**: *la stessa posizione del servizio Lingua*.
    - **Azure Bot**
        - **Handle di bot**: *nome univoco per il bot* (*pre-popolato*)
    - **Scegliere il piano tariffario**
        - **Piano tariffario**: gratuito F0 (potrebbe essere necessario selezionare *Cambia piano*).
    - **ID app Microsoft**
        - **Tipo di** creazione: *selezionare **Crea nuova identità gestita assegnata dall'utente*** 

5. Selezionare **Avanti** per continuare ad aggiornare le impostazioni. 
    - **Servizio app**
        - **Nome dell'app**: *uguale a **Handle di bot** con **.azurewebsites.net** aggiunto automaticamente*
        - **Lingua dell'SDK**: *scegliere C# o Node.js*
    - **Piano di servizio app**
        - **Tipo di creazione: *selezionare **Crea nuovo piano di** servizio app***
    - **Impostazioni app**
        - **Chiave** risorsa lingua: *è necessario copiare la chiave della risorsa lingua e incollarla qui*:
            - Aprire un'altra scheda del browser e passare al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com?azure-portal=true).
            - Passare alla risorsa del servizio linguistico.
            - Nella **pagina Chiavi ed endpoint** copiare una delle chiavi
            - Incollarlo qui.
        - **Nome progetto della lingua**: MargiesTravel
        - **Nome host dell'endpoint di servizio della lingua**: *pre-popolato con l'endpoint di servizio della lingua*
    - **Dettagli del servizio della lingua**
        - **ID sottoscrizione**: *pre-popolato con il proprio ID sottoscrizione*
        - **Nome gruppo di risorse**: *pre-popolato con il proprio nome del gruppo di risorse.*
        - **Nome dell'account**: *pre-popolato con il nome della risorsa*

1. Seleziona **Crea**. Attendere quindi che il bot venga creato (l'icona di notifica in alto a destra, simile a una campana, verrà animata durante l'attesa). Quindi, nella notifica che la distribuzione è stata completata, selezionare **Vai alla risorsa** (o in alternativa, nella home page fare clic su **Gruppi** di risorse, aprire il gruppo di risorse in cui è stato creato il bot e selezionare la **risorsa bot di Azure** ).
1. Nel riquadro sinistro del bot cercare **Impostazioni**, selezionare **Test in chat Web** e attendere che il bot visualizzi il messaggio **Hello and Welcome** (l'inizializzazione potrebbe richiedere alcuni secondi).
1. Usa l'interfaccia della chat di test per assicurarti che il bot risponda alle domande dalla tua knowledge base come previsto. Provare ad esempio a inviare `I need to cancel my hotel`.

Sperimentare l'uso del bot. Probabilmente si noterà che può rispondere alle domande disponibili nelle domande frequenti in modo abbastanza accurato, ma avrà una capacità limitata di interpretare le domande per cui non è stato sottoposto a training. È sempre possibile usare Language Studio per modificare la knowledge base per migliorarla e ripubblicarla.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare le risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse contenente la risorsa creata. 
1. Selezionare la risorsa e selezionare **Elimina** e quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

- Per altre informazioni sul servizio di risposta alla domanda, vedere la [documentazione](https://docs.microsoft.com/azure/cognitive-services/language-service/question-answering/overview).
- Per altre informazioni sul servizio Bot Microsoft, vedere [la pagina del servizio Azure Bot](https://azure.microsoft.com/services/bot-service/).
