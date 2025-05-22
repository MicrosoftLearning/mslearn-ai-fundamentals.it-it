---
lab:
  title: Analizzare il testo nel portale Fonderia Azure AI
---

# Analizzare il testo nel portale Fonderia Azure AI

L'elaborazione del linguaggio naturale (NLP) è un ramo dell'intelligenza artificiale che si occupa del linguaggio scritto o parlato. È possibile usare l'elaborazione del linguaggio naturale per creare soluzioni che estraggono il significato semantico dal testo o dal parlato, oppure soluzioni che formulano risposte significative in linguaggio naturale.

Il servizio Lingua di Azure AI include Analisi del testo, con funzionalità quali riconoscimento delle entità, estrazione di frasi chiave, riepilogo e analisi del sentiment. Si supponga, ad esempio, che l'agenzia di viaggi fittizia Margie's Travel incoraggi i clienti a inviare recensioni per i soggiorni in hotel. È possibile usare il servizio di linguaggio per estrarre entità denominate, identificare frasi chiave, riepilogare il testo e altro ancora.

In questo esercizio, verrà utilizzato Lingua di Azure AI nel portale Fonderia Azure AI, piattaforma Microsoft per la creazione di applicazioni intelligenti, per analizzare le recensioni degli hotel. 

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

1. Nel menu a sinistra nella schermata selezionare **Playground**.

1. Nella pagina *Playground* selezionare il riquadro **playground Lingua** per provare alcune funzionalità di Lingua di Azure AI.

## Estrarre entità denominate con Lingua di Azure AI nel portale Fonderia Azure AI

Le *entità denominate* sono parole che descrivono persone, luoghi e oggetti con nomi appropriati. Verrà ora utilizzata la funzionalità di estrazione di entità denominata di Lingua di Azure AI per identificare i tipi di informazioni in una recensione.

1. Nel playground Lingua selezionare **Estrai informazioni**. Selezionare quindi il riquadro **Estrai entità denominate**. 

1. In *Esempio* copiare e incollare la recensione seguente:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selezionare **Esegui**. Esaminare l'output. Notare nella sezione *Dettagli* come le entità estratte includono informazioni aggiuntive, ad esempio i punteggi di tipo e di attendibilità. Il punteggio di attendibilità rappresenta la probabilità che il tipo identificato appartenga effettivamente a tale categoria.

## Estrarre le frasi chiave con Lingua di Azure AI nel portale Fonderia Azure AI

Le *frasi chiave* sono le informazioni più importanti nel testo. Verrà utilizzata ora la funzionalità di estrazione frasi chiave di Lingua di Azure AI per estrarre informazioni importanti da una recensione.

1. Nel playground Lingua selezionare **Estrai informazioni**. Selezionare quindi il riquadro **Estrai frasi chiave**. 

1. In *Esempio* copiare e incollare la recensione seguente:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selezionare **Esegui**. Esaminare l'output. Notare le diverse frasi estratte nella sezione *Dettagli*. Queste frasi dovrebbero contribuire maggiormente al significato del testo.

## Riepilogare il testo con Lingua di Azure AI nel portale Fonderia Azure AI
 
1. Verranno ora esaminate le funzionalità di riepilogo di Lingua di Azure AI. Nel playground Lingua selezionare *Riepiloga informazioni* e quindi il riquadro **Riepiloga testo**.

1. In *Esempio* copiare e incollare la recensione seguente:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selezionare **Esegui**. Esaminare l'output. Notare che il *Riepilogo estratto* in *Dettagli* fornisce punteggi di classificazione per le frasi più salienti.   

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.

1. Selezionare la risorsa e poi **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Lingua](https://learn.microsoft.com/azure/ai-services/language-service/overview).
