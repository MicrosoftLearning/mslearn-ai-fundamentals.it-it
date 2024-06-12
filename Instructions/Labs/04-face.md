---
lab:
  title: Rilevare i visi in Vision Studio
---

# Rilevare i visi in Vision Studio

Le soluzioni di visione richiedono spesso che l'IA sia in grado di rilevare i visi umani. Si supponga che la società fittizia di vendita al dettaglio Northwind Traders voglia individuare dove i clienti si trovano in un negozio per aiutarli al meglio. Un modo per eseguire questa operazione consiste nel determinare se sono presenti visi nelle immagini e, in tal caso, per restituire le coordinate del rettangolo di delimitazione che mostrano la loro posizione.

Per testare le funzionalità di rilevamento dei volti del servizio Viso di Intelligenza artificiale di Azure, si userà [Azure Vision Studio](https://portal.vision.cognitive.azure.com/). Si tratta di una piattaforma basata sull'interfaccia utente che consente di esplorare le funzionalità di Visione artificiale di Azure senza dover scrivere codice.

## Creare una risorsa *Servizi di Azure AI*

È possibile usare il servizio Viso di intelligenza artificiale di Azure con una **risorsa multiservizio dei servizi** di Intelligenza artificiale di Azure. Se non è già stato fatto, creare una risorsa **Servizi di Azure AI** nella sottoscrizione di Azure.

1. In un'altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l'account Microsoft associato alla sottoscrizione di Azure.

1. Fare clic sul pulsante **&#65291;Crea una risorsa** e cercare *Servizi di Azure Ai*. Selezionare **Crea** un piano di **Servizi di Azure AI**. Verrà visualizzata una pagina per creare una risorsa Servizi di Azure AI. Eseguire la configurazione con le seguenti impostazioni:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: *selezionare l'area geografica più vicina. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2".*
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *Standard S0.*
    - **Selezionando questa casella si riconosce che ho letto e compreso tutti i termini seguenti**: *Selezionato*.

1. Selezionare **Rivedi e crea** e quindi **Crea** e attendere il completamento della distribuzione.

## Connettere la risorsa del servizio Intelligenza artificiale di Azure a Vision Studio

Connettere quindi la risorsa dei servizi di intelligenza artificiale di Azure di cui è stato effettuato il provisioning in precedenza a Vision Studio.

1. In un'altra scheda del browser passare a Vision Studio all'indirizzo [](https://portal.vision.cognitive.azure.com?azure-portal=true)https://portal.vision.cognitive.azure.com.** **

1. Accedere con l'account e assicurarsi di usare la stessa directory di quella in cui è stata creata la risorsa dei servizi di intelligenza artificiale di Azure.

1. Nella home page di Vision Studio selezionare **Visualizza tutte le risorse** nell'intestazione **Introduzione a Visione** .

    ![Il collegamento Visualizza tutte le risorse è evidenziato in Introduzione a Visione in Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. **Nella pagina Selezionare una risorsa da usare**, passare il cursore del mouse sulla risorsa creata in precedenza nell'elenco e quindi selezionare la casella a sinistra del nome della risorsa, quindi selezionare Seleziona **come risorsa predefinita**.

    > **Nota**: se la risorsa non è elencata, potrebbe essere necessario aggiornare **** la pagina.

    ![La finestra di dialogo Selezionare una risorsa da usare viene visualizzata con la risorsa cog-ms-learn-vision-SUFFIX di Servizi cognitivi evidenziata e selezionata. Il pulsante Seleziona come risorsa predefinita è evidenziato.](./media/analyze-images-vision/default-resource.png)

1. Chiudere la pagina delle impostazioni selezionando "x" in alto a destra nella schermata.

## Rilevare i visi in Vision Studio 

1. In un Web browser passare a Vision Studio all'indirizzo [](https://portal.vision.cognitive.azure.com?azure-portal=true)https://portal.vision.cognitive.azure.com.** **

1. **Nella pagina di destinazione Introduzione a Visione** artificiale selezionare la **scheda Viso** e quindi selezionare il **riquadro Rileva visi in un'immagine**.

1. **Nella sottotitolo Prova in uscita** confermare i criteri di utilizzo delle risorse leggendo e selezionando la casella.  

1. Selezionare ognuna delle immagini di esempio e osservare i dati di rilevamento dei volti restituiti.

1. Ora proviamo con alcune delle nostre immagini. Selezionare questa opzione [**https://aka.ms/mslearn-detect-faces](https://aka.ms/mslearn-detect-faces)** per scaricare **detect-faces.zip.** Aprire quindi la cartella nel computer.

1. Individuare il file denominato **store-camera-1.jpg**, che contiene l'immagine seguente:

    ![Immagine di persone in un negozio.](./media/create-face-solutions/store-camera-1.jpg)

1. Caricare **store-camera-1.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti.

1. Individuare il file denominato **store-camera-2.jpg**, che contiene l'immagine seguente:

    ![Immagine di più persone in un negozio.](./media/create-face-solutions/store-camera-2.jpg)

1. Caricare **store-camera-2.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti.

1. Individuare il file denominato **store-camera-3.jpg**, che contiene l'immagine seguente:

    ![Immagine delle persone in un negozio con una pianta oscurando un viso.](./media/create-face-solutions/store-camera-3.jpg)

1. Caricare **store-camera-3.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti. Si noti che Il viso di Intelligenza artificiale di Azure non ha rilevato il viso nascosto.

In questo esercizio è stato illustrato in che modo i servizi di intelligenza artificiale di Azure possono rilevare i visi nelle immagini. Se hai tempo, prova a provare le immagini di esempio o alcune delle tue immagini.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare le risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** in [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina** e quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la pagina[ del ](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity)servizio Viso per intelligenza artificiale di Azure.
