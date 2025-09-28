---
lab:
  title: Analizzare le immagini nel portale Fonderia Azure AI
---

# Analizzare le immagini nel portale Fonderia Azure AI

**Visione di Azure AI** include numerose funzionalità per comprendere il contenuto e il contesto delle immagini ed estrarre informazioni dalle immagini. In questo esercizio, viene utilizzato Visione di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per analizzare le immagini usando le esperienze try-it-out predefinite. 

Si supponga che l'azienda di vendita al dettaglio fittizia *Northwind Traders* abbia deciso di implementare un "negozio intelligente", in cui i servizi di intelligenza artificiale mantengono monitorato il negozio per identificare i clienti che richiedono assistenza e indirizzare i dipendenti per aiutarli. Usando Visione di Azure AI, le immagini scattate da fotocamere in tutto il negozio possono essere analizzate per fornire descrizioni significative di ciò che illustrano.

Questo esercizio richiede circa **20** minuti.

## Scaricare ed estrarre file di immagine

1. Scaricare **[image-analysis.zip](https://aka.ms/mslearn-images-for-analysis)** da `https://aka.ms/mslearn-images-for-analysis`.
1. Estrarre il file ZIP scaricato in una cartella nel computer.

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page del Portale Fonderia Azure AI.](./media/ai-foundry-portal.png)

1. Scorrere fino alla fine della pagina e selezionare il riquadro **Esplora i Servizi di Azure AI**.

    ![Screenshot del riquadro Esplora i Servizi di Azure AI.](./media/ai-services.png)

1. Nella pagina Servizi di Azure AI selezionare il riquadro **Visione e documento**.

    ![Screenshot del riquadro Visione e documento.](./media/vision-tile.png)

1. Nella pagina **Visione e documento** visualizzare la scheda **Immagine** e selezionare il riquadro **Didascalia immagine**.

    ![Screenshot del riquadro Didascalia immagine.](./media/image-captioning-tile.png)

1. Nel riquadro **Aggiungi didascalie alle immagini** usare il pulsante **Selezionare un hub** per **creare un nuovo hub** con le impostazioni seguenti:
    - **Nome hub**: *Immettere un nome valido per l'hub.*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Località**: *Selezionare una delle località seguenti*/*:
        - Stati Uniti orientali
        - Francia centrale
        - Corea centrale
        - Europa occidentale
        - Stati Uniti occidentali
    - **Connetti i Servizi di Azure AI**: *Creare una nuova risorsa di Servizi di Azure AI con un nome valido*
    - **Connettere Azure AI Search**: ignorare la connessione

    \**Al momento della scrittura di questo documento, Visione di Azure AI è supportato negli hub in queste aree*.

1. Quando viene creato l'hub, verrà richiesto di creare un progetto. Immettere un nome di progetto appropriato e selezionare **Crea progetto**.

## Generare didascalie per un'immagine

Ora verrà utilizzata la funzionalità di didascalia delle immagini di Visione di Azure AI per analizzare le immagini scattate da una fotocamera nell'archivio *Northwind Traders*. Le didascalie delle immagini sono disponibili tramite le funzionalità **Caption** e **Dense Captions**.

1. Nel riquadro attività a sinistra selezionare **Servizi AI**.

    *Ora è necessario ripetere i passaggi usati in precedenza per tornare all'interfaccia di didascalia delle immagini e usare il nuovo progetto basato su hub.*

1. Nella pagina **Servizi AI** selezionare il riquadro **Visione e documento**. Nella scheda **Immagine** della pagina **Visione e documento** selezionare quindi il riquadro **Didascalia immagine**.

1. Nella pagina **Aggiungi didascalie alle immagini** nel menu di selezione *Servizi di Azure AI connessi* assicurarsi che sia stata selezionata la risorsa di Servizi di Azure AI creata nell'hub.

