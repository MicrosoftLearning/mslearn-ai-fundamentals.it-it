---
lab:
  title: Esplorare Copilot in Microsoft Edge
---
# Esplorare Microsoft Copilot in Microsoft Edge

In questo esercizio si esamineranno alcuni dei modi in cui Microsoft Copilot può usare l'intelligenza artificiale generativa per migliorare la produttività durante la creazione di nuovi contenuti. Nello scenario di questo esercizio, si inizierà con alcune note di alto livello alla base di un'idea di business e si userà Copilot in Microsoft Edge per sviluppare un piano aziendale e una presentazione per potenziali investitori.

Il completamento di questo esercizio richiede circa **40** minuti.

> **Nota**: Questo esercizio presuppone che l'utente disponga di un account [ Microsoft personale](https://signup.live.com) (ad esempio un account outlook.com) con cui si è connessi a [Microsoft Edge](https://www.microsoft.com/edge/download) nel computer.

## Usare Copilot per esplorare un documento e fare ricerca per un'idea

Per iniziare l'esplorazione dell'intelligenza artificiale generativa, si userà Microsoft Copilot in Edge per esaminare un documento esistente ed estrarre alcune informazioni dettagliate.

1. In Microsoft Edge, passare a [OneDrive](https://onedrive.live.com) all'indirizzo `https://onedrive.live.com` e accedere usando l'account Microsoft personale, chiudendo eventuali messaggi o offerte di benvenuto visualizzati.
1. In un'altra scheda del browser, aprire il documento [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) da `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. Quindi, quando il documento viene aperto in Edge, selezionare l'opzione **Salva una copia in OneDrive** e salvare il documento nella cartella **Documenti** in OneDrive. Il documento verrà quindi aperto automaticamente in Microsoft Word online.

    > **Suggerimento**: Se non viene visualizzata l'opzione per salvare una copia del file in OneDrive, scaricarla nel computer locale. Quindi, in OneDrive aprire la cartella **Documenti** e usare il pulsante **+Aggiungi nuovo** per caricare il **file business Idea.docx** dal computer locale in OneDrive.

1. Visualizzare il testo in **Business Idea.docx**, che descrive alcune idee di alto livello per un'impresa di pulizie a New York City.
1. Usare l'icona **Copilot** sulla barra degli strumenti Edge per aprire il riquadro Copilot, come illustrato di seguito:

    ![Screenshot del riquadro Copilot in Microsoft Edge.](./media/generative-ai/edge-copilot.png)

1. Nel riquadro Copilot, scorrere verso il basso per visualizzare tutto il contenuto in base alle esigenze e assicurarsi che la scheda **Chat** sia selezionata e che lo stile della conversazione sia impostato su **Più Bilanciato**. In questo modo, Copilot risponde con un equilibrio di creatività e precisione dei fatti.
1. Nella casella di chat, nella parte inferiore del riquadro Copilot, immettere il prompt seguente:

    ```
    What is this document about?
    ```

    Se richiesto, verificare di voler consentire a Copilot di accedere alla pagina.

1. Esaminare la risposta di Copilot, che dovrebbe riepilogare i punti principali del documento, come illustrato di seguito:

    ![Screenshot del riquadro Copilot con una risposta.](./media/generative-ai/copilot-response.png)

    > **Nota**: La risposta specifica può variare.

1. Immettere il prompt seguente:

    ```
    How do I go about setting up a business in New York?
    ```

1. Esaminare la risposta, che dovrebbe contenere alcuni consigli e collegamenti alla risorsa per iniziare a creare un'azienda a New York e può includere alcuni suggerimenti per ottenere altre informazioni.

    > **Importante**: La risposta generata dall'intelligenza artificiale si basa su informazioni pubbliche sul Web. Anche se può essere utile per aiutare a comprendere i passaggi necessari per creare un'azienda, non è garantito che sia accurato al 100% e non sostituisce la necessità di consigli professionali!

## Usare Copilot per creare contenuti per un piano aziendale

Ora che hai fatto alcune ricerche iniziali, Copilot ti aiuterà a sviluppare un piano aziendale per la tua impresa di pulizie.

1. Con il **documento Business Idea.docx** ancora aperto in Microsoft Edge, nel riquadro Copilot, immettere il prompt seguente:

    ```
    Suggest a name for my cleaning business
    ```

1. Esaminare i suggerimenti e selezionare un nome per l'impresa di pulizie (o continuare a chiedere di trovare un nome desiderato).
1. Immettere il prompt seguente, sostituendo *Contoso Cleaning* con il nome della società desiderato:

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

1. Esaminare la risposta e nell'output usare l'icona **Copia** (&#128461;) per copiarla negli Appunti. Selezionare quindi tutto il testo nel documento **Business Ideas.docx** e incollare il testo copiato nel documento per sostituirlo. Infine, riordinare il testo incollato sostituendo il testo iniziale della risposta (in cui Copilot ha riconosciuto l'istruzione) con un titolo per il nome dell'impresa di pulizie. Si dovrebbe ottenere, alla fine, con un documento di piano aziendale, simile al seguente:

    ![Screenshot di un documento di Word con un piano aziendale generato da Copilot.](./media/generative-ai/generated-content.png)

1. Nel riquadro Copilot, immettere il prompt seguente:

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```

1. Esaminare la risposta, che dovrebbe presentare quattro opzioni per un logo creato da Microsoft Designer.
1. Usare più richieste per eseguire l'iterazione del design (ad esempio, `Make it green and blue`) fino a quando non si ottiene un logo con cui si è soddisfatti.
1. Fare clic con il pulsante destro del mouse sul design preferito e copiarlo negli Appunti. Incollarlo quindi nella parte superiore del documento del piano aziendale, come illustrato di seguito:

    ![Screenshot di un documento di Word con un'immagine generata da Copilot.](./media/generative-ai/generated-image.png)

1. Chiudere la scheda Microsoft Word e tornare alla cartella **Documenti** in OneDrive.

## Usare Copilot per creare contenuto per una presentazione

Con l'aiuto di Copilot, è stata creata una bozza di piano aziendale per l'idea di creare un'impresa di pulizie. Ora, avrai bisogno di una presentazione efficace per convincere un investitore a prestarti i finanziamenti per avviare l'attività.

1. Nella cartella **Documenti** in OneDrive, aggiungere una nuova **presentazione PowerPoint**.

    Se la **finestra di progettazione** viene aperta automaticamente, chiuderla.

1. Nella diapositiva di titolo della presentazione, immettere il nome dell'impresa di pulizie come titolo e `Investor Opportunity` come sottotitolo.
1. Aggiungere una nuova diapositiva usando il layout **Due contenuti** (che include un titolo e due segnaposto per il contenuto).
1. Modificare il titolo della diapositiva in `Benefits of Hiring a Commercial Cleaner`.
1. Nel riquadro Copilot, immettere il prompt seguente:

    ```
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Copiare la risposta di Copilot negli Appunti e incollarla nel segnaposto del contenuto a sinistra. Eliminare quindi la frase iniziale che riconosce la richiesta e riformattare il testo nel segnaposto fino a quando non si è soddisfatti.
1. Nel riquadro Copilot, immettere il prompt seguente:

    ```
    Create a photorealistic image of a clean office.
    ```

1. Quando Copilot ha generato un'immagine corretta, copiarla negli Appunti e incollarla nel segnaposto del contenuto a destra della diapositiva.

    Se la **finestra di progettazione** viene aperta automaticamente, selezionare il design di diapositiva desiderato. Chiudere quindi la **finestra di progettazione**.

1. Applicare qualsiasi riformattazione aggiuntiva che si ritiene sia necessaria, fino a quando non si dispone di una diapositiva simile alla seguente:

    ![Screenshot di una presentazione di PowerPoint con contenuto generato da Copilot.](./media/generative-ai/powerpoint-slide.png)

1. Nella barra del titolo di PowerPoint, selezionare il nome predefinito della presentazione (**Presentazione**) e rinominarlo `Business Presentation.pptx`.
1. Chiudere la scheda PowerPoint e tornare alla cartella **Documenti** in OneDrive.

## Usare Copilot per comporre un messaggio di posta elettronica

Sono stati creati alcuni elementi collaterali che consentono di iniziare a creare la propria attività. Ora è il momento di contattare un investitore alla ricerca di alcuni finanziamenti iniziali.

1. Usare l'**icona di avvio delle app** all'estremità sinistra della barra del titolo di OneDrive per aprire **Outlook**.
1. Creare una nuova e-mail e compilare la casella **A** con il proprio indirizzo e-mail.
1. Nel riquadro Copilot, selezionare la scheda **Componi**. Impostare quindi le opzioni seguenti per comporre nuovo contenuto:
    - **Scrivi su**: `Request a meeting with an investment bank to discuss funding for a commercial cleaning business.`
    - **Tono**: Professionale
    - **Formato**: E-mail
    - **Lunghezza**: Media
1. Selezionare **Genera bozza** ed esaminare l'output generato.
1. Usare il contenuto generato per completare l'e-mail, come illustrato di seguito:

    ![Screenshot di un'e-mail generata da Copilot.](./media/generative-ai/generated-email.png)

    Se lo desideri, puoi inviare l'e-mail a te stesso.

## Esercizio

Ora, hai visto come usare Copilot per cercare idee e generare contenuti, perché non provare a esplorarlo ulteriormente? Per avviare una nuova sessione di Copilot, nella scheda **Chat**, selezionare l'icona **Nuovo argomento** accanto alla casella di richiesta e quindi provare a usare Copilot per pianificare un evento atto a promuovere l'alfabetizzazione dei bambini in una biblioteca locale. Alcuni aspetti che è possibile provare includono:

- Ricercare alcuni suggerimenti per incoraggiare i bambini a leggere già da piccoli.
- Creare un volantino o un poster per l'evento.
- Comporre un'e-mail per una campagna che invita autori locali di libri per bambini a venire e parlare all'evento.
- Creare una presentazione per dare inizio all'evento.

In questo modo, si può esprimere la propria creatività, mentre Copilot aiuta a trovare le informazioni, generare e perfezionare il testo, creare immagini e rispondere a domande.


## Conclusione

In questo esercizio è stato usato Copilot in Microsoft Edge per trovare informazioni e generare contenuto. Speriamo che sia stato illustrato chiaramente come usare l'IA generativa in un copilota può contribuire alla produttività e alla creatività dell'utente.

Anche se i servizi gratuiti usati in questi esercizi sono senza dubbio molto potenti, è possibile ottenere ancora di più con servizi come [Copilot per Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365), in cui Microsoft Copilot è integrato nelle applicazioni di produttività di Windows e Microsoft Office, fornendo un aiuto altamente contestualizzato in attività comuni. Microsoft 365 consente di portare la potenza dell'intelligenza artificiale generativa ai dati e ai processi aziendali, integrandosi al tempo stesso nell'infrastruttura IT esistente per garantire una soluzione gestibile e sicura.