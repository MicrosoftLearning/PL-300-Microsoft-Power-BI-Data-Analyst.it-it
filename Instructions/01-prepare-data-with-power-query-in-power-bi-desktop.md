---
lab:
  title: Preparare i dati in Power BI Desktop
  module: 2 - Get Data in Power BI
---

# Preparare i dati in Power BI Desktop

**Il tempo stimato per completare il lab è di 30 minuti.**

Questo lab fa parte di una serie che comprende molti lab progettati come attività completa, dalla preparazione dei dati alla pubblicazione come report e dashboard. È possibile completare i lab nell'ordine desiderato. Se tuttavia si intende seguire più lab, è consigliabile procedere in questo ordine:

1. **Preparare i dati in Power BI Desktop**
1. Caricare i dati in Power BI Desktop
1. Progettare un modello di dati in Power BI
1. Creare calcoli DAX in Power BI Desktop
1. Creare calcoli DAX avanzati in Power BI Desktop
1. Progettare un report in Power BI Desktop
1. Migliorare un report in Power BI Desktop
1. Eseguire l'analisi dei dati in Power BI
1. Creare un dashboard di Power BI
1. Applicare la sicurezza a livello di riga

## **Presentazione del lab**

Questo lab è progettato per introdurre l'applicazione Power BI Desktop e come connettersi ai dati e come usare le tecniche di anteprima dei dati per comprendere le caratteristiche e la qualità dei dati di origine. Gli obiettivi di apprendimento sono:

- Aprire Power BI Desktop
- Connettersi all'origine dati
- Visualizzare in anteprima i dati di origine
- Usare gli strumenti del profilo dati

## **Esercizio 1: Preparare i dati**

In questo esercizio verranno create otto query Power BI Desktop. Per sei query verranno usati dati di origine di SQL Server e per due i dati di file CSV.

### **Attività 1: Introduzione all'Power BI Desktop**

In questa attività si inizia aprendo un file power BI iniziale (con estensione pbix). Il file iniziale non contiene dati, ma è stato configurato appositamente per completare il lab. Le impostazioni a livello di report seguenti sono state disabilitate nel file di avvio:

- Caricamento dati > Importa relazioni da origini dati al primo caricamento
- Caricamento dati > Autodetect nuove relazioni dopo il caricamento dei dati

*Nota: durante lo sviluppo di un modello di dati è possibile abilitare queste due opzioni, è possibile disabilitarle in precedenza per supportare l'esperienza del lab. Quando si creano relazioni nel lab **Load Data in Power BI Desktop** lab, si apprenderà perché si aggiungeranno ognuna di esse.*

<br/>

