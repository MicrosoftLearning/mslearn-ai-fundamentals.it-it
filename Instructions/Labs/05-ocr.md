---
lab:
  title: Leggere testo in Vision Studio
---

# Leggere testo in Vision Studio

In questo esercizio si userà il servizio Azure per intelligenza artificiale per esplorare le funzionalità di riconoscimento ottico dei caratteri di Visione di Azure AI. Si userà Vision Studio per sperimentare l'estrazione di testo dalle immagini, senza dover scrivere codice.

Il rilevamento e l'interpretazione del testo incorporato in un'immagine rappresentano una sfida comune per i sistemi di visione artificiale. Questa operazione è nota come riconoscimento ottico dei caratteri (OCR). In questo esercizio si userà una risorsa dei servizi di Azure AI, tra cui i servizi Visione di Azure AI. Si userà quindi Vision Studio per provare OCR con diversi tipi di immagini.

## Creare una risorsa *Servizi di Azure AI*

È possibile usare le funzionalità OCR di Visione di Azure AI con una risorsa multiservizio dei **servizi di Azure AI**. Se non è già stato fatto, creare una risorsa **Servizi di Azure AI** nella sottoscrizione di Azure.

1. In un’altra scheda del browser aprire il **portale di Azure** in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l’account Microsoft associato alla sottoscrizione di Azure.

1. Fare clic sul pulsante **&#65291;Crea una risorsa** e cercare *Servizi di Azure Ai*. Selezionare **Crea** un piano di **Servizi di Azure AI**. Verrà visualizzata una pagina per creare una risorsa Servizi di Azure AI. Eseguire la configurazione con le seguenti impostazioni:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: *selezionare l'area geografica più vicina. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2"*.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *Standard S0.*
    - **Selezionando questa casella, confermo di aver letto e compreso tutte le condizioni seguenti**: *Opzione selezionata*.

1. Selezionare **Rivedi e crea**, quindi **Crea** e attendere il completamento della distribuzione.

## Connettere la risorsa del servizio Azure per intelligenza artificiale a Vision Studio

Connettere quindi la risorsa dei servizi di Azure AI di cui in precedenza è stato effettuato il provisioning in Vision Studio.

1. In un'altra scheda del browser, passare a **Vision Studio** su [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Accedere con l'account e assicurarsi di usare la stessa directory di quella in cui è stata creata la risorsa dei servizi di Azure AI.

1. Nella home page di Vision Studio selezionare **Visualizza tutte le risorse** nell'intestazione **Introduzione a Visione**.

    ![Il collegamento Visualizza tutte le risorse è evidenziato in Introduzione a Vision in Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. Nella pagina **Seleziona una risorsa da usare**, passare il cursore del mouse sulla risorsa dell’elenco creata in precedenza, quindi selezionare la casella a sinistra del nome della risorsa, poi scegliere **Seleziona come risorsa predefinita**.

    > **Nota**: Se la risorsa non è elencata, potrebbe essere necessario **aggiornare** la pagina.

    ![La finestra di dialogo Seleziona una risorsa da usare viene visualizzata con la risorsa cog-ms-learn-vision-SUFFIX di Servizi cognitivi evidenziata e selezionata. Il pulsante Seleziona come risorsa predefinita è evidenziato.](./media/analyze-images-vision/default-resource.png)

1. Chiudere la pagina delle impostazioni selezionando "x" in alto a destra nella schermata.

## Estrarre testo dalle immagini in Vision Studio
    
1. In un Web browser passare a **Vision Studio** su [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Nella pagina di destinazione **Introduzione a Visione** selezionare **Riconoscimento ottico dei caratteri**, quindi il riquadro **Estrai testo dalle immagini**.

1. Nella sottotitolo **Prova** acconsentire ai criteri di utilizzo delle risorse leggendo e selezionando la casella.  

1. Selezionare [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images) per scaricare **ocr-images.zip**. Aprire quindi la cartella.

1. Nel portale selezionare **Esplora file** e passare alla cartella del computer in cui è stato scaricato **ocr-images.zip**. Selezionare **advert.jpg** e selezionare **Apri**.

1. Esaminare ora gli elementi restituiti:
    - In **Attributi rilevati** qualsiasi testo trovato nell'immagine è organizzato in una struttura gerarchica di aree, righe e parole.
    - Nell'immagine, la posizione del testo è indicata da un riquadro delimitatore, come illustrato di seguito:

    ![Immagine del testo nell'immagine delimitata.](media/read-text-computer-vision/advert-bounding-boxes.jpg)

1. È ora possibile provare con un'altra immagine. Selezionare **Esplora file** e passare alla cartella in cui sono stati salvati i file di GitHub. Selezionare **letter.jpg**.

    ![Immagine di una lettera digitata.](media/read-text-computer-vision/letter.jpg)

1. Esaminare i risultati della seconda immagine. Dovrebbe restituire il testo e i rettangoli delimitatori del testo. Se si ha tempo, provare con **note.jpg** e **receipt.jpg**.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la documentazione di Visione di Azure AI sul [riconoscimento ottico dei caratteri](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr).
