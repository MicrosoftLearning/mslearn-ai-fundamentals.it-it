---
lab:
  title: Analizzare il testo nel portale Fonderia Azure AI
---

# Analizzare il testo nel portale Fonderia Azure AI

Lingua di Azure AI include Analisi del testo, con funzionalità quali riconoscimento delle entità, estrazione di frasi chiave, riepilogo e analisi del sentiment. Si supponga, ad esempio, che l'agenzia di viaggi fittizia Margie's Travel incoraggi i clienti a inviare recensioni per i soggiorni in hotel. È possibile usare il servizio di linguaggio per estrarre entità denominate, identificare frasi chiave, riepilogare il testo e altro ancora.

In questo esercizio, verrà utilizzato Lingua di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per analizzare le recensioni degli hotel. 

Questo esercizio richiede circa **20** minuti.

## Creare un progetto nel portale Fonderia Azure AI

1. In un Web browser, aprire il [Portale Fonderia Azure AI](https://ai.azure.com) su `https://ai.azure.com` e accedere usando le credenziali di Azure. Chiudere tutti i riquadri dei suggerimenti o di avvio rapido che vengono aperti al primo accesso e, se necessario, usare il logo **Fonderia Azure AI** in alto a sinistra per passare alla home page, simile all'immagine seguente (chiudere il riquadro **Aiuto** nel caso sia aperto):

    ![Screenshot della home page del Portale Fonderia Azure AI.](./media/ai-foundry-portal.png)

1. Scorrere fino alla fine della pagina e selezionare il riquadro **Esplora i Servizi di Azure AI**.

    ![Screenshot del riquadro Esplora i Servizi di Azure AI.](./media/ai-services.png)

1. Nella pagina Servizi di Azure AI selezionare il riquadro **Lingua + Traduttore**.

    ![Screenshot del riquadro Lingua + Traduttore.](./media/language-tile.png)

1. Nella pagina **Lingua + Traduttore** selezionare **Prova il playground Lingua**. Quindi, quando richiesto, creare un nuovo progetto con le impostazioni seguenti:
    - **Nome progetto**: *Immettere un nome valido per il progetto.*
    - **Impostazioni avanzate**:
        - **Sottoscrizione**: *la sottoscrizione di Azure usata*
        - **Gruppo di risorse**: *creare o selezionare un gruppo di risorse*
        - **Area**: *Selezionare una delle aree **consigliate di Fonderia AI***
        - **Fonderia AI o Azure OpenAI** *Creare una nuova risorsa di Fonderia Azure AI con un nome valido*

1. Selezionare **Crea**. Attendere la creazione del progetto. L'operazione potrebbe richiedere alcuni minuti.

1. Al termine della creazione del progetto, si verrà indirizzati al playground **Lingua** (in caso contrario, nel riquadro attività a sinistra selezionare **Playground** e aprire il playground Lingua da lì).

    Il playground Lingua è un'interfaccia utente che consente di provare alcune funzionalità di Lingua di Azure AI.  

## Usare Lingua di Azure AI per analizzare il testo

Lingua di Azure AI offre un'ampia gamma di funzionalità di analisi del testo.

### Estrarre entità denominate con Lingua di Azure AI nel portale Fonderia Azure AI

Le *entità denominate* sono parole che descrivono persone, luoghi e oggetti con nomi appropriati. Verrà ora utilizzata la funzionalità di estrazione di entità denominata di Lingua di Azure AI per identificare i tipi di informazioni in una recensione.

1. Nel playground Lingua selezionare **Estrai informazioni**. Selezionare quindi il riquadro **Estrai entità denominate**. 

1. In *Esempio* immettere la recensione seguente:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selezionare **Esegui**. Esaminare l'output.

    ![Screenshot dell'interfaccia Estrarre entità denominate nel playground Lingua.](./media/entity-extraction.png)

    Notare nella sezione *Dettagli* come le entità estratte includono informazioni aggiuntive, ad esempio i punteggi di tipo e di attendibilità. Il punteggio di attendibilità rappresenta la probabilità che il tipo identificato appartenga effettivamente a tale categoria.

### Estrarre le frasi chiave con Lingua di Azure AI nel portale Fonderia Azure AI

Le *frasi chiave* sono le informazioni più importanti nel testo. Verrà utilizzata ora la funzionalità di estrazione frasi chiave di Lingua di Azure AI per estrarre informazioni importanti da una recensione.

1. Nel playground Lingua selezionare **Estrai informazioni**. Selezionare quindi il riquadro **Estrai frasi chiave**. 

1. In *Esempio* immettere la recensione seguente:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selezionare **Esegui**. Esaminare l'output.

    ![Screenshot dell'interfaccia Estrarre frasi chiave nel playground Lingua.](./media/key-phrases.png)

    Notare le diverse frasi estratte nella sezione *Dettagli*. Queste frasi dovrebbero contribuire maggiormente al significato del testo.

### Riepilogare il testo con Lingua di Azure AI nel portale Fonderia Azure AI
 
Verranno ora esaminate le funzionalità di riepilogo di Lingua di Azure AI.

1. Nel playground Lingua selezionare **Riepiloga informazioni** e quindi il riquadro **Riepiloga testo**.

1. In *Esempio* immettere la recensione seguente:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selezionare **Esegui**. Esaminare l'output.

    ![Screenshot dell'interfaccia Riepilogo testo nel playground Lingua.](./media/summarize-text.png)

    Notare che il *Riepilogo estratto* in *Dettagli* fornisce punteggi di classificazione per le frasi più salienti.

### Analizzare il sentiment nel testo

L'analisi del sentiment è un'attività comune quando si analizzano testi come le recensioni degli hotel.

1. Nel playground Lingua selezionare **Classifica testo**. Selezionare quindi il riquadro **Analizza sentiment**.

1. In *Esempio* immettere la recensione seguente:
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. Selezionare **Esegui**. Esaminare l'output.

    ![Screenshot dell'interfaccia Analisi del sentiment nel playground Lingua.](./media/sentiment-analysis.png)

    Si noti che l'analisi produce un punteggio di sentiment complessivo e punteggi individuali per ogni frase.

## Rilevare la lingua e tradurre il testo

Lingua di Azure AI consente di rilevare la lingua in cui viene scritto il testo. Traduttore per Azure AI consente inoltre di tradurre facilmente un testo da una lingua a un'altra.

### Rileva lingua

Per iniziare, rilevare la lingua in cui viene scritta una recensione.

1. Nel riquadro **Classifica testo** selezionare il riquadro **Rileva lingua**.

1. In *Esempio* immettere la recensione seguente:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Selezionare **Esegui**. Esaminare l'output.

    ![Screenshot dell'interfaccia Rileva lingua nel playground Lingua.](./media/detect-language.png)

    Si noti che la lingua viene rilevata come francese. 

### Tradurre testo

Tradurre ora la recensione dal francese all'inglese.

1. Nella parte superiore della pagina usare il collegamento **&larr;** (indietro) accanto al titolo della pagina **Playground Lingua** per visualizzare tutti i playground disponibili.
1. Nell'elenco dei playground aprire il **Playground Traduttore**.
1. Nel playground Traduttore selezionare **Traduzione testuale**.
1. Nel riquadro **Configura** selezionare le opzioni di lingua seguenti:
    - **Traduci da**: Francese
    - **Traduci in**: In inglese
1. In *Esempio* immettere la recensione in lingua francese:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Selezionare **Traduci**. Esaminare l'output.

    ![Screenshot dell'interfaccia Traduzione testo nel playground Traduttore.](./media/text-translation.png)

    Si noti che la recensione in francese viene tradotta in inglese.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare **Elimina gruppo di risorse** e **immettere il nome del gruppo di risorse** per confermare. Il gruppo di risorse viene quindi eliminato.

## Altre informazioni

Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Lingua](https://learn.microsoft.com/azure/ai-services/language-service/overview).
