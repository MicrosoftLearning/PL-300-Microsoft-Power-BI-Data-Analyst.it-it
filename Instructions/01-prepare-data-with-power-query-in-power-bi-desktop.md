---
lab:
  title: Preparare i dati in Power BI Desktop
  module: Module 2 - Get Data in Power BI
---

# <a name="prepare-data-in-power-bi-desktop"></a>**Preparare i dati in Power BI Desktop**

**Il tempo stimato per il completamento del lab è di 45 minuti**

In this lab you commence the development of a Power BI Desktop solution for the Adventure Works company. It involves connecting to source data, previewing the data, and using data preview techniques to understand the characteristics and quality of the source data.

Contenuto del lab:

- Aprire Power BI Desktop

- Impostare le opzioni di Power BI Desktop

- Connettersi all'origine dati

- Visualizzare in anteprima i dati di origine

- Usare le tecniche di anteprima dei dati per comprendere meglio i dati

### <a name="lab-story"></a>**Presentazione del lab**

This lab is one of many in a series of labs that was designed as a complete story from data preparation to publication as reports and dashboards. You can complete the labs in any order. However, if you intend to work through multiple labs, for the first 10 labs, we suggest you do them in the following order:

1. **Preparare i dati in Power BI Desktop**

2. Caricare i dati in Power BI Desktop

3. Modellare i dati in Power BI Desktop

5. Creare calcoli DAX in Power BI Desktop - Parte 1

6. Creare calcoli DAX in Power BI Desktop - Parte 2

7. Progettare un report in Power BI Desktop - Parte 1

8. Progettare un report in Power BI Desktop - Parte 2

9. Creare un dashboard di Power BI

10. Eseguire l'analisi dei dati in Power BI Desktop

11. Applicare la sicurezza a livello di riga

## <a name="exercise-1-prepare-data"></a>**Esercizio 1: Preparare i dati**

In this exercise you will create eight Power BI Desktop queries. Six queries will source data from SQL Server, and two from CSV files.

### <a name="task-1-save-the-power-bi-desktop-file"></a>**Attività 1: Salvare il file di Power BI Desktop**

In questa attività verrà innanzitutto salvato il file di Power BI Desktop.

1. Per aprire Power BI Desktop, sulla barra delle applicazioni fare clic sul collegamento Microsoft Power BI Desktop.

    ![Figura 2](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image1.png)

1. Per chiudere la finestra introduttiva, fare clic su **X** nella parte superiore destra della finestra.

    ![Immagine 3](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image2.png)

1. Per salvare il file, fare clic sulla scheda della barra multifunzione **File** per aprire la visualizzazione Backstage.

1. Selezionare **Salva**.

    ![Immagine 4](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image3.png)

1. Nella finestra **Salva con nome** passare alla cartella **D:\PL300\MySolution**.

1. Nella casella **Nome file** immettere **Sales Analysis**.

    ![Immagine 14](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image4.png)

1. Fare clic su **Salva**.

    ![Figura 17](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image5.png)

    Suggerimento: è anche possibile salvare il file facendo clic sull'icona **Salva** in alto a sinistra.

    ![Figura 18](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image6.png)

### <a name="task-2-set-power-bi-desktop-options"></a>**Attività 2: Impostare le opzioni di Power BI Desktop**

In questa attività si imposteranno le opzioni di Power BI Desktop.

1. In Power BI Desktop fare clic sulla scheda **File** della barra multifunzione per aprire la visualizzazione Backstage.

1. A sinistra selezionare **Opzioni e impostazioni** e quindi **Opzioni**.

    ![Immagine 1](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image7.png)

1. Nella finestra **Opzioni**, a sinistra, nel gruppo **File corrente** selezionare **Caricamento dati**.

    ![Figura 5](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image8.png)

    Le impostazioni di **Caricamento dati** per il file corrente consentono di impostare le opzioni che determinano i comportamenti predefiniti durante la modellazione.

1. Nel gruppo **Relazioni** deselezionare le due opzioni già selezionate.

    ![Immagine 7](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image9.png)

    While having these two options enabled can be helpful when developing a data model, you disabled them earlier to support the lab experience. When you create relationships in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab, you’ll learn why you are adding each one.

1. Fare clic su **OK**.

    ![Figura 9](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image10.png)

1. Salvare il file di Power BI Desktop.

### <a name="task-3-get-data-from-sql-server"></a>**Attività 3: Recuperare i dati da SQL Server**

In questa attività verranno create query basate sulle tabelle di SQL Server.

