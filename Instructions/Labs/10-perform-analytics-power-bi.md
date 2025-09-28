---
lab:
  title: Eseguire l'analisi in Power BI
  module: Perform analytics in Power BI
---

# Eseguire l'analisi in Power BI

## Presentazione del lab

In questo lab verrà creato il report **Sales Exploration**.

Contenuto del lab:

- Creare grafici a dispersione animati.
- Usare un oggetto visivo per prevedere valori.

**Questo lab dovrebbe richiedere circa 30 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/10-perform-analytics-power-bi/10-perform-analytics.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\10-perform-analytics** .

1. Aprire il **file 10-Starter-Sales Analysis.pbix** .

> _**Nota**: è possibile che venga visualizzata una finestra di dialogo di accesso durante il caricamento del file. Selezionare **Annulla** per chiudere la finestra di dialogo di accesso. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche._

## Creare un grafico a dispersione animato

In questa attività verrà creato un grafico a dispersione che può essere animato.

1. Creare una nuova pagina e denominarla **Grafico** a dispersione.

1. Aggiungere un oggetto visivo **Grafico a dispersione** alla pagina del report e quindi posizionarlo e ridimensionarlo in modo da riempire l'intera pagina.

    > *Il grafico può essere animato quando viene aggiunto un campo nell'area **Asse di riproduzione**.*

     ![Figura 18](Linked_image_Files/10-perform-analytics-power-bi_image15.png)

     ![Immagine 75](Linked_image_Files/10-perform-analytics-power-bi_image16.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

    > *I lab usano una notazione abbreviata per fare riferimento a un campo. Sarà simile al seguente: Reseller Business Type.It will look like this: **Reseller\|****** **Business Type.** In questo esempio **Reseller** è il nome della tabella e **Business Type** è il nome del campo.*

     - Asse X: **Sales Sales \|**
     - Asse Y: **Margine profitto vendite \|**
     - Legenda: **Tipo di business rivenditore \|**
     - Dimensioni: **\| Sales Quantity**
     - Asse di riproduzione: **Trimestre data \|**

1. Nel riquadro **Filtri** aggiungere il campo **Product \| Category** nell'area **Filtri** in questa pagina.

1. Nella scheda del filtro filtrare per **Bikes**.

1. Per animare il grafico, nell'angolo inferiore sinistro selezionare **Riproduci**.

    ![Figura 41](Linked_image_Files/10-perform-analytics-power-bi_image19.png)

1. Guardare l'intero ciclo di animazione da **FY2018 Q1** a **FY2020 Q4**.

    > *Il grafico a dispersione consente di comprendere i valori delle misure simultaneamente, in questo caso la quantità di ordini, i ricavi delle vendite e il margine di profitto.*
    > 
    > *Ogni bolla rappresenta un tipo di business rivenditore. Le modifiche apportate alle dimensioni delle bolle riflettono quantità di ordini aumentate o ridotte. Mentre i movimenti orizzontali rappresentano aumenti/riduzioni dei ricavi delle vendite e i movimenti verticali rappresentano aumenti/riduzioni della redditività.*

1. Quando l'animazione si arresta, selezionare una delle bolle per visualizzare il rilevamento nel tempo.

1. Passare il puntatore del mouse su una bolla per visualizzare una descrizione comando che descrive i valori della misura per il tipo di rivenditore in quel momento.

1. Nel riquadro **Filtri** filtrare solo per **Clothing** e notare che produce un risultato molto diverso.

1. Salvare il file di Power BI Desktop.

## Creare una previsione

In questa attività si creerà una previsione per determinare i possibili ricavi delle vendite future.

1. Aggiungere una nuova pagina e quindi rinominare la pagina **Previsione**.

1. Aggiungere un oggetto visivo **Grafico a linee** alla pagina del report e quindi posizionarlo e ridimensionarlo in modo da riempire l'intera pagina.

     ![Figura 19](Linked_image_Files/10-perform-analytics-power-bi_image21.png)

     ![Immagine 74](Linked_image_Files/10-perform-analytics-power-bi_image22.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

     - Asse X: **Data \|**
     - Asse Y: **Sales Sales \|**

1. Nel riquadro **Filtri** aggiungere il campo **Date \| Year** nell'area **Filtri in questa pagina**.

1. Nella scheda filtro filtrare per due anni: **FY2019** e **FY2020**.

    > *Quando si prevede in una linea temporale, sono necessari almeno due cicli (anni) di dati per produrre una previsione accurata e stabile.*

1. Aggiungere anche il campo **Product \| Category** nell'area **Filtri in questa pagina** e filtrare per **Bikes**.

1. Per aggiungere una previsione, sotto il riquadro **Visualizzazioni** selezionare il riquadro **Analisi**.

     ![Figura 20](Linked_image_Files/10-perform-analytics-power-bi_image26.png)

1. Espandere la sezione **Previsione**.

    > *Se la **sezione Forecast** non è disponibile, è probabile che l'oggetto visivo non sia stato configurato correttamente. La previsione è disponibile solo quando vengono soddisfatte due condizioni: l'asse ha un singolo campo di tipo data e un solo campo valore.*

1. Impostare l'opzione **Previsione**su **Sì**.

1. Configurare le proprietà di previsione seguenti, quindi **Applica**:

    - Unità: **Mesi**
    - Lunghezza prevista: **1 mese**
    - Stagionalità: **365**
    - Intervallo di confidenza: **80%**

    ![Immagine 52](Linked_image_Files/10-perform-analytics-power-bi_image29.png)

1. Nell'oggetto visivo Grafico a linee si noti che la previsione è stata estesa di un mese dopo i dati della cronologia.

    > *L'area grigia rappresenta l'attendibilità. Più ampia è la fiducia, meno stabile, e quindi meno accurata, è probabile che la previsione sia.*
    >
    > *Quando si conosce la lunghezza del ciclo, in questo caso annuale, è necessario immettere i punti di stagionalità. A volte può essere settimanale (7) o mensile (30).*

1. Nel riquadro **Filtri** filtrare solo per **Clothing** e notare che produce un risultato diverso.

## Lab completato

È possibile scegliere di salvare il report di Power BI, anche se non è necessario per questo lab. Nell'esercizio successivo si userà un file di avvio predefinito.

1. Passare al **menu "File"** nell'angolo in alto a sinistra e selezionare **"Salva con nome".** 
1. Selezionare **Esplora il dispositivo**
1. Selezionare la cartella in cui si desidera salvare il file e assegnargli un nome descrittivo. 
1. Selezionare il **pulsante Salva** per salvare il report come file con estensione pbix. 
1. Se viene visualizzata una finestra di dialogo che richiede di applicare modifiche alle query in sospeso, selezionare **Applica**.
1. Chiudere Power BI Desktop.