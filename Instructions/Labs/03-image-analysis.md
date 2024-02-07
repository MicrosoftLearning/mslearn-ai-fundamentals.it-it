---
lab:
  title: Analizzare le immagini in Vision Studio
---

# Analizzare le immagini in Vision Studio 

**Visione** artificiale di Azure include numerose funzionalità per comprendere il contenuto e il contesto delle immagini ed estrarre informazioni dalle immagini. Azure AI Vision Studio consente di provare molte delle funzionalità di analisi delle immagini. 

In questo esercizio si userà Vision Studio per analizzare le immagini usando le esperienze try-it-out predefinite. Si supponga che il rivenditore *fittizio Northwind Traders* abbia deciso di implementare un "negozio intelligente", in cui i servizi di intelligenza artificiale monitorano lo store per identificare i clienti che richiedono assistenza e indirizzare i dipendenti a aiutarli. Usando Visione artificiale di Azure, le immagini scattate da fotocamere in tutto il negozio possono essere analizzate per fornire descrizioni significative di ciò che illustrano.

## Creare una risorsa *Servizi di Azure AI*

È possibile usare le funzionalità di analisi delle immagini di Visione artificiale di Azure con una **risorsa multiservizio di Servizi** di intelligenza artificiale di Azure. Se non è già stato fatto, creare una risorsa **Servizi di Azure AI** nella sottoscrizione di Azure.

1. In un'altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l'account Microsoft associato alla sottoscrizione di Azure.

1. Fare clic sul pulsante **&#65291;Crea una risorsa** e cercare *Servizi di Azure Ai*. Selezionare **Crea** un piano di **Servizi di Azure AI**. Verrà visualizzata una pagina per creare una risorsa Servizi di Azure AI. Eseguire la configurazione con le seguenti impostazioni:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: Stati Uniti orientali.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *Standard S0.*
    - **Selezionando questa casella si riconosce che ho letto e compreso tutti i termini seguenti**: *Selezionato*.

1. Selezionare **Rivedi e crea** e quindi **Crea** e attendere il completamento della distribuzione.

## Connessione la risorsa del servizio azure per intelligenza artificiale in Vision Studio

Connettere quindi la risorsa del servizio Di intelligenza artificiale di Azure di cui è stato effettuato il provisioning in precedenza a Vision Studio.

1. In un'altra scheda del browser passare a [Vision Studio](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Accedere con l'account e assicurarsi di usare la stessa directory di quella in cui è stata creata la risorsa dei servizi di intelligenza artificiale di Azure.