1. Aprire Power BI Desktop.

    ![icona Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Suggerimento: per impostazione predefinita, la finestra di dialogo Introduzione viene aperta davanti a Power BI Desktop. È possibile scegliere di accedere e quindi chiudere il popup.*

1. Per aprire il file di Power BI Desktop iniziale, selezionare il file **> Apri report > Sfoglia report**.

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Labs\01-prepare-data-with-power-query-in-power-bi-desktop\Starter** .

1. Selezionare il file **Sales Analysis**.

1. Salvare una copia del file con **Salva con nome** nella cartella **D:\PL300\MySolution** .

### **Attività 2: Ottenere dati da SQL Server**

Questa attività illustra come connettersi a un database SQL Server e importare tabelle, che creano query in Power Query.

1. Nella scheda **Home** della barra multifunzione selezionare **SQL Server** all'interno del gruppo **Dati**.

     ![SQL Server Ottenere dati icona](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

1. Nella finestra **SQL Server Database** immettere **localhost** nella casella **Server**, quindi selezionare **OK**.
    
    *Nota: in questo lab si connetterà al database SQL Server usando **localhost** perché le origini dati del gateway non possono risolvere **localhost**. Questa non è una procedura consigliata durante la creazione di soluzioni personalizzate.*

1. Se richiesto per le credenziali, nella finestra **SQL Server Database** selezionare **Usa le credenziali correnti** e quindi **Connetti**.

1. Nella finestra **Strumento di navigazione**, a sinistra, espandere il database **AdventureWorksDW2020**.
    
    *Nota: il database **AdventureWorksDW2020** si basa sul database di esempio **AdventureWorksDW2017** . È stata modificata per supportare gli obiettivi di apprendimento dei laboratori del corso.*

1. Selezionare, ma non controllare la tabella **DimEmployee**

     ![Database AdventureWorksDW2020 con DimEmployee indicato](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

1. Nel riquadro a destra osservare un'anteprima dei dati della tabella. I dati di anteprima consentono di visualizzare le colonne e un esempio di righe.

1. Per creare query, selezionare la casella di controllo accanto alle sei tabelle seguenti:

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Completare questa attività facendo clic su **Trasforma dati**, che aprirà editor di Power Query.
    1. *Questo lab è destinato solo a connettersi e profilare i dati, ma non **trasformare i dati**.*

### **Attività 3: Visualizzare in anteprima i dati in editor di Power Query**

Questa attività introduce la editor di Power Query e consente di esaminare e profilare i dati. Ciò consente di determinare come pulire e trasformare i dati in un secondo momento.

1. Nella finestra **Editor di Power Query**, a sinistra, osservare il riquadro **Query**. Il riquadro **Query** contiene una query per ogni tabella selezionata.

     ![Elenco di query caricate](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

1. Selezionare la prima query **DimEmployee**.

    *La tabella **DimEmployee** nel database di SQL Server archivia una riga per ogni dipendente. Un subset delle righe di questa tabella rappresenta i venditori, che saranno rilevanti per il modello che si svilupperà.*

1. Nell'angolo inferiore sinistro della barra di stato vengono fornite alcune statistiche della tabella: la tabella contiene 33 colonne e 296 righe.

     ![Numero di 33 colonne, 296 righe](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

1. Nel riquadro di anteprima dei dati scorrere orizzontalmente per esaminare tutte le colonne. Si noti che le ultime cinque colonne contengono i collegamenti **Table** o **Value**.
    
    *Queste cinque colonne rappresentano relazioni con altre tabelle nel database. Possono essere usati per unire le tabelle insieme. Si aggiungeranno tabelle **nel lab Carica dati in Power BI Desktop** lab.*

1. Per valutare la qualità delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna qualità** nel gruppo **Anteprima dati**. La qualità della colonna consente di determinare facilmente la percentuale di valori validi, con errori o vuoti rilevata nelle colonne.

     ![Selezione qualità colonna nella barra multifunzione](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

1. Si noti che la colonna **Position** ha righe vuote (null) del 94%.

     ![Qualità della colonna che mostra le righe vuote del 94%](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

1. Per valutare la distribuzione delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna distribuzione** nel gruppo **Anteprima dati**.

1. Esaminare di nuovo la colonna **Position** e osservare che sono presenti quattro valori distinti e un valore univoco.

1. Esaminare la distribuzione della colonna per la colonna **EmployeeKey** , sono presenti 296 valori distinti e 296 valori univoci.
    
    *Quando i conteggi distinti e univoci sono uguali, significa che la colonna contiene valori univoci. Quando si esegue la modellazione, è importante che alcune tabelle di modello dispongano di colonne univoce. Queste colonne univoce possono essere usate per creare relazioni uno-a-molti, che verranno eseguite nel lab **Dati modello in Power BI Desktop** lab.*

     ![Distribuzione delle colonne che mostra 296 valori distinti, 296 valori univoci](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

1. Nel riquadro **Query** selezionare la query **DimEmployeeSalesTerritory**.
    
    *La tabella **DimEmployeeSalesTerritory** archivia una riga per ogni dipendente e le aree del territorio di vendita gestite. La tabella supporta la correlazione di molte aree a un singolo dipendente. Alcuni dipendenti gestiscono uno, due o forse più aree. Quando si modellano questi dati, è necessario definire una relazione molti-a-molti.*

1. Nel riquadro **Query** selezionare la query **DimProduct**. La tabella **DimProduct** contiene una riga per ogni prodotto venduto dall'azienda.

1. Scorrere orizzontalmente per visualizzare le ultime colonne. Osservare la colonna **DimProductSubcategory**.
    
    *Quando si aggiungono trasformazioni a questa query nel lab **Load Data in Power BI Desktop** lab, si userà la colonna **DimProductSubcategory** per aggiungere tabelle.*

1. Nel riquadro **Query** selezionare la query **DimReseller**.
    
    *La tabella **DimReseller** contiene una riga per rivenditore. I rivenditori vendono, distribuiscono o aggiungono valore ai prodotti Adventure Works.*

1. Per visualizzare i valori delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Profilo colonna** nel gruppo **Anteprima dati**.

1. Selezionare l'intestazione di colonna **BusinessType** e notare il nuovo riquadro sotto il riquadro di anteprima dei dati.

1. Esaminare le statistiche delle colonne e la distribuzione dei valori nel riquadro di anteprima dei dati.
    
    *Si noti il problema di qualità dei dati: esistono due etichette per il warehouse (**Warehouse** e **il Ware House** non corretto).*

     ![Distribuzione dei valori per la colonna BusinessType](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

1. Passare il puntatore sulla barra relativa a **Ware House** e osservare che sono presenti cinque righe con questo valore.
    
    *Si applicherà una trasformazione per riassegnare la etichetta a queste cinque righe nel lab **Load Data in Power BI Desktop** lab.*

1. Nel riquadro **Query** selezionare la query **DimSalesTerritory**.  
    
    *La tabella **DimSalesTerritory** contiene una riga per area di vendita, inclusa la sede centrale **aziendale**. Le aree vengono assegnate a un paese e i paesi vengono assegnati ai gruppi. Nel lab **Dati modello in Power BI Desktop** si creerà una gerarchia per supportare l'analisi a livello di area, paese o gruppo.*

1. Nel riquadro **Query** selezionare la query **FactResellerSales**.
    
    *La tabella **FactResellerSales** contiene una riga per riga dell'ordine di vendita, un ordine di vendita contiene uno o più elementi della riga.*

1. Verificare la qualità della colonna **TotalProductCost** e osservare che l'8% delle righe è vuoto.
    
    *I valori di colonna **TotalProductCost** mancanti sono un problema di qualità dei dati. Per risolvere il problema, nel lab **Load Data in Power BI Desktop** si applicano trasformazioni per compilare i valori mancanti usando il costo standard del prodotto archiviato nella tabella **DimProduct** correlata.*

### **Attività 4: Ottenere dati da un file CSV**

In questa attività verrà creata una nuova query in base ai file CSV.

1. Per aggiungere una nuova query, nella finestra **editor di Power Query**, nella scheda **Home** della barra multifunzione selezionare la freccia verso **** il basso **Nuova origine** e quindi **selezionare Testo/CSV**.

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Resources** e selezionare il file **ResellerSalesTargets.csv**. Selezionare **Open** (Apri).

1. Nella finestra **ResellerSalesTargets.csv** esaminare i dati in anteprima. Selezionare **OK**.

1. Nel riquadro **Query** osservare l'aggiunta della query **ResellerSalesTargets**.
    
    *Il file CSV **ResellerSalesTargets** contiene una riga per venditore, all'anno. Ogni riga registra 12 destinazioni mensili di vendita (espresse in migliaia). L'anno lavorativo dell'azienda Adventure Works inizia il 1 luglio.*

1. Notare anche che nessuna colonna contiene valori vuoti.  Quando non è presente un obiettivo di vendita mensile, viene invece archiviato un trattino.

1. Esaminare le icone in ogni intestazione di colonna, a sinistra del nome della colonna. Le icone rappresentano il tipo di dati della colonna. **123** indica un numero intero e **ABC** indica il testo.

     ![Immagine 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

1. Ripetere i passaggi per creare una query in base al file ** diD:\PL300\Resources\ColorFormats.csv** .
    
    *Il file **CSV ColorFormats** contiene una riga per colore del prodotto. Ogni riga registra i codici HEX per formattare i colori di sfondo e carattere.*

*È ora necessario disporre di due nuove query, **ResellerSalesTargets** e **ColorFormats**.*

 ![Elenco query](Linked_image_Files/01-all-queries-loaded.png)

### **Attività 5: Fine**

In questa attività si completerà il lab.

1. Nella scheda **Visualizza** della barra multifunzione, nel gruppo **Anteprima dati** deselezionare le tre opzioni di anteprima dei dati abilitate in precedenza in questo lab:

    - Colonna qualità
    - Colonna distribuzione
    - Profilo colonna

     ![Immagine 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

1. **Salvare** il file Power BI Desktop. Quando viene richiesto di applicare le modifiche in sospeso, selezionare **Applica successivamente**.
    
    *Suggerimento: l'applicazione delle query caricherà i dati nel modello di dati. Non è possibile eseguire questa operazione, poiché sono necessarie molte trasformazioni che devono essere applicate prima.*
