---
lab:
  title: Estrarre i dati dei moduli in Document Intelligence Studio
---

# Estrarre i dati dei moduli in Document Intelligence Studio

Intelligence sui documenti di Intelligenza artificiale di Azure è in grado di analizzare ed estrarre informazioni da moduli e documenti, quindi identificare i nomi e i dati dei campi. 

In che modo Document Intelligence si basa sul riconoscimento ottico dei caratteri (OCR)? Mentre OCR può leggere documenti stampati o scritti a mano, OCR estrae testo in un formato non strutturato che è difficile archiviare in un database o analizzare. L'intelligenza dei documenti ha senso dei dati non strutturati acquisendo la struttura del testo, ad esempio coppie chiave/valore e informazioni nelle tabelle. 

In questo esercizio si esaminerà un modello predefinito in Intelligence documenti sottoposto a training per riconoscere i dati per le ricevute. 

> **NOTA Azure** AI Document Intelligence è il nuovo nome per Azure Riconoscimento modulo. È comunque possibile visualizzare Riconoscimento modulo di Azure nel portale di Azure o in Document Intelligence Studio.

## Creare una *risorsa di Document Intelligence*

È possibile usare Document Intelligence per intelligenza artificiale di Azure creando una *risorsa di Document Intelligence* o una *risorsa dei servizi* di intelligenza artificiale di Azure. In questo esercizio si creerà *una risorsa di Document Intelligence* , se non ne è già disponibile una.

1. In un'altra scheda del browser aprire [Document Intelligence Studio](https://formrecognizer.appliedai.azure.com/studio), accedendo con l'account Microsoft.
1. Selezionare **Impostazioni** e selezionare la **scheda Risorsa** . Selezionare **Crea una nuova risorsa**.
1. Nella finestra di dialogo Crea risorsa immettere quanto segue:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Nome nuova risorsa**: *immettere un nome* univoco.
    - **Località**: *selezionare un'area. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2".*
    - **** Piano tariffario: *fo gratuito (se disponibile, in caso contrario selezionare SO standard).*
1. Selezionare **Continua** e quindi **Fine**. Attendere che la risorsa venga distribuita.

    >**Nota** Se la risorsa non è ancora visualizzata, potrebbe essere necessario aggiornare **** la pagina.

Mantenere aperto Document Intelligence Studio.

## Analizzare una ricevuta in Document Intelligence Studio

A questo punto è possibile analizzare una ricevuta per la società fittizia di vendita al dettaglio northwind Traders.

1. Selezionare questa opzione [****https://aka.ms/mslearn-receipt](https://aka.ms/mslearn-receipt) per scaricare un documento di esempio nel computer. Apri la cartella . 
1. Selezionare **Document Intelligence Studio** per tornare alla **pagina Introduzione a Document Intelligence Studio** e in Ricevute selezionare **Prova**.
1. Nell'elenco a discesa predefinito assicurarsi che **sia** selezionata l'opzione Ricevute.
1. Selezionare **Sfoglia per i file** e passare alla cartella in cui è stata salvata l'immagine. Selezionare l'immagine della ricevuta e quindi **Apri**. L'immagine viene visualizzata sul lato sinistro dello schermo.

    ![Screenshot di una ricevuta northwind.](media/document-intelligence/receipt.jpg)

1. A destra selezionare **Esegui analisi**.
1. Quando l'analisi è stata eseguita, vengono restituiti i risultati. Si noti che il servizio ha riconosciuto campi dati specifici, ad esempio il nome del commerciante, l'indirizzo, il numero di telefono e la data e l'ora della transazione, nonché gli elementi di riga, il subtotale, l'imposta e gli importi totali. Accanto a ogni campo è una probabilità percentuale che il campo sia corretto.

In questo esercizio è stato usato Document Intelligence Studio per creare una risorsa di Document Intelligence. È stato quindi usato il servizio per analizzare una ricevuta. Dai risultati restituiti, si è visto in che modo l'intelligence dei documenti è stata in grado di identificare campi specifici, consentendo l'elaborazione più semplice dei dati dei documenti quotidiani. Prima di chiudere Document Intelligence Studio, perché non provare alcune delle ricevute di esempio, incluse quelle in lingue diverse?

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare le risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il [portale di Azure]( https://portal.azure.com) e selezionare il gruppo di risorse contenente la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina** e quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Questo esercizio ha dimostrato solo alcune delle funzionalità del servizio intelligence sui documenti di intelligenza artificiale. Per altre informazioni sulle operazioni che è possibile eseguire con questo servizio, vedere la [pagina Intelligence sui](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0) documenti.
