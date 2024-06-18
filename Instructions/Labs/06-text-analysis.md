---
lab:
  title: Analizzare il testo con Language Studio
---

# Analizzare il testo con Language Studio

In questo esercizio verranno esaminate le funzionalità di Lingua di Azure AI analizzando alcune recensioni di hotel come esempio. Verrà usato Language Studio per capire se le recensioni sono principalmente positive o negative.

L'elaborazione del linguaggio naturale (NLP) è un ramo dell'intelligenza artificiale che si occupa del linguaggio scritto o parlato. È possibile usare l'elaborazione del linguaggio naturale per creare soluzioni che estraggono il significato semantico dal testo o dal parlato, oppure soluzioni che formulano risposte significative in linguaggio naturale.

Si supponga, ad esempio, che l'agenzia di viaggi fittizia Margie's Travel incoraggi i clienti a inviare recensioni per i soggiorni in hotel. È possibile usare il servizio Lingua per identificare le frasi chiave, determinare quali recensioni sono positive e quali sono negative o analizzare il testo della recensione per individuare le menzioni di entità note, ad esempio località o persone.

Il servizio di Lingua di Azure AI include funzionalità di analisi del testo e NLP. Tali funzionalità includono l'identificazione delle frasi chiave nel testo e la classificazione del testo in base al sentiment.

## Creare una risorsa del servizio *Lingua*

È possibile usare molte funzionalità di Lingua di Azure AI con una risorsa di **Lingua** o di **Servizi di Azure AI**. Esistono alcune istanze in cui è possibile usare solo una risorsa di Lingua. Per l'esercizio seguente verrà usata una risorsa di **Lingua**. Se non è già stato fatto, creare una risorsa di **Lingua**nella sottoscrizione di Azure.

1. In un’altra scheda del browser aprire il portale di Azure in [https://portal.azure.com](https://portal.azure.com?azure-portal=true), accedere con l’account Microsoft associato alla sottoscrizione di Azure.

1. Cliccare sul pulsante **＋ Crea una risorsa** e cercare *Servizio Lingua*. Selezionare **Crea** un piano del **Servizio Lingua**. Verrà visualizzata una pagina in cui **Selezionare funzionalità aggiuntive**. Mantenere la selezione predefinita e fare clic su **Continua per creare la risorsa**. 

1. Nella pagina **Crea Lingua**, configurare l'opzione con le impostazioni seguenti:
    - **Sottoscrizione**: *la sottoscrizione di Azure usata*.
    - **Gruppo di risorse**: *selezionare o creare un nuovo gruppo di risorse con un nome univoco*.
    - **Area**: *selezionare l'area geografica più vicina. Se negli Stati Uniti orientali usare "Stati Uniti orientali 2"*.
    - **Nome**: *immettere un nome univoco*.
    - **Piano tariffario**: *F0 o S gratuito se F0 gratuito non è disponibile*
    - **Selezionando questa casella, confermo di aver letto e compreso tutte le condizioni seguenti**: *Opzione selezionata*.

1. Selezionare **Rivedi e crea**, quindi **Crea** e attendere il completamento della distribuzione.

## Configurare la risorsa in Lingua di Azure AI Studio

1. In un'altra scheda del browser, aprire **Language Studio** all'indirizzo [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true) e accedere.

1. Se richiesto da **Seleziona una risorsa di Azure**, eseguire le configurazioni seguenti:
    - **Directory di Azure**: *Directory predefinita, la directory in uso*
    - **Sottoscrizione di Azure**: *Selezionare la sottoscrizione usata*
    - **Tipo di risorsa**: Linguaggio
    - **Nome della risorsa**: *selezionare la risorsa del servizio Lingua appena creata*

Quindi seleziona **Fatto**.

> **Importante**: A partire da luglio 2023, i Servizi di Azure AI includono tutti i servizi noti in precedenza come Servizi cognitivi e Servizi di intelligenza artificiale applicata di Azure. È ancora in corso l'aggiornamento del riferimento di alcune interfacce utente da `Cognitive Services` a `Azure AI services`. I due nomi fanno riferimento allo stesso tipo di risorsa.

> **Nota**: Se ***non*** viene chiesto di scegliere una risorsa del servizio Lingua, è possibile che nella sottoscrizione siano presenti più risorse di questo tipo e in tal caso:
> 1. Nella barra in alto della pagina selezionare **Impostazioni (&#9881;)**. 
> 1. Nella pagina **Impostazioni** visualizzare la scheda **Risorse**.
> 1. Selezionare la risorsa appena creata, poi selezionare **Cambia risorsa**. Assicurarsi che l'identità gestita sia **Abilitata**.
> ![Abilitare la risorsa della lingua.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. Nella parte superiore della pagina, selezionare **Language Studio** per tornare alla relativa home page.

## Analizzare le recensioni in Language Studio

1. In un Web browser, passare a **Language Studio** su [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true).

1. Nella pagina di destinazione di **Language Studio**, selezionare la scheda **Classifica testo**, quindi selezionare il riquadro **Analizza sentiment e opinioni**.

1. In *Selezionare la lingua del testo*, selezionare **Inglese**.

1. In *Seleziona la risorsa di Azure*, selezionare la propria risorsa.

1. In *Immetti testo, carica un file o usa uno dei testi di esempio*, copiare e incollare la revisione seguente:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selezionare la casella per confermare che la demo comporterà l'utilizzo ed eventuali costi, quindi selezionare **Esegui**.

1. Esaminare l'output. Si noti che il *documento* viene analizzato per il sentiment, nonché per ogni *frase*. Selezionare **Frase 1** per visualizzare l'analisi del sentiment per tale frase. 

Si noti che esiste un sentiment complessivo seguito da punteggi accanto a tre categorie, *punteggio positivo*, *punteggio neutro*, *punteggio negativo*. In ognuna delle categorie viene fornito un punteggio compreso tra 0 e 1. Questi punteggi di attendibilità indicano la probabilità che il testo fornito corrisponda a un sentiment particolare. 

Selezionare di nuovo **Frase 1** per chiudere.

1. Scorrere verso l'alto per selezionare **Cancella casella di testo** e copiare e incollare la revisione seguente:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. Selezionare **Esegui**. Esaminare l'output e rivedere il sentiment e il livello di attendibilità.

1. Selezionare di nuovo il riquadro **Cancella casella di testo** e copiare e incollare la revisione seguente:

    >Very noisy and rooms are tiny The Lombard Hotel, San Francisco, USA 9/5/2018 Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget

1. Selezionare **Esegui** ed esaminare il sentiment insieme al livello di attendibilità. Esaminare il testo e confrontarlo con l'analisi del sentiment restituito dal servizio.

In questo esercizio è stato usato Language Studio per creare una nuova risorsa Lingua o usare una risorsa esistente. È stata abilitata la risorsa in Impostazioni prima di provare il servizio di opinion mining e sentiment. È stato quindi testato il servizio con tre parti di testo.

## Eseguire la pulizia

Se non si intende eseguire altri esercizi, eliminare eventuali risorse non più necessarie. In questo modo si evita di accumulare costi non necessari.

1. Aprire il **portale di Azure** su [https://portal.azure.com](https://portal.azure.com) e selezionare il gruppo di risorse che contiene la risorsa creata.
1. Selezionare la risorsa e selezionare **Elimina**, quindi **Sì** per confermare. La risorsa viene quindi eliminata.

## Altre informazioni

Per altre informazioni su cosa è possibile fare con questo servizio, vedere la [pagina del servizio Lingua](https://learn.microsoft.com/azure/ai-services/language-service/overview).
