---
lab:
  title: Estrarre dati con la comprensione dei contenuti nel Portale Fonderia Azure AI
---

# Estrarre dati con la comprensione dei contenuti nel Portale Fonderia Azure AI

**Comprensione del Contenuto di Azure AI (anteprima)** usa l'intelligenza artificiale generativa per elaborare il contenuto di molti tipi (documenti, immagini, video e audio) in un formato di output definito dall'utente.

In questo esercizio, verrà utilizzata la Comprensione del Contenuto di Azure AI nel Portale Fonderia Azure AI, la piattaforma Microsoft per la creazione di applicazioni intelligenti, per riconoscere i dati da una fattura. 

Questo esercizio richiede circa **25** minuti.

## Creare un progetto di Fonderia Azure AI e un'attività di comprensione dei contenuti

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page di Fonderia Azure AI con l'opzione Crea un agente selezionata.](./media/azure-ai-foundry-home-page.png)

1. In una nuova finestra del browser, aprire la [pagina di esplorazione dei servizi di Azure AI](https://ai.azure.com/explore/aiservices).

1. Nella pagina *Servizi IA* selezionare il riquadro *Prova comprensione dei contenuti*.

1. Selezionare **Selezionare o creare un progetto per iniziare**. 

1. Selezionare **+ Crea un progetto**.

1. Nella procedura guidata immettere un nome valido per il progetto. 

1. Selezionare **Opzioni avanzate** e specificare le impostazioni seguenti:
    - **Risorsa di Fonderia Azure AI**: *mantenere il nome predefinito*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Area**: selezionare una delle seguenti posizioni:
        * Stati Uniti occidentali
        * Svezia centrale
        * Australia orientale

1. Selezionare **Crea**. Attendere il completamento del processo di configurazione. L'operazione potrebbe richiedere alcuni minuti.

    >**Nota**: se viene visualizzato un errore di autorizzazione, selezionare il pulsante **Correggi** per aggiungere le autorizzazioni appropriate per continuare.

1. Quando il progetto viene creato, per impostazione predefinita verrà visualizzata la finestra di creazione delle attività di comprensione dei contenuti. Usare le impostazioni seguenti per creare un'attività di comprensione dei contenuti:
    - **Nome attività**: `contoso-invoice`
    - **Descrizione**: `An invoice analysis task`
    - *Selezionare Analisi del contenuto di un singolo file*
    - **Impostazioni avanzate**: *mantenere l'impostazione predefinita*.

1. Selezionare **Crea** e attendere che venga creata l’attività. 

1. Selezionare l'attività **contoso-invoice**. 

## Analizzare una fattura con la Comprensione del Contenuto di Azure AI in Fonderia Azure AI 

Si supponga di voler estrarre dati da molte fatture e inserire i dati in un database. È possibile usare Comprensione del contenuto di Azure AI per analizzare una fattura e creare un analizzatore personalizzato in grado di analizzare altre fatture simili. Per iniziare, definire lo schema.

#### Definire lo schema 

1. Nella pagina *Definisci schema* è possibile aggiungere file di test. Scaricare [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) da `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Caricare il file nella pagina **Definisci schema**. Selezionare il modello **Estrazione dati fattura**. Il modello di estrazione dei dati della fattura include campi dati pre-selezionati che l'analizzatore proverà a rilevare. 

    ![Screenshot della pagina Definisci schema nello strumento di comprensione del contenuto.](./media/content-understanding/define-schema.png)

1. Selezionare **Crea**. Ora è possibile modificare lo schema aggiungendo o eliminando campi. Al termine della revisione dei campi, selezionare **Salva**.

    ![Sceenshot della pagina Definisci schema dopo la selezione della creazione.](./media/content-understanding/define-schema-2.png)

1. Attendere il completamento dell'analisi. L'operazione potrebbe richiedere alcuni istanti.

#### Testare l'analizzatore 

1. Al termine dell'analisi, sarà possibile vedere come l'analizzatore è stato eseguito nella pagina *Analizzatore di test*. Esaminare la scheda *Campi*. *Nota*: potrebbe essere necessario espandere la finestra per visualizzare i risultati completi. Questi dati sono allineati ai dati visualizzati nella fattura? 
    ![Screenshot della pagina Analizzatore di test con la scheda dei risultati del campo evidenziata.](./media/content-understanding/test-analyzer-fields.png)

1. Si noti il *punteggio di attendibilità* accanto a ogni campo. Il punteggio di attendibilità rappresenta la probabilità che i risultati del modello siano accurati. I risultati con punteggi di attendibilità più vicini al 100% indicano maggiore attendibilità nella stima.

1. Esaminare la scheda *Risultati*. Le stesse informazioni visualizzate nella scheda Campi si trovano nella scheda dei risultati in JSON. Il codice JSON mostra l'aspetto delle informazioni quando vengono inviate da e verso un'applicazione client. 

    ![Screenshot della pagina analizzatore di test con la scheda dei risultati evidenziata.](./media/content-understanding/test-analyzer-result.png)

1. Il servizio di comprensione dei contenuti deve aver identificato correttamente il testo che corrisponde ai campi nello schema. In caso contrario, è possibile usare la pagina *Dati etichetta* per caricare un altro modulo di esempio e identificare in modo esplicito il testo corretto per ogni campo. Quando si è soddisfatti del grado di rilevamento dei dati nella fattura da parte dell'analizzatore, selezionare la scheda **Elenco analizzatori**. 

#### Creare l'analizzatore 

Ora che è stato eseguito il training di un modello per estrarre campi da una fattura campione, è possibile creare un analizzatore da usare con moduli simili. Creando un analizzatore, è possibile distribuire il modello e usarlo per automatizzare altre attività relative alle fatture.

1. Nella scheda *Elenco analizzatori* selezionare **+ Crea analizzatore**. Immettere gli elementi seguenti: 
    - **Nome**: `invoice-analyzer`
    - **Descrizione**: `An invoice analyzer`

    ![Screenshot della pagina Crea analizzatore](./media/content-understanding/build-analyzer.png)

1. Selezionare **Compila**. Attendere che il nuovo analizzatore sia pronto (usare il pulsante Aggiorna per controllare). L'analizzatore usa un modello predittivo basato sullo schema definito e testato nei passaggi precedenti. 
1. Provare ora a testare l'analizzatore creato. Scaricare una fattura diversa da Contoso [contoso-invoice-2.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf) da `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf`.
1. Tornare alla pagina *Elenco analizzatori* e selezionare il collegamento invoice-analyzer. Verranno visualizzati i campi definiti nello schema dell'analizzatore.
1. Nella pagina invoice-analyzer selezionare *Test*.
1. Usare il pulsante **+ Carica file di test** per caricare *contoso-receipt-2.pdf*. Selezionare **Esegui analisi** per estrarre i dati dei campi dal modulo di test. Esaminare i risultati del test.

    ![Screenshot dei risultati del test per l'analizzatore creato.](./media/content-understanding/build-analyzer-2.png)

1. Selezionare la scheda *Esempio di codice*. Cercare l'*endpoint* nel codice. Nella fase del processo *Crea analizzatore* è stato distribuito il modello di comprensione del contenuto in un endpoint. L'endpoint può essere usato nel codice simile a quello visualizzato nell'esempio per incorporare il modello in un processo ripetibile in un'applicazione.  

    ![Screenshot dell'esempio di codice per l'analizzatore creato.](./media/content-understanding/code-example.png)

## Eseguire la pulizia

Al termine del lavoro con il servizio di comprensione dei contenuti, è necessario eliminare le risorse create in questo esercizio per evitare di incorrere in costi di Azure non necessari.

- Nel Portale Fonderia Azure AI passare al progetto contoso-receipt ed eliminarlo.
- Nel portale di Azure eliminare il gruppo di risorse creato in questi esercizi.
