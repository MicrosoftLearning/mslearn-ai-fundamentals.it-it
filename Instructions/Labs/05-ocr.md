---
lab:
  title: Leggere testo in Vision Studio
---

# Leggere testo in Vision Studio

In questo esercizio si userà il servizio Azure per intelligenza artificiale per esplorare le funzionalità di riconoscimento ottico dei caratteri di Visione artificiale di Azure. Si userà Vision Studio per sperimentare l'estrazione di testo dalle immagini, senza dover scrivere codice.

Una sfida comune di visione artificiale consiste nel rilevare e interpretare il testo incorporato all'interno di un'immagine. Questa operazione è nota come riconoscimento ottico dei caratteri (OCR). In questo esercizio si userà una risorsa dei servizi di intelligenza artificiale di Azure, che include i servizi Visione artificiale di Azure. Si userà quindi Vision Studio per provare OCR con diversi tipi di immagini.

## Creare una risorsa *Servizi di Azure AI*

È possibile usare le funzionalità OCR di Visione artificiale di Azure con una **risorsa multiservizio dei servizi** di intelligenza artificiale di Azure. Se non è già stato fatto, creare una risorsa **Servizi di Azure AI** nella sottoscrizione di Azure.

1. In un'altra scheda del browser aprire il **portale di Azure** in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l'account Microsoft associato alla sottoscrizione di Azure.

1. Fare clic sul pulsante **&#65291;Crea una risorsa** e cercare *Servizi di Azure Ai*. Selezionare **Crea** un piano di **Servizi di Azure AI**. Verrà visualizzata una pagina per creare una risorsa Servizi di Azure AI. Eseguire la configurazione con le seguenti impostazioni:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: Stati Uniti orientali.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *Standard S0.*
    - **Selezionando questa casella si riconosce che ho letto e compreso tutti i termini seguenti**: *Selezionato*.

1. Selezionare **Rivedi e crea** e quindi **Crea** e attendere il completamento della distribuzione.

## Connessione la risorsa del servizio azure per intelligenza artificiale in Vision Studio

Connettere quindi la risorsa dei servizi di intelligenza artificiale di Azure di cui è stato effettuato il provisioning in precedenza a Vision Studio.

1. In un'altra scheda del browser passare a Vision Studio all'indirizzo [](https://portal.vision.cognitive.azure.com?azure-portal=true)https://portal.vision.cognitive.azure.com.** **

1. Accedere con l'account e assicurarsi di usare la stessa directory di quella in cui è stata creata la risorsa dei servizi di intelligenza artificiale di Azure.

1. Nella home page di Vision Studio selezionare **Visualizza tutte le risorse** nell'intestazione **Introduzione a Visione** .

    ![Il collegamento Visualizza tutte le risorse è evidenziato in Introduzione a Visione in Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. **Nella pagina Selezionare una risorsa da usare**, passare il cursore del mouse sulla risorsa creata in precedenza nell'elenco e quindi selezionare la casella a sinistra del nome della risorsa, quindi selezionare Seleziona **come risorsa predefinita**.

    > **Nota**: se la risorsa non è elencata, potrebbe essere necessario aggiornare **** la pagina.

    ![La finestra di dialogo Selezionare una risorsa da usare viene visualizzata con la risorsa cog-ms-learn-vision-SUFFIX di Servizi cognitivi evidenziata e selezionata. Il pulsante Seleziona come risorsa predefinita è evidenziato.](./media/analyze-images-vision/default-resource.png)

1. Chiudere la pagina delle impostazioni selezionando "x" in alto a destra nella schermata.

## Estrarre testo dalle immagini in Vision Studio
    
1. In un Web browser passare a Vision Studio all'indirizzo [](https://portal.vision.cognitive.azure.com?azure-portal=true)https://portal.vision.cognitive.azure.com.** **

1. Nella **pagina di destinazione Introduzione a Visione** artificiale selezionare **Riconoscimento** ottico dei caratteri e quindi il **riquadro Estrai testo dalle immagini** .

1. **Nella sottotitolo Prova in uscita** confermare i criteri di utilizzo delle risorse leggendo e selezionando la casella.  

1. Selezionare questa opzione [**https://aka.ms/mslearn-ocr-images](https://aka.ms/mslearn-ocr-images)** per scaricare **ocr-images.zip.** Aprire quindi la cartella .

1. Nel portale selezionare **Sfoglia un file** e passare alla cartella nel computer in cui è stato scaricato **ocr-images.zip**. Selezionare **advert.jpg** e selezionare **Apri**.

1. Esaminare ora gli elementi restituiti:
    - In **Attributi** rilevati qualsiasi testo trovato nell'immagine è organizzato in una struttura gerarchica di aree, righe e parole.
    - Nell'immagine la posizione del testo è indicata da un rettangolo delimitatore, come illustrato di seguito:

    ![Immagine del testo nell'immagine delimitata](media/read-text-computer-vision/text-bounding-boxes.png)

1. È ora possibile provare un'altra immagine. Selezionare **Sfoglia per un file** e passare alla cartella in cui sono stati salvati i file da GitHub. Selezionare **letter.jpg**.

    ![Immagine di una lettera digitata.](media/read-text-computer-vision/letter.jpg)

1. Esaminare i risultati della seconda immagine. Deve restituire il testo e le caselle di delimitazione del testo. Se si ha tempo, provare **note.jpg** e **receipt.jpg**.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare le risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** in [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina** e quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la documentazione di Visione artificiale di Azure sul [riconoscimento](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr) ottico dei caratteri.
