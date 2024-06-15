---
lab:
  title: Estrarre i dati dei moduli in Informazioni sui documenti di Studio
---

# Estrarre i dati dei moduli in Informazioni sui documenti di Studio

Informazioni sui documenti di Azure AI è in grado di analizzare ed estrarre informazioni da moduli e documenti, quindi identificare i nomi e dati dei campi. 

In che modo Informazioni sui documenti si basa sul riconoscimento ottico dei caratteri (OCR)? Il riconoscimento ottico dei caratteri (OCR) è in grado di leggere documenti stampati o scritti a mano, ma estrae testo in un formato non strutturato che è difficile archiviare in un database o analizzare. Informazioni sui documenti ricava il senso dei dati non strutturati acquisendo la struttura del testo, ad esempio coppie chiave/valore e informazioni nelle tabelle. 

In questo esercizio si prenderà in esame un modello predefinito in Informazioni sui documenti che è sottoposto a training per riconoscere i dati per le ricevute. 

> **NOTA**Informazioni sui documenti di Azure AI è il nuovo nome per Riconoscimento modulo di Azure. È comunque possibile visualizzare Riconoscimento modulo di Azure nel portale di Azure o Informazioni sui documenti di Studio.

## Creare risorsa di *Informazioni sui documenti*

È possibile usare Informazioni sui documenti di Azure AI creando o una risorsa di *Informazioni sui documenti* o una risorsa di *Servizi di Azure AI*. In questo esercizio si creerà una risorsa di *Informazioni sui documenti*, se non se ne ha già una.

1. In un'altra scheda del browser aprire [Informazioni sui documenti di Studio](https://formrecognizer.appliedai.azure.com/studio), accedendo con l’account Microsoft.
1. Selezionare **Impostazioni** e selezionare la scheda **Risorsa**. Selezionare **Crea una nuova risorsa**.
1. Nella finestra di dialogo Crea risorsa, immettere quanto segue:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Nome nuova risorsa**: *Immetti un nome univoco*.
    - **Località**: *Selezionare un'area geografica. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2"*.
    - **Piano tariffario**: *FO gratuito (se disponibile, in caso contrario selezionare SO Standard)*.
1. Selezionare **Continua** e quindi **Fine**. Attendere che la risorsa venga distribuita.

    >**Nota** Se la risorsa non è ancora visualizzata, potrebbe essere necessario **Aggiornare** la pagina.

Mantenere aperto Informazioni sui documenti di Studio.

## Analizzare una ricevuta in Informazioni sui documenti di Studio

A questo punto è possibile analizzare una ricevuta per la società fittizia di vendita al dettaglio Northwind Traders.

1. Selezionare [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) per scaricare un documento di esempio nel proprio computer. Apri la cartella . 
1. Selezionare **Informazioni sui documenti di Studio** per tornare alla pagina **Attività iniziali di Informazioni sui documenti di Studio** e, in Ricevute, selezionare **Prova**.
1. Nell'elenco a discesa predefinito assicurarsi che **Ricevute** sia selezionato.
1. Selezionare **Esplora file** e passare alla cartella in cui è stata salvata l'immagine. Selezionare l'immagine della ricevuta e quindi **Apri**. L'immagine appare sul lato sinistro dello schermo.

    ![Screenshot di una ricevuta Northwind.](media/document-intelligence/receipt.jpg)

1. Sulla destra selezionare **Esegui analisi**.
1. Quando l'analisi è stata eseguita, vengono restituiti i risultati. Si noti che il servizio ha riconosciuto campi dati specifici, ad esempio il nome del fornitore, l'indirizzo, il numero di telefono, la data e l'ora della transazione, nonché gli elementi di riga, il subtotale, le imposte e gli importi totali. Accanto a ogni campo vi è una probabilità percentuale che il campo sia corretto.

In questo esercizio è stato usato Informazioni sui documenti di Studio per creare una risorsa di Informazioni sui documenti. È stato quindi usato il servizio per analizzare una ricevuta. Dai risultati restituiti, si è visto in che modo Informazioni sui documenti è stata in grado di identificare campi specifici, consentendo di elaborare più agevolmente i dati dei documenti quotidiani. Prima di chiudere Informazioni sui documenti di Studio, perché non provare alcune delle ricevute di esempio, incluse quelle in lingue diverse?

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio Informazioni sui documenti di Azure AI. Per ulteriori informazioni su ciò che si può fare con questo servizio, consultare la pagina [Informazioni sui documenti](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
