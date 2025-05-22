---
lab:
  title: Analizzare le immagini nel portale Fonderia Azure AI
---

# Analizzare le immagini nel portale Fonderia Azure AI

**Visione di Azure AI** include numerose funzionalità per comprendere il contenuto e il contesto delle immagini ed estrarre informazioni dalle immagini. In questo esercizio, viene utilizzato Visione di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per analizzare le immagini usando le esperienze try-it-out predefinite. 

Si supponga che l'azienda di vendita al dettaglio fittizia *Northwind Traders* abbia deciso di implementare un "negozio intelligente", in cui i servizi di intelligenza artificiale mantengono monitorato il negozio per identificare i clienti che richiedono assistenza e indirizzare i dipendenti per aiutarli. Usando Visione di Azure AI, le immagini scattate da fotocamere in tutto il negozio possono essere analizzate per fornire descrizioni significative di ciò che illustrano.

## Creare un progetto nel portale Fonderia Azure AI

Per iniziare, creare un progetto Fonderia Azure AI.

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page di Fonderia Azure AI con l'opzione Crea un agente selezionata.](./media/azure-ai-foundry-home-page.png)

1. Nella home page, selezionare **+ Crea un agente**.

1. Nella procedura guidata **Crea un agente**, immettere un nome valido per il progetto. 

1. Selezionare **Opzioni avanzate** e specificare le impostazioni seguenti:
    - **Risorsa di Fonderia Azure AI**: *mantenere il nome predefinito*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Area**: selezionare una delle seguenti posizioni:
        * Stati Uniti orientali
        * Francia centrale
        * Corea centrale
        * Europa occidentale
        * Stati Uniti occidentali

1. Selezionare **Crea** e rivedere la configurazione. Attendere il completamento del processo di configurazione.

    >**Nota**: se viene visualizzato un errore di autorizzazione, selezionare il pulsante **Correggi** per aggiungere le autorizzazioni appropriate per continuare.

1. Quando il progetto viene creato, per impostazione predefinita viene visualizzato il playground Agenti nel portale Fonderia Azure AI, simile al seguente:

    ![Screenshot dei dettagli di un progetto di Azure AI nel portale Fonderia di Azure AI.](./media/ai-foundry-project-2.png)
 
