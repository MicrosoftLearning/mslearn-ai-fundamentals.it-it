---
lab:
  title: Estrarre dati con la comprensione dei contenuti nel Portale Fonderia Azure AI
---

# Estrarre dati con la comprensione dei contenuti nel Portale Fonderia Azure AI

Comprensione del Contenuto di Azure AI offre un'analisi multi modale di documenti, file audio, video e immagini per estrarre informazioni.

In questo esercizio, verrà usato il servizio Comprensione del Contenuto di Azure AI nel Portale Fonderia Azure AI, la piattaforma Microsoft per la creazione di applicazioni intelligenti, per estrarre informazioni dalle fatture. 

Questo esercizio richiede circa **25** minuti.

## Creare un progetto di Fonderia Azure AI per la comprensione dei contenuti

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page del Portale Fonderia Azure AI.](./media/ai-foundry-portal.png)

1. Scorrere fino alla fine della pagina e selezionare il riquadro **Esplora i Servizi di Azure AI**.

    ![Screenshot del riquadro Esplora i Servizi di Azure AI.](./media/ai-services.png)

1. Nella pagina Servizi di Azure AI selezionare **Prova Comprensione del Contenuto**.

    ![Screenshot del pulsante Prova Comprensione del Contenuto.](./media/try-content-understanding.png)

1. Nella pagina Comprensione del Contenuto selezionare **Creare un progetto per iniziare**. Nella finestra di dialogo **Crea progetto** selezionare il tipo di risorsa consigliato (**Risorsa di Fonderia Azure AI**):

    ![Screenshot dei risultati dell'analisi.](./media/resource-type.png)

1. Nella pagina **Avanti** immettere un nome valido per il progetto. Selezionare quindi **Opzioni avanzate** e specificare le impostazioni seguenti:
    - **Risorsa di Fonderia Azure AI**: *nome valido per la risorsa di Fonderia Azure AI*
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*
    - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
    - **Area**: Selezionare una delle località seguenti\*:
        * Stati Uniti occidentali
        * Svezia centrale
        * Australia orientale

    \**Al momento della stesura di questo articolo, Comprensione del Contenuto è supportato in queste aree.*

    ![Screenshot di Impostazioni progetto.](./media/content-project-settings.png)

1. Selezionare **Crea**. Attendere il completamento del processo di configurazione. L'operazione potrebbe richiedere alcuni minuti.

## Estrarre informazioni da una fattura

1. Scaricare [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) da `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Nella pagina Comprensione del Contenuto selezionare la scheda **Prova** e quindi selezionare il riquadro **Estrazione dati fattura**.

    ![Screenshot della pagina "Prova" di Comprensione del Contenuto.](./media/content-understanding-invoice.png)

    Viene fornita una fattura di esempio.

1. Selezionare la fattura di esempio e usare il pulsante **Esegui analisi** per estrarne le informazioni. Al termine dell'analisi, visualizzare i risultati.

    ![Screenshot dei risultati dell'analisi della fattura di esempio.](./media/sample-invoice-analysis.png)

1. Usare il collegamento **Sfoglia elenco file** per caricare il documento **contoso-invoice-1.pdf** scaricato in precedenza ed eseguire l'analisi su tale file.

    ![Screenshot dei risultati dell'analisi della fattura Contoso.](./media/contoso-invoice-analysis.png)

    Si noti che l'analizzatore di Comprensione del Contenuto è in grado di estrarre informazioni dalla fattura, anche se è formattata in modo differente dall'esempio.

1. Nel riquadro a destra in cui vengono visualizzati i campi estratti, visualizzare la scheda **Risultato** per vedere la risposta JSON che verrà inviata a un'applicazione client. Uno sviluppatore scriverà codice per elaborare questa risposta ed eseguire un'operazione con i campi estratti.

    ![Screenshot dei risultati dell'analisi della fattura Contoso.](./media/invoice-analysis-json.png)

## Eseguire la pulizia

Al termine del lavoro con il servizio di comprensione dei contenuti, è necessario eliminare le risorse create in questo esercizio per evitare di incorrere in costi di Azure non necessari.

- Nel portale di Azure eliminare il gruppo di risorse creato in questi esercizi.