1. Nella home page di Vision Studio selezionare **Visualizza tutte le risorse** nell'intestazione **Introduzione a Visione** .

    ![Il collegamento Visualizza tutte le risorse è evidenziato in Introduzione a Visione in Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. **Nella pagina Selezionare una risorsa da usare**, passare il cursore del mouse sulla risorsa creata in precedenza nell'elenco e quindi selezionare la casella a sinistra del nome della risorsa, quindi selezionare Seleziona **come risorsa predefinita**.

    > **Nota**: se la risorsa non è elencata, potrebbe essere necessario aggiornare **** la pagina.

    ![La finestra di dialogo Selezionare una risorsa da usare viene visualizzata con la risorsa cog-ms-learn-vision-SUFFIX di Servizi cognitivi evidenziata e selezionata. Il pulsante Seleziona come risorsa predefinita è evidenziato.](./media/analyze-images-vision/default-resource.png)

1. Chiudere la pagina delle impostazioni selezionando "x" in alto a destra nella schermata.

## Generare didascalia per un'immagine

A questo punto è possibile usare Vision Studio per analizzare le immagini scattate da una fotocamera nel *negozio Northwind Traders* .

Si esaminerà ora l'immagine didascalia funzionalità di Visione artificiale di Azure. Le didascalia di immagini sono disponibili tramite le **funzionalità Caption e **Dense Captions****.

1. In un Web browser passare a [Vision Studio](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Nella **pagina di destinazione Introduzione a Visione** artificiale selezionare la **scheda Analisi** immagini e quindi selezionare il **riquadro Aggiungi didascalia alle immagini**.

    ![Nella home page di Vision Studio la scheda Analisi immagini è selezionata ed evidenziata. Il riquadro Aggiungi didascalia alle immagini è evidenziato.](./media/analyze-images-vision/add-captions.png)

1. **Nella sottotitolo Prova in uscita** confermare i criteri di utilizzo delle risorse leggendo e selezionando la casella.  

1. Selezionare questa opzione [**https://aka.ms/mslearn-images-for-analysis](https://aka.ms/mslearn-images-for-analysis)** per scaricare **image-analysis.zip.** Aprire la cartella nel computer e individuare il file denominato **store-camera-1.jpg**, che contiene l'immagine seguente:

    ![Immagine di un genitore che usa una fotocamera del cellulare per scattare una foto di un bambino in un negozio](./media/analyze-images-vision/store-camera-1.jpg)

1. Caricare l'immagine **store-camera-1.jpg** trascinandola nella **casella Trascinare i file qui** o passando al file system.

1. Osservare il testo generato didascalia, visibile nel **pannello Attributi** rilevati a destra dell'immagine.

    La **funzionalità Caption** fornisce una singola frase in inglese leggibile e leggibile che descrive il contenuto dell'immagine.

1. Successivamente, usare la stessa immagine per eseguire **didascalia** dense. Tornare alla **home page di Vision Studio** e, come in precedenza, selezionare la **scheda Analisi** immagini e quindi selezionare il **riquadro Dense didascalia ing**.

    La **funzionalità Dense Captions** differisce dalla **funzionalità Caption** in quanto fornisce più didascalia leggibili per un'immagine, una che descrive il contenuto dell'immagine e altre, ognuna che copre gli oggetti essenziali rilevati nell'immagine. Ogni oggetto rilevato include un rettangolo di selezione, che definisce le coordinate pixel all'interno dell'immagine associata all'oggetto.

1. Passare il puntatore del mouse su uno dei didascalia nell'elenco **Attributi rilevati** e osservare cosa accade all'interno dell'immagine.

    ![Vengono visualizzate l'immagine e i relativi didascalia.](./media/analyze-images-vision/dense-captioning.png)

    Spostare il cursore del mouse sulle altre didascalia nell'elenco e osservare come il rettangolo di delimitazione viene spostato nell'immagine per evidenziare la parte dell'immagine usata per generare il didascalia.

## Assegnazione di tag alle immagini

La funzionalità successiva che si proverà è la **funzionalità Estrai tag** . L'estrazione di tag si basa su migliaia di oggetti riconoscibili, tra cui esseri viventi, paesaggi e azioni.

1. Tornare alla home page di Vision Studio, quindi selezionare il **riquadro Estrai tag comuni dalle immagini** nella **scheda Analisi** immagini.

2. **In Scegliere il modello da provare** lasciare **selezionato il modello predefinito e il modello** gap. **In Scegliere la lingua** selezionare **Inglese** o una lingua delle preferenze.

3. Aprire la cartella contenente le immagini scaricate e individuare il file denominato **store-image-2.jpg**, simile al seguente:

    ![Immagine di una persona con un carrello della spesa in un supermercato](./media/analyze-images-vision/store-camera-2.jpg)

4. Caricare il **file store-camera-2.jpg** .

5. Esaminare l'elenco dei tag estratti dall'immagine e il punteggio di attendibilità per ognuno nel pannello degli attributi rilevati. Qui il punteggio di attendibilità è la probabilità che il testo per l'attributo rilevato descriva ciò che è effettivamente nell'immagine. Si noti nell'elenco dei tag che include non solo oggetti, ma azioni, ad esempio *shopping*, *vendita* e *standing*.

    ![Screenshot del pannello rileva attributi in Vision Studio con punteggi di testo e attendibilità visualizzati accanto all'immagine originale.](./media/analyze-images-vision/detect-attributes.png)

## Rilevamento oggetti

In questa attività si usa la **funzionalità rilevamento** oggetti di Analisi immagini. Rilevamento oggetti rileva ed estrae rettangoli delimitatori basati su migliaia di oggetti riconoscibili e esseri viventi.

1. Tornare alla home page di Vision Studio, quindi selezionare il **riquadro Rileva oggetti comuni nelle immagini** nella **scheda Analisi** immagini.

1. **In Scegliere il modello da provare** lasciare **selezionato il modello predefinito e il modello** gap.

1. Aprire la cartella contenente le immagini scaricate e individuare il file denominato **store-camera-3.jpg**, simile al seguente:

    ![Immagine di una persona con un carrello per gli acquisti](./media/analyze-images-vision/store-camera-3.jpg)

1. Caricare il **file store-camera-3.jpg** .

1. Nella **casella Attributi** rilevati osservare l'elenco degli oggetti rilevati e i relativi punteggi di attendibilità.

1. Passare il cursore del mouse sugli oggetti nell'elenco **Attributi** rilevati per evidenziare il rettangolo di selezione dell'oggetto nell'immagine.

1. Spostare il **dispositivo di scorrimento Valore** soglia fino a quando non viene visualizzato un valore pari a 70 a destra del dispositivo di scorrimento. Osservare cosa accade agli oggetti nell'elenco. Il dispositivo di scorrimento soglia specifica che devono essere visualizzati solo gli oggetti identificati con un punteggio di attendibilità o una probabilità maggiore della soglia.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare le risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1.  Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse contenente la risorsa creata. 
1.  Selezionare la risorsa e selezionare **Elimina** e quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la [pagina](https://learn.microsoft.com/azure/ai-services/computer-vision/overview) Visione artificiale di Azure.
