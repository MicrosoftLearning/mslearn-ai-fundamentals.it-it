---
lab:
  title: Esplorare l'intelligenza artificiale generativa con Microsoft Copilot
---
# Esplorare l'intelligenza artificiale generativa con Microsoft Copilot

In questo esercizio si esaminerà l'intelligenza artificiale generativa con Microsoft Copilot. 

## Accedere a Microsoft Copilot

1. Aprire [copilot.microsoft.com](https://copilot.microsoft.com?azure-portal=true) e accedere con l'account Microsoft personale.

1. Microsoft Copilot usa l'intelligenza artificiale generativa per migliorare i risultati della ricerca Bing. Ciò significa che a differenza della sola ricerca, che restituisce contenuto esistente, Microsoft Copilot può mettere insieme nuove risposte in base alla modellazione del linguaggio naturale e alle informazioni del Web.  

1. Verso la parte inferiore della schermata comparirà la finestra **Chiedimi qualsiasi cosa**. Quando si immettono richieste nella finestra, Copilot usa l'intero thread di conversazione per restituire le risposte. Ad esempio, proviamo a porre una serie di domande sul tema dei viaggi.

## Usare le richieste per generare le risposte

1. Digitare una richiesta: `What are 3 pros and cons of traveling in the winter?`. Prima della risposta appariranno le voci *Ricerca in corso per:...* e *Generazione delle risposte per l'utente in corso...*. Il modello usa le risposte cercate come informazioni di base per generare risposte originali. Si noti che la fine della risposta contiene i collegamenti alle origini. 

![Screenshot della risposta di Copilot a una richiesta di viaggio con tre punti elenco per professionisti e tre punti elenco per contro.](./media/generative-ai/bing-copilot-response-traveling.png) 

> **Nota**: se non viene visualizzato un messaggio **Generazione...* o una risposta elenco puntato, non è stato ancora visualizzato Copilot in azione. È necessario tornare al menu di accesso e connettere l'account corrente in uso con un account personale. 
 
1. Digitare una richiesta: `Find me 3 more pros`. Ciò che si intende con questa richiesta è che si desidera vedere altri 3 motivi positivi per viaggiare in inverno che non siano già stati elencati. Si noti che con questo prompt si chiede a Copilot di eseguire due operazioni che la ricerca da sola non esegue: usare la risposta di chat precedente per escludere ciò che viene restituito nella nuova risposta e usare l'argomento della chat precedente senza specificarlo in modo esplicito. 

1. Digitare una richiesta: `Where are 3 places I can go to find fewer crowds?`. 

    > **Nota**: mentre Copilot è in grado di fornire una risposta correlata, può eliminare "memorie" precedenti del thread di conversazione mentre continua. Di conseguenza, le risposte ottenute potrebbero non essere direttamente correlate ai viaggi in inverno. Ciò è dovuto in gran parte alle limitazioni di input dei token. Quando la chat "ricorda" parti precedenti di una conversazione, è perché ha salvato una certa quantità di token dalla conversazione. Man mano che si introducono nuovi token tramite le nuove richieste e risposte, la chat lascia andare i token meno recenti. 

1. Il **pulsante Nuovo argomento** accanto alla finestra della chat è utile. Se si fa clic su di esso, il thread di conversazione precedente viene cancellato in modo che le risposte ai nuovi argomenti non siano basate sull'argomento precedente. Usare l'icona **Nuovo argomento** in corrispondenza della finestra della chat per cancellare la cronologia dei messaggi. 

## Provare la generazione di immagini

1. Verrà ora illustrato un esempio di generazione di immagini. Digitare una richiesta: `Create an image of an elephant eating a hamburger`. Si noti che viene visualizzato un messaggio *che tenterò di creare prima* che Copilot restituisca una risposta. 

    ![Uno screenshot di elefanti che mangiano hamburger](./media/generative-ai/dall-e-elephant.png)

    È importante notare che la risposta può essere simile ma non uguale. Ciò è dovuto al fatto che le risposte sono diverse.  

1. Nella risposta c'è un testo in basso che recita "Con tecnologia DALL-E". Occorre considerare che DALL-E si basa su modelli linguistici di grandi dimensioni, mentre l'input in linguaggio naturale genera immagini. 

1. Tornare alla chat di Copilot facendo clic sull'icona Di Microsoft Bing nell'angolo in alto a destra della schermata. 

## Provare la generazione di codice

1. Verrà ora illustrato un esempio di generazione e traduzione di codice. Digitare una richiesta: `Use Python to create a list`. 

1. Digitare la richiesta: `Translate that into C#`. Si noti che non è stato necessario specificare il "che" è come Copilot sa fare riferimento alla cronologia delle conversazioni.

## Attività bonus

1. Digitare una richiesta: `What are 3 examples of generative AI helping people?`. Potrebbe tornare utile come modello di brainstorming per le proprie idee relative a Copilot!  
