---
lab:
  title: Rilevare i visi in Vision Studio
---

# Rilevare i visi in Vision Studio

Le soluzioni di visione richiedono spesso che l'IA sia in grado di rilevare i visi umani. Si supponga che la società fittizia di vendita al dettaglio Northwind Traders voglia individuare dove i clienti si trovano in un negozio per aiutarli al meglio. Un modo per eseguire questa operazione consiste nel determinare se sono presenti dei visi nelle immagini e, in tal caso, nel restituire le coordinate del rettangolo di delimitazione che mostrano la loro posizione.

Per testare le funzionalità di rilevamento dei volti del servizio Viso di Azure per intelligenza artificiale, si userà [Azure Vision Studio](https://portal.vision.cognitive.azure.com/). Si tratta di una piattaforma basata sull'interfaccia utente che consente di esplorare le funzionalità di Visione di Azure AI senza dover scrivere codice.

## Creare una risorsa *Servizi di Azure AI*

È possibile usare il servizio Viso di Azure per intelligenza artificiale con una risorsa multiservizio dei **servizi di Azure per intelligenza artificiale**. Se non è già stato fatto, creare una risorsa **Servizi di Azure AI** nella sottoscrizione di Azure.

1. In un’altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l’account Microsoft associato alla sottoscrizione di Azure.

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

## Rilevare i visi in Vision Studio 

1. In un Web browser passare a **Vision Studio** su [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Nella pagina di destinazione **Introduzione a Vision** selezionare la scheda **Viso** e quindi selezionare il riquadro **Rileva visi in un'immagine**.

1. Nel sottotitolo **Prova in uscita** confermare i criteri di utilizzo delle risorse leggendo e selezionando la casella.  

1. Selezionare ognuna delle immagini di esempio e osservare i dati di rilevamento dei volti restituiti.

1. Ora proviamo con alcune delle nostre immagini. Selezionare [**https://aka.ms/mslearn-detect-faces**](https://aka.ms/mslearn-detect-faces) per scaricare **detect-faces.zip**. Aprire quindi la cartella nel computer.

1. Individuare il file denominato **store-camera-1.jpg**, che contiene l'immagine seguente:

    ![Immagine di persone in un negozio.](./media/create-face-solutions/store-camera-1.jpg)

1. Caricare **store-camera-1.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti.

1. Individuare il file denominato **store-camera-2.jpg**, che contiene l'immagine seguente:

    ![Immagine di più persone in un negozio.](./media/create-face-solutions/store-camera-2.jpg)

1. Caricare **store-camera-2.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti.

1. Individuare il file denominato **store-camera-3.jpg**, che contiene l'immagine seguente:

    ![Immagine delle persone in un negozio con una pianta oscurando un viso.](./media/create-face-solutions/store-camera-3.jpg)

1. Caricare **store-camera-3.jpg** ed esaminare i dettagli di rilevamento dei volti restituiti. Si noti che Viso di Azure AI non ha rilevato il viso nascosto.

In questo esercizio è stato illustrato in che modo i servizi di intelligenza artificiale di Azure possono rilevare i visi nelle immagini. Se si ha tempo, provare le immagini di esempio o alcune delle immagini proprie.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Viso di Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity).
