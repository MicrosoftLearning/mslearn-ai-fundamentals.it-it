---
lab:
  title: Estrarre dati dai documenti nel portale Fonderia di Azure AI
---

# Estrarre dati dai documenti nel portale Fonderia di Azure AI

Il servizio **Informazioni sui documenti di Azure AI** consente all'utente di analizzare ed estrarre informazioni da moduli e documenti, quindi di identificare i nomi e dati dei campi. 

In che modo Informazioni sui documenti si basa sul riconoscimento ottico dei caratteri (OCR)? Il riconoscimento ottico dei caratteri (OCR) è in grado di leggere documenti stampati o scritti a mano, ma estrae testo in un formato non strutturato che è difficile archiviare in un database o analizzare. Informazioni sui documenti ricava il senso dei dati non strutturati acquisendo la struttura del testo, ad esempio i campi dei dati e le informazioni nelle tabelle. 

In questo esercizio, verranno utilizzati i modelli predefiniti di Informazioni sui documenti di Azure AI nel portale Fonderia di Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per riconoscere i dati da una ricevuta. 

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere eventuali suggerimenti o riquadri di avvio rapido che vengono aperti al primo accesso. 

1. Nel browser, passare a `https://ai.azure.com/managementCenter/allResources` e selezionare **Crea**. Scegliere quindi l'opzione per creare una nuova *risorsa Hub IA*.

1. Nella procedura guidata *Creare un progetto*, immettere un nome valido per il progetto e, se viene suggerito un hub esistente, selezionare l'opzione per crearne uno *nuovo*. 

1. Espandere *Opzioni avanzate* per specificare le impostazioni seguenti per il progetto:
    - **Sottoscrizione**: sottoscrizione di Azure.
    - **Gruppo di risorse**: creare o selezionare un gruppo di risorse
    - **Area**: selezionare una delle seguenti posizioni:
        * Stati Uniti orientali
        * Francia centrale
        * Corea centrale
        * Europa occidentale
        * Stati Uniti occidentali

    Attendere la creazione del progetto o dell'hub.

1. Quando il progetto viene creato, verrà visualizzata una pagina *Panoramica* dei dettagli del progetto. Nel menu a sinistra selezionare **Servizi di intelligenza artificiale**. 

1. Nella pagina *Servizi di intelligenza artificiale* selezionare il riquadro *Visione e documento* per provare le funzionalità Visione e documento di Azure AI.

    ![Screenshot del riquadro Visione e Documento in Fonderia Azure AI.](./media/vision-document-tile.png)

## Analizzare una ricevuta con Informazioni sui documenti di Azure AI in Fonderia Azure AI 

A questo punto è possibile analizzare una ricevuta per la società fittizia di vendita al dettaglio Northwind Traders.

1. Nella pagina *Visione e documento* scorrere verso il basso e selezionare **Documento**. In *Modelli predefiniti per documenti specifici* selezionare il riquadro **Ricevute**.

1. Nell'elenco a discesa in *Prova*, notare che la risorsa dei Servizi di Azure AI è selezionata. Lasciare invariato.

1. Nel computer usare [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) per aprire un'immagine di esempio di ricevuta. Salvare il file nella cartella Download o sul desktop. 
 
1. In Fonderia Azure AI, nella pagina *Ricevute*, selezionare **Esplora file** e passare alla cartella in cui è stata salvata l'immagine. Selezionare l'immagine della ricevuta e quindi **Apri**. L'immagine appare sul lato sinistro dello schermo.

    ![Screenshot di una ricevuta Northwind.](media/document-intelligence/receipt.jpg)

1. Sulla destra selezionare **Esegui analisi**.

1. Quando l'analisi è stata eseguita, vengono restituiti i risultati. Si noti che il servizio ha riconosciuto campi dati specifici, ad esempio il nome del fornitore, l'indirizzo, il numero di telefono, la data e l'ora della transazione, nonché gli elementi di riga, il subtotale, le imposte e gli importi totali. Accanto a ogni campo vi è una probabilità percentuale che il campo sia corretto.

    ![Screenshot del risultato dell'analisi delle ricevute nel portale Fonderia Azure AI, che mostra i rettangoli di selezione intorno ai campi dati e il testo in tali campi estratti.](media/receipt-lab-result.png)

In questo esercizio è stato usato il modello di ricevute predefinito di Informazioni sui documenti di Azure AI nel portale Fonderia Azure AI. Dai risultati restituiti, si è visto in che modo Informazioni sui documenti è stata in grado di identificare campi specifici, consentendo di elaborare più agevolmente i dati dei documenti quotidiani. Prima di chiudere la demo, perché non provare alcune delle ricevute di esempio, incluse quelle in lingue diverse?

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Informazioni sui documenti di Azure AI. Per ulteriori informazioni su ciò che si può fare con questo servizio, consultare la pagina [Informazioni sui documenti](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