1. Usare il collegamento **Cerca un file** per caricare l'immagine **store-camera-1.jpg** dai file scaricati ed estratti in precedenza.

1. Osservare il testo della didascalia generato, visibile nel pannello **Attributi rilevati** a destra dell'immagine.

    ![Screenshot della pagina Aggiungi didascalie alle immagini con un'immagine analizzata.](./media/image-captioning.png)

    La funzionalità **Caption** fornisce una singola frase in inglese leggibile dall’uomo che descrive il contenuto dell'immagine.

1. Successivamente, usare la stessa immagine per eseguire i **sottotitoli densi**. Tornare alla pagina **Visione e documento** selezionando la freccia **&larr;** *indietro* nella parte superiore della pagina, quindi nella scheda **Immagine**, della pagina **Visione e documento** selezionare il riquadro **Didascalie compatte**.

    La funzionalità **Didascalie dense** differisce dalla funzionalità **Didascalia** in quanto fornisce più didascalie leggibili per un'immagine, una che descrive il contenuto dell'immagine e altre, ognuna che copre gli oggetti essenziali rilevati nell'immagine. Ogni oggetto rilevato include un rettangolo di selezione, che definisce le coordinate pixel all'interno dell'immagine associata all'oggetto.

1. Caricare di nuovo l'immagine **store-camera-1.jpg** e visualizzare i risultati delle didascalie compatte.

    ![Screenshot dei risultati delle didascalie compatte.](./media/dense-captioning.png)

    Passare il puntatore del mouse su una delle didascalie nell'elenco **Attributi rilevati** e osservare che viene generata una didascalia per ogni oggetto rilevato nell'immagine.

## Assegnazione di tag alle immagini 

La funzionalità successiva che si proverà è la funzionalità *Estrai tag*. L'estrazione di tag si basa su migliaia di oggetti riconoscibili, tra cui esseri viventi, paesaggi e azioni.

1. Tornare alla pagina **Visione e documento** selezionando la freccia **&larr;** *indietro* nella parte superiore della pagina. Nella scheda **Immagine** della pagina **Visione e documento** selezionare il riquadro **Estrazione di tag comuni**.
1. Caricare il file **store-camera-2.jpg** dalla cartella estratta in precedenza.
1. Esaminare l'elenco dei tag estratti dall'immagine e il punteggio di attendibilità per ognuno nel pannello degli attributi rilevati. Qui il punteggio di attendibilità è la probabilità che il testo per l'attributo rilevato descriva ciò che è effettivamente presente nell'immagine. Si noti nell'elenco dei tag che include non solo oggetti, ma azioni, ad esempio *shopping*, *vendita* e *standing*.

    ![Uno screenshot del pannello rileva attributi in Vision Studio con punteggi di testo e attendibilità visualizzati accanto all'immagine originale.](./media/analyze-images-vision/detect-attributes.png)

## Rilevamento oggetti

In questa attività si usa la funzionalità **Rilevamento oggetti** di Analisi immagini. Rilevamento oggetti rileva ed estrae rettangoli delimitatori basati su migliaia di oggetti riconoscibili e esseri viventi.

1. Tornare alla pagina **Visione e documento** selezionando la freccia **&larr;** *indietro* nella parte superiore della pagina. Nella scheda **Immagine** selezionare il riquadro **Rilevamento oggetti comuni**.

1. Caricare il file **store-camera-3.jpg**.

1. Nella casella **Attributi rilevati** osservare l'elenco degli oggetti rilevati e i relativi punteggi di attendibilità.

    ![Screenshot dei risultati delle didascalie compatte.](./media/object-detection.png)

1. Provare a rilevare gli oggetti in **store-camera-4.jpg**

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata. 
1. Selezionare **Elimina gruppo di risorse** e **immettere il nome del gruppo di risorse** per confermare. Il gruppo di risorse viene quindi eliminato.

## Altre informazioni

Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la [pagina del servizio Visione di Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
