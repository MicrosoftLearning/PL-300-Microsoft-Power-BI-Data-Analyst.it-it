---
lab:
  title: Eseguire Analisi avanzate in Power BI
  module: Perform Data Analysis in Power BI
---


# **Eseguire l'analisi dei dati in Power BI**

## **Presentazione del lab**

In questo lab verrà creato il report **Sales Exploration**.

Contenuto del lab:

- Creare grafici a dispersione animati
- Usare un oggetto visivo per prevedere valori

**Questo lab deve richiedere circa 30 minuti.**

## **Introduzione - Accedere**

In questa attività verrà configurato l'ambiente per il lab accedendo a Power BI.

*Nota: se si è già eseguito l'accesso a Power BI, passare all'attività successiva.*

1. Per aprire Microsoft Edge, sulla barra delle applicazioni selezionare il collegamento al programma Microsoft Edge.

     ![Figura 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Nella finestra del browser Microsoft Edge passare a **https://app.powerbi.com**.

    *Suggerimento: è anche possibile usare l'elemento preferito Servizio Power BI sulla barra dei preferiti di Microsoft Edge.*

1. Completare il processo di accesso con le credenziali dell'organizzazione (o fornite). Se in Microsoft Edge viene chiesto se restare connessi, selezionare **Sì**.

1. Nella finestra del browser Microsoft Edge, nel servizio Power BI, nel riquadro **Navigazione** espandere **Area di lavoro personale**. Lasciare aperta la finestra del browser Microsoft Edge.

     ![Figura 22](Linked_image_Files/07-my-workspace-new.png)

## **Introduzione: creare un set di dati**

In questa attività verrà configurato l'ambiente per il lab creando un set di dati. *Se il set di dati è già stato pubblicato, passare all'attività successiva.*

1. Nella finestra del browser Microsoft Edge, nella servizio Power BI passare a **Area di lavoro personale**.

1. Selezionare **Carica > Sfoglia**.

1. Passare alla cartella **D:\PL300\Labs\08-perform-data-analysis-in-power-bi-desktop\Starter** .

1. Selezionare il file **Sales Analysis.pbix** e quindi selezionare **Apri**.

    *Se viene richiesto di sostituire il set di dati, selezionare **Sostituisci**.*

*Questo metodo creerà un report e un set di dati. Verrà usato solo il set di dati per creare un nuovo report in questo esercizio. Questo stesso processo può essere eseguito con un set di dati esistente da un report diverso anziché caricare nuovo. Inoltre, se non si usa il report, le procedure consigliate per l'area di lavoro suggeriscono di eliminare il file non necessario.*

## **Creare il report**

In questa attività si creerà una connessione dinamica al set di dati di Power BI creato nell'ultima attività e quindi si creerà un nuovo report di **esplorazione vendite** .

1. Aprire Power BI Desktop.

    ![icona Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Importante: se Power BI Desktop è già aperto (da un lab precedente), chiudere tale istanza.*

    *Suggerimento: per impostazione predefinita, la finestra di dialogo Introduzione viene aperta davanti a Power BI Desktop. È possibile scegliere di accedere e quindi chiudere il popup.*

1. Nella barra multifunzione Home selezionare **Recupera dati > set di dati di Power BI**.

1. Nella finestra **Hub dati** selezionare il set di dati **Sales Analysis** **nell'area di lavoro** personale e quindi **connettersi** o fare doppio clic per caricare il set di dati.

1. Passare a **File > Salvare** e salvare il nome del file come **Esplorazione vendite** nella cartella **D:\PL300\MySolution** .

*È ora possibile creare due pagine del report e in ogni pagina verrà usato un oggetto visivo diverso per analizzare ed esplorare i dati.*

## **Creare un grafico a dispersione animato**

In questa attività verrà creato un grafico a dispersione che può essere animato.

1. Rinominare **Pagina 1** in **Grafico a dispersione**.

1. Aggiungere un oggetto visivo **Grafico a dispersione** alla pagina del report e quindi posizionarlo e ridimensionarlo in modo da riempire l'intera pagina.
    
    *Il grafico può essere animato quando viene aggiunto un campo nell'area **Asse di riproduzione**.*

     ![Figura 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

     ![Immagine 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:
    
    *I lab usano una notazione a breve per fare riferimento a un campo. Sarà simile al seguente: **Tipo di business** **rivenditore****\|**. In questo esempio **, Reseller** è il nome della tabella e **Il tipo di business** è il nome del campo.*

     - Asse X: **Sales \| Sales**
     - Asse Y: **Sales \| Profit Margin**
     - Legenda: **Reseller \| Business Type**
     - Dimensioni: **Sales \| Quantity**
     - Asse di riproduzione: **Date \| Quarter**

1. Nel riquadro **Filtri** aggiungere il campo **Product \| Category** nell'area **Filtri** in questa pagina.

1. Nella scheda del filtro filtrare per **Bikes**.

1. Per animare il grafico, nell'angolo in basso a sinistra selezionare **Riproduci**.

    ![Figura 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

1. Guardare l'intero ciclo di animazione da **FY2018 Q1** a **FY2020 Q4**.
    
    *Il grafico a dispersione consente di comprendere i valori delle misure simultaneamente, in questo caso la quantità di ordini, i ricavi delle vendite e il margine di profitto.*
    
    *Ogni bolla rappresenta un tipo di attività del rivenditore. Le variazioni nelle dimensioni delle bolle rispecchiano le quantità di ordini aumentate o diminuite. I movimenti orizzontali rappresentano invece aumenti o riduzioni dei ricavi delle vendite e i movimenti verticali rappresentano aumenti o riduzioni della redditività.*

1. Quando l'animazione si arresta, selezionare una delle bolle per visualizzare il rilevamento nel tempo.

1. Passare il puntatore del mouse su una bolla per visualizzare una descrizione comando che descrive i valori della misura per il tipo di rivenditore in quel momento.

1. Nel riquadro **Filtri** filtrare solo per **Clothing** e notare che produce un risultato molto diverso.

1. Salvare il file di Power BI Desktop.


## **Creare una previsione**

In questa attività si creerà una previsione per determinare i possibili ricavi delle vendite future.

1. Aggiungere una nuova pagina e quindi rinominarla in **Previsione**.

1. Aggiungere un oggetto visivo **Grafico a linee** alla pagina del report e quindi posizionarlo e ridimensionarlo in modo da riempire l'intera pagina.

     ![Figura 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

     ![Immagine 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

     - Asse X: **Date \| Date**
     - Asse Y: **Sales \| Sales**

1. Nel riquadro **Filtri** aggiungere il campo **Date \| Year** nell'area **Filtri in questa pagina**.

1. Nella scheda del filtro filtrare per due anni: **FY2019** e **FY2020**.
    
    *Quando si prevede una linea temporale, è necessario almeno due cicli (anni) di dati per produrre una previsione accurata e stabile.*

1. Aggiungere anche il campo **Product \| Category** nell'area **Filtri in questa pagina** e filtrare per **Motociclette**.

1. Per aggiungere una previsione, sotto il riquadro **Visualizzazioni** selezionare il riquadro **Analisi**.

     ![Figura 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

8. Espandere la sezione **Previsione**.
    
    *Se la sezione **Previsione** non è disponibile, è probabile che l'oggetto visivo non sia stato configurato correttamente. La previsione è disponibile solo quando vengono soddisfatte due condizioni: l'asse ha un singolo campo di data di tipo e c'è un solo campo valore.*

1. Impostare l'opzione **Previsione**su **Sì**.

1. Configurare le proprietà di previsione seguenti, quindi **Applica**:

    - Unità: **Mesi**
    - Lunghezza di previsione: **1 mese**
    - Stagionalità: **365**
    - Intervallo di confidenza: **80%**

    ![Immagine 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

1. Nell'oggetto visivo grafico a linee si noti che la previsione è stata estesa di un mese dopo i dati della cronologia.
    
    *L'area grigia rappresenta la confidenza. Maggiore è la confidenza, meno stabile e quindi meno accurata sarà probabilmente la previsione.*
    
    *Quando si conosce la lunghezza del ciclo, in questo caso annuale, immettere i punti di stagionalità. Il ciclo può anche essere settimanale (7) o mensile (30).*

1. Nel riquadro **Filtri** filtrare solo per **Clothing** e osservare che si ottiene un risultato diverso.

### **Completare il lab**

In questa attività si completerà il lab in Power BI Desktop.

1. Selezionare la pagina **Grafico a dispersione**.

1. Salvare il file di Power BI Desktop.

1. Per pubblicare **** il file **nell'area di lavoro Personale**, nella scheda **Home** della barra multifunzione selezionare **Pubblica** e quindi selezionare **Seleziona** per pubblicare.

    ![Figura 23](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image46.png)

1. Chiudere Power BI Desktop.