1. Nella scheda **Home** della barra multifunzione fare clic su **SQL Server** nel gruppo **Dati**.

    ![Figura 19](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

2. Nella finestra **Database SQL Server** immettere **localhost** nella casella **Server**.

    ![Figura 21](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image12.png)

    In questo lab si avvia lo sviluppo di una soluzione di Power BI Desktop per l'azienda Adventure Works.

3. Fare clic su **OK**.

    ![Figura 22](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image13.png)

4. Nella finestra **Strumento di navigazione**, a sinistra, espandere il database **AdventureWorksDW2020**.

    Si esaminerà come connettersi ai dati di origine, come visualizzare in anteprima i dati e come usare le tecniche di anteprima dei dati per comprendere le caratteristiche e la qualità dei dati di origine.

    ![Immagine 28](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image17.png)

5. Selezionare la tabella **DimEmployee**, ma non la relativa casella di controllo.

    ![Figura 29](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

6. Nel riquadro a destra osservare un'anteprima dei dati della tabella.

    I dati di anteprima consentono di determinare le colonne e un campione di righe.

7. Per creare query, selezionare la casella di controllo accanto alle sei tabelle seguenti:

    - DimEmployee

    - DimEmployeeSalesTerritory

    - DimProduct

    - DimReseller

    - DimSalesTerritory

    - FactResellerSales

8. Per applicare le trasformazioni ai dati delle tabelle selezionate, fare clic su **Trasforma dati**.

    You won’t be transforming the data in this lab. The objectives of this lab focus on exploring and profiling the data in the <bpt id="p1">**</bpt>Power Query Editor<ept id="p1">**</ept> window.

    ![Immagine 30](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image19.png)

### <a name="task-4-preview-sql-server-queries"></a>**Attività 4: Visualizzare in anteprima le query di SQL Server**

In this task you will preview the data of the SQL Server queries. First, you will learn relevant information about the data. You will also use column quality, column distribution, and column profile tools to understand the data and to assess data quality.

1. Nella finestra **Editor di Power Query**, a sinistra, osservare il riquadro **Query**.

    ![Figura 31](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

    Il riquadro **Query** contiene una query per ogni tabella selezionata.

2. Selezionare la prima query **DimEmployee**.

    ![Immagine 33](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image21.png)

    The <bpt id="p1">**</bpt>DimEmployee<ept id="p1">**</ept> table in the SQL Server database stores one row for each employee. A subset of the rows from this table represents the salespeople, which will be relevant to the model you’ll develop.

3. In basso a sinistra, nella barra di stato, osservare le statistiche per la tabella, che contiene 33 colonne e 296 righe.

    ![Figura 36](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

4. Nel riquadro di anteprima dei dati scorrere orizzontalmente per esaminare tutte le colonne.

5. Si noti che le ultime cinque colonne contengono i collegamenti **Table** o **Value**.

    These five columns represent relationships to other tables in the database. They can be used to join tables together. You’ll join tables in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab.

6. Per valutare la qualità delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna qualità** nel gruppo **Anteprima dati**.

    ![Figura 35](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

    La qualità della colonna consente di determinare facilmente la percentuale di valori validi, con errori o vuoti rilevata nelle colonne.

7. Per la colonna **Position** (sestultima colonna), si noti che il 94% delle righe è vuoto (null).

    ![Immagine 38](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

8. Per valutare la distribuzione delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna distribuzione** nel gruppo **Anteprima dati**.

    ![Immagine 40](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image25.png)

9. Esaminare di nuovo la colonna **Position** e osservare che sono presenti quattro valori distinti e un valore univoco.

10. Esaminare la distribuzione della colonna **EmployeeKey** (prima colonna), dove sono presenti 296 valori distinti e 296 valori univoci.

    ![Immagine 43](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

    When the distinct and unique counts are the same, it means the column contains unique values. When modeling, it’s important that some model tables have unique columns. These unique columns can be used to create one-to-many relationships, which you will do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab.

11. Nel riquadro **Query** selezionare la query **DimEmployeeSalesTerritory**.

    ![Immagine 44](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image27.png)

    The <bpt id="p1">**</bpt>DimEmployeeSalesTerritory<ept id="p1">**</ept> table stores one row for each employee and the sales territory regions they manage. The table supports relating many regions to a single employee. Some employees manage one, two, or possibly more regions. When you model this data, you’ll need to define a many-to-many relationship, which you’ll do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 2<ept id="p1">**</ept> lab.

12. Nel riquadro **Query** selezionare la query **DimProduct**.

    ![Immagine 46](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image28.png)

    La tabella **DimProduct** contiene una riga per ogni prodotto venduto dall'azienda.

13. Scorrere orizzontalmente per visualizzare le ultime colonne.

14. Osservare la colonna **DimProductSubcategory**.

    Quando si aggiungono trasformazioni a questa query nel lab **Caricare i dati in Power BI Desktop**, si userà la colonna **DimProductSubcategory** per unire le tabelle.

15. Nel riquadro **Query** selezionare la query **DimReseller**.

    ![Immagine 49](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image29.png)

    The <bpt id="p1">**</bpt>DimReseller<ept id="p1">**</ept> table contains one row per reseller. Resellers sell, distribute, or value add to the Adventure Works products.

16. Per visualizzare i valori delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Profilo colonna** nel gruppo **Anteprima dati**.

    ![Figura 41](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image30.png)

17. Selezionare l'intestazione di colonna **BusinessType**.

18. Notare il nuovo riquadro aperto sotto il riquadro di anteprima dei dati.

19. Esaminare le statistiche delle colonne e la distribuzione dei valori nel riquadro di anteprima dei dati.

20. Si noti il problema relativo alla qualità dei dati: sono presenti due etichette per il magazzino (**Warehouse** e la versione con un errore di ortografia **Ware House**).

    ![Immagine 51](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

21. Passare il puntatore sulla barra relativa a **Ware House** e osservare che sono presenti cinque righe con questo valore.

    Verrà applicata una trasformazione per rietichettare queste cinque righe nel lab **Caricare i dati in Power BI Desktop**.

22. Nel riquadro **Query** selezionare la query **DimSalesTerritory**.

    ![Immagine 52](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image32.png)

    The <bpt id="p1">**</bpt>DimSalesTerritory<ept id="p1">**</ept> table contains one row per sales region, including <bpt id="p2">**</bpt>Corporate HQ<ept id="p2">**</ept> (headquarters). Regions are assigned to a country, and countries are assigned to groups. In the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab, you’ll create a hierarchy to support analysis at region, country, or group level.

23. Nel riquadro **Query** selezionare la query **FactResellerSales**.

    ![Immagine 54](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image33.png)

    La tabella **FactResellerSales** contiene una riga per ogni riga dell'ordine di vendita. Un ordine di vendita contiene uno o più articoli.

24. Verificare la qualità della colonna **TotalProductCost** e osservare che l'8% delle righe è vuoto.

    ![Immagine 63](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image34.png)

    Questo lab fa parte di una serie che comprende molti lab progettati come attività completa, dalla preparazione dei dati alla pubblicazione come report e dashboard.

### <a name="task-5-get-data-from-a-csv-file"></a>**Attività 5: Recuperare i dati da un file CSV**

In questa attività verrà creata una query basata su un file CSV.

1. Per aggiungere una nuova query nella finestra **Editor di Power Query**, nella scheda **Home** della barra multifunzione fare clic sulla freccia a discesa **Nuova origine** nel gruppo **Nuova query** e quindi selezionare **Testo/CSV**.

    ![Immagine 70](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image35.png)

2. Nella finestra **Apri** passare alla cartella **D:\PL300\Resources** e selezionare il file **ResellerSalesTargets.csv**.

3. Fare clic su **Apri**.

4. Nella finestra **ResellerSalesTargets.csv** esaminare i dati in anteprima.

5. Fare clic su **OK**.

    ![Immagine 71](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image36.png)

  
‎ 

6. Nel riquadro **Query** osservare l'aggiunta della query **ResellerSalesTargets**.

    ![Immagine 72](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image37.png)

    È possibile completare i lab nell'ordine desiderato.

7. Notare anche che nessuna colonna contiene valori vuoti.

    Quando non è presente un obiettivo di vendita mensile, viene invece archiviato un trattino.

8. Esaminare le icone in ogni intestazione di colonna, a sinistra del nome della colonna.

    ![Immagine 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

    Se tuttavia si intende seguire più lab, per i primi 10 è consigliabile procedere in questo ordine:

    Nel lab **Caricare i dati in Power BI Desktop** si applicheranno molte trasformazioni per ottenere un risultato di tipo diverso costituito solo da tre colonne: **Date**, **EmployeeKey** e **TargetAmount**.

### <a name="task-6-get-additional-data-from-a-csv-file"></a>**Attività 6: Recuperare dati aggiuntivi da un file CSV**

In questa attività verrà creata una query aggiuntiva basata su un file CSV diverso.

1. Usare la procedura descritta nell'attività precedente per creare una query basata sul file **D:\PL300\Resources\ColorFormats.csv**.

    ![Immagine 75](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image39.png)

    The <bpt id="p1">**</bpt>ColorFormats<ept id="p1">**</ept> CSV file contains one row per product color. Each row records the HEX codes to format background and font colors. You’ll integrate this data with the <bpt id="p1">**</bpt>DimProduct<ept id="p1">**</ept> query data in the <bpt id="p2">**</bpt>Load Data in Power BI Desktop<ept id="p2">**</ept> lab.

### <a name="task-7-finish-up"></a>**Attività 7: Completare il lab**

In questa attività si completerà il lab.

1. Nella scheda **Visualizza** della barra multifunzione, nel gruppo **Anteprima dati** deselezionare le tre opzioni di anteprima dei dati abilitate in precedenza in questo lab:

    - Colonna qualità

    - Colonna distribuzione

    - Profilo colonna

    ![Immagine 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

2. Per salvare il file di Power BI Desktop, nella finestra **Editor di Power Query** selezionare **Salva** nella visualizzazione Backstage **File**.

    ![Immagine 77](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image41.png)

3. Quando viene richiesto di applicare le query, fare clic su **Applica più tardi**.

    ![Immagine 86](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image42.png)

    Applying the queries will load their data to the data model. You’re not ready to do that, as there are many transformations that must be applied first.

4. Se si intende iniziare il lab successivo, lasciare aperto Power BI Desktop.

    Nel lab **Caricare i dati in Power BI Desktop** verranno eseguite varie trasformazioni delle query e quindi si applicheranno le query per caricarle nel modello di dati.