1. In una nuova finestra del browser, aprire la [pagina di esplorazione dei servizi di Azure AI](https://ai.azure.com/explore/aiservices).

1. Nella pagina *Servizi di intelligenza artificiale* selezionare il riquadro *Visione e documento* per provare le funzionalità Visione e documento di Azure AI.

## Generare didascalie per un'immagine

Ora verrà utilizzata la funzionalità di didascalia delle immagini di Visione di Azure AI per analizzare le immagini scattate da una fotocamera nell'archivio *Northwind Traders*. Le didascalie delle immagini sono disponibili tramite le funzionalità **Caption** e **Dense Captions**.

1. Nella pagina *Visione e documento* scorrere verso il basso e selezionare **Immagine** in *Visualizza tutte le altre funzionalità di visione*. Selezionare quindi il riquadro **Didascalia immagine**.

    ![Screenshot del riquadro di didascalia delle immagini nella sezione immagine della pagina Visione e documento.](./media/vision-image-captioning-tile.png)

1. Nella pagina **Aggiungi didascalie alle immagini** esaminare la risorsa a cui si è connessi nel sottotitolo **Prova**. Non è necessario apportare modifiche. (*Nota*: se non è stata personalizzata una posizione della risorsa valida in precedenza durante la creazione delle risorse, potrebbe essere richiesto di creare una nuova risorsa dei Servizi di Azure AI che si trova in un'area valida. Sarà necessario creare la nuova risorsa per continuare con il lab.)  

1. Selezionare [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) per scaricare **image-analysis.zip**. Aprire la cartella nel computer e individuare il file denominato **store-camera-1.jpg**, che contiene l'immagine seguente:

    ![Immagine di un genitore che usa una fotocamera del cellulare per scattare una foto di un bambino in un negozio](./media/analyze-images-vision/store-camera-1.jpg)

1. Caricare l'immagine **store-camera-1.jpg** trascinandola nella casella **Trascina i file selezionati qui** o passando al file system.

1. Osservare il testo della didascalia generato, visibile nel pannello **Attributi rilevati** a destra dell'immagine.

    La funzionalità **Caption** fornisce una singola frase in inglese leggibile dall’uomo che descrive il contenuto dell'immagine.

1. Successivamente, usare la stessa immagine per eseguire i **sottotitoli densi**. Tornare alla pagina **Visione e documento** selezionando la freccia *Indietro* nella parte superiore della pagina. Nella pagina *Visione e documento* selezionare la scheda **Immagine** e quindi il riquadro **Didascalie dense**.

    La funzionalità **Didascalie dense** differisce dalla funzionalità **Didascalia** in quanto fornisce più didascalie leggibili per un'immagine, una che descrive il contenuto dell'immagine e altre, ognuna che copre gli oggetti essenziali rilevati nell'immagine. Ogni oggetto rilevato include un rettangolo di selezione, che definisce le coordinate pixel all'interno dell'immagine associata all'oggetto.

1. Passare il puntatore del mouse su una delle didascalie nell'elenco attributi **rilevati** e osservare cosa accade all'interno dell'immagine.

    ![Vengono visualizzate l'immagine e le relative didascalie.](./media/analyze-images-vision/dense-captioning.png)

    Spostare il cursore del mouse sulle altre didascalie nell'elenco e osservare come il rettangolo di selezione viene spostato nell'immagine per evidenziare la parte dell'immagine usata per generare la didascalia.

## Assegnazione di tag alle immagini 

La funzionalità successiva che si proverà è la funzionalità *Estrai tag*. L'estrazione di tag si basa su migliaia di oggetti riconoscibili, tra cui esseri viventi, paesaggi e azioni.

1. Tornare alla pagina *Visione e documento* di Fonderia Azure AI, quindi selezionare la scheda **Immagine** e il riquadro **Estrazione tag comuni**.

1. Aprire la cartella contenente le immagini scaricate e individuare il file denominato **store-image-2.jpg**, simile al seguente:

    ![Immagine di una persona con un carrello della spesa in un supermercato](./media/analyze-images-vision/store-camera-2.jpg)

1. Caricare il file **store-camera-2.jpg**.

1. Esaminare l'elenco dei tag estratti dall'immagine e il punteggio di attendibilità per ognuno nel pannello degli attributi rilevati. Qui il punteggio di attendibilità è la probabilità che il testo per l'attributo rilevato descriva ciò che è effettivamente presente nell'immagine. Si noti nell'elenco dei tag che include non solo oggetti, ma azioni, ad esempio *shopping*, *vendita* e *standing*.

    ![Uno screenshot del pannello rileva attributi in Vision Studio con punteggi di testo e attendibilità visualizzati accanto all'immagine originale.](./media/analyze-images-vision/detect-attributes.png)

## Rilevamento oggetti

In questa attività si usa la funzionalità **Rilevamento oggetti** di Analisi immagini. Rilevamento oggetti rileva ed estrae rettangoli delimitatori basati su migliaia di oggetti riconoscibili e esseri viventi.

1. Tornare alla pagina *Visione e documento* di Fonderia Azure AI, quindi selezionare la scheda **Immagine** e il riquadro **Rilevamento oggetti comuni**.

1. Aprire la cartella contenente le immagini scaricate e individuare il file denominato **store-camera-3.jpg**, simile al seguente:

    ![Immagine di una persona con un carrello per gli acquisti](./media/analyze-images-vision/store-camera-3.jpg)

1. Caricare il file **store-camera-3.jpg**.

1. Nella casella **Attributi rilevati** osservare l'elenco degli oggetti rilevati e i relativi punteggi di attendibilità.

1. Passare il cursore del mouse sugli oggetti nell'elenco **Attributi rilevati** per evidenziare il rettangolo di selezione dell'oggetto nell'immagine.

1. Spostare il dispositivo di scorrimento **Valore soglia** fino a quando non viene visualizzato un valore pari a 70 a destra del dispositivo di scorrimento. Osservare cosa accade agli oggetti nell'elenco. Il dispositivo di scorrimento soglia specifica che devono essere visualizzati solo gli oggetti identificati con un punteggio di attendibilità o una probabilità maggiore della soglia.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1.  Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata. 
1.  Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la [pagina del servizio Visione di Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
