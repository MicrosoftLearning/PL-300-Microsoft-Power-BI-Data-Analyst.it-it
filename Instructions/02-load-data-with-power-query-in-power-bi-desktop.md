---
lab:
  title: Caricare i dati in Power BI Desktop
  module: '3 - Clean, Transform, and Load Data in Power BI'
---

# Caricare i dati in Power BI Desktop

**Il tempo stimato per il completamento del lab è di 45 minuti.**

In questo lab verranno applicate trasformazioni a ognuna delle query create nel lab precedente. Le query verranno quindi applicate per caricare ognuna come tabella nel modello di dati.

Contenuto del lab:

- Applicare varie trasformazioni
- Applicare query per caricarle nel modello di dati

## **Presentazione del lab**

Questo lab fa parte di una serie che comprende molti lab progettati come attività completa, dalla preparazione dei dati alla pubblicazione come report e dashboard. È possibile completare i lab nell'ordine desiderato. Se tuttavia si intende seguire più lab, è consigliabile procedere in questo ordine:

1. Preparare i dati in Power BI Desktop
1. **Caricare i dati in Power BI Desktop**
1. Progettare un modello di dati in Power BI
1. Creare calcoli DAX in Power BI Desktop
1. Creare calcoli DAX avanzati in Power BI Desktop
1. Progettare un report in Power BI Desktop
1. Migliorare un report in Power BI Desktop
1. Eseguire l'analisi dei dati in Power BI
1. Creare un dashboard di Power BI
1. Applicare la sicurezza a livello di riga

## **Esercizio 1: Caricare i dati**

In questo esercizio si applicheranno trasformazioni a ognuna delle query create nel lab precedente.

### **Attività 1: Operazioni preliminari**

In questa attività si configurerà l'ambiente per il lab.

*Importante: se il lab precedente è stato completato nella stessa macchina virtuale, passare all'attività successiva.*

1. Aprire Power BI Desktop.
    
    *Suggerimento: per impostazione predefinita, la finestra di dialogo Introduzione viene visualizzata davanti a Power BI Desktop. È possibile scegliere di eseguire l'accesso e quindi chiudere il popup.*

    ![icona Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Per aprire il file di Power BI Desktop iniziale, selezionare file **> Apri report > Sfoglia report**.

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter** e aprire il file **Sales Analysis** .

1. Chiudere eventuali finestre aperte di carattere informativo.

1. Si noti il messaggio di avviso giallo sotto la barra multifunzione. 

    *Questo messaggio avvisa il fatto che le query non sono state applicate al caricamento come tabelle del modello. Le query verranno applicate più avanti in questo lab.*
    
    Per ignorare il messaggio di avviso giallo, selezionare **X** a destra.

1. Per creare una copia del file, passare a **File > Salva con** nome e salvare nella cartella **D:\PL300\MySolution** .

1. Se viene richiesto di applicare le modifiche, selezionare **Applica più tardi**.

### **Attività 2: Configurare la query Salesperson**

In questa attività si userà editor di Power Query per configurare la query **Salesperson**.

*Importante: quando viene richiesto di rinominare le colonne, è importante rinominarle esattamente come descritto.*

1. Per aprire la finestra **Editor di Power Query**, nella scheda della barra multifunzione **Home**, nel gruppo **Query** selezionare l'icona **Trasforma dati**.

     ![Trasforma dati nella barra multifunzione Home](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image10.png)

1. Nella finestra **Editor di Power Query**, nel riquadro **Query**, selezionare la query **DimEmployee**.

     ![Immagine 1](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image11.png)

1. Per rinominare la query, nel riquadro **Impostazioni query** (situato a destra), nella casella **Nome** sostituire il testo con **Salesperson** e quindi premere **INVIO**. Verificare quindi che il nome sia stato aggiornato nel riquadro **Query** .
    
    *Il nome della query determina il nome della tabella del modello. È consigliabile definire nomi concisi e descrittivi.*

1. Per individuare una colonna specifica, nella scheda **Home** della barra multifunzione selezionare la freccia giù **Gestisci colonne** , selezionare la freccia giù **Scegli colonne** e quindi selezionare **Vai a colonna**.
    
    *Passare a Colonna è una funzionalità utile con molte colonne. In caso contrario, è possibile scorrere orizzontalmente le colonne.*

     ![Gestisci colonne > Scegliere colonne > Vai alla colonna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image13.png)

1. Nella finestra **Vai a colonna** , per ordinare l'elenco in base al nome della colonna, selezionare il pulsante **az** sort e quindi selezionare **Name** e **SalesPersonFlag**. Fare clic su **OK**.

     ![Passare alle opzioni di ordinamento delle colonne](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image14.png)

1. Selezionare l'intestazione di colonna **SalesPersonFlag** , quindi selezionare la freccia giù, quindi **FALSE** e fare clic su **OK**.
    
    *Questa azione filtra le righe per recuperare solo i dipendenti che sono venditori.*

1. Nel riquadro **Impostazioni query**, nell'elenco **Passaggi applicati**, notare l'aggiunta del passaggio **Filtrate righe**.
    
    *Ogni trasformazione creata genera risultati in un'altra logica di passaggio. È possibile modificare o eliminare i passaggi. È anche possibile selezionare un passaggio per visualizzare in anteprima i risultati della query in tale fase della trasformazione della query.*

     ![Passaggi applicati](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image17.png)

1. Per rimuovere le colonne, nella scheda **Home** della barra multifunzione selezionare il gruppo **Gestisci colonne** , selezionare l'icona **Scegli colonne** .

1. Nella finestra **Scegli colonne**, per deselezionare tutte le colonne, deselezionare l'opzione **(Seleziona tutte le colonne)**.

1. Per includere colonne, selezionare le 6 colonne seguenti:

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - FirstName
    - LastName
    - Title
    - EmailAddress

1. Nell'elenco **Passaggi applicati** si noti l'aggiunta di un altro passaggio della query.

     ![Rimozione di altri passaggi di colonne](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image21.png)

1. Per creare una singola colonna del nome, selezionare prima l'intestazione di colonna **FirstName**. Tenendo premuto il tasto **CTRL** selezionare la colonna **LastName**.

     ![Selezione multipla di due colonne per creare una singola colonna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image22.png)

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Merge di colonne** dal menu di scelta rapida.
    
    *Molte trasformazioni comuni possono essere applicate facendo clic con il pulsante destro del mouse sull'intestazione di colonna e scegliendo quindi la trasformazione desiderata dal menu di scelta rapida. Si noti, tuttavia, che sono disponibili altre trasformazioni nella barra multifunzione.*

1. Nella finestra **Merge di colonne** selezionare **Spazio** nell'elenco a discesa **Separatore**.

1. Nella casella **Nome nuova colonna** sostituire il testo con **Salesperson**.

1. Per rinominare la colonna **EmployeeNationalIDAlternateKey** , fare doppio clic sull'intestazione di colonna **EmployeeNationalIDAlternateKey** e sostituire il testo con **EmployeeID**, quindi premere **INVIO**.

1. Usare i passaggi precedenti per rinominare la colonna **EmailAddress** in **UPN**.
    
    *UPN è l'acronimo di User Principal Name, ovvero nome dell'entità utente.*

1. Nella parte inferiore sinistra della barra di stato verificare che la query includa cinque colonne e 18 righe.

### **Attività 3: Configurare la query SalespersonRegion**

In questa attività verrà configurata la query **SalespersonRegion**.

1. Nel riquadro **Query** selezionare la query **DimEmployeeSalesTerritory**.

1. Nel riquadro **Impostazioni query** rinominare la query in **SalespersonRegion**.

1. Per rimuovere le ultime due colonne, selezionare prima di tutto l'intestazione di colonna **DimEmployee**.

1. Tenendo premuto il tasto **CTRL** selezionare l'intestazione di colonna **DimSalesTerritory**.

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Rimuovi colonne** dal menu di scelta rapida.

1. Nella barra di stato verificare che la query includa due colonne e 39 righe.

### **Attività 4: Configurare la query Product**

In questa attività verrà configurata la query **Product**.

*Importante: quando sono già state fornite istruzioni dettagliate, i passaggi del lab forniranno istruzioni più concise. Se sono necessarie le istruzioni dettagliate, è possibile fare riferimento ai passaggi delle attività precedenti.*

1. Selezionare la query **DimProduct** e rinominare la query in **Product**.

1. Individuare la colonna **FinishedGoodsFlag** e quindi filtrare la colonna per recuperare i prodotti finiti , vale a dire TRUE.

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Color
    - DimProductSubcategory

1. Si noti che la colonna **DimProductSubcategory** rappresenta una tabella correlata (contiene collegamenti a **Value**).

1. Nell'intestazione di colonna **DimProductSubcategory** , a destra del nome della colonna, selezionare il pulsante espandi.

    ![Icona di espansione della colonna](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image31.png)

1. Vedere l'elenco completo delle colonne, quindi selezionare la casella **Seleziona tutte le** colonne per deselezionare tutte le colonne.
2. Selezionare **EnglishProductSubcategoryName** e **DimProductCategory** e deselezionare la casella di controllo **Usa nome colonna originale come prefisso** prima di selezionare **OK**.
    
    *Selezionando queste due colonne verrà applicata una trasformazione per creare un join con la tabella **DimProductSubcategory** e quindi includere tali colonne. La colonna **DimProductCategory** è in realtà un'altra tabella correlata nell'origine dati.*
    
    *I nomi delle colonne di query devono essere sempre univoci. Se questa casella di controllo rimane selezionata, a ogni colonna viene aggiunto il nome della colonna espanso come prefisso (in questo caso **DimProductSubcategory**). Poiché è noto che i nomi delle colonne selezionate non sono in conflitto con i nomi delle colonne nella query **Product**, l'opzione è deselezionata.*

1. Si noti che la trasformazione ha determinato l'aggiunta di due colonne e che la colonna **DimProductSubcategory** è stata rimossa.

1. Espandere la colonna **DimProductCategory** e quindi introdurre solo la colonna **EnglishProductCategoryName**.

1. Rinominare le 4 colonne seguenti:

    - **EnglishProductName** in **Product**
    - **StandardCost** in **Standard Cost** (includere uno spazio)
    - **EnglishProductSubcategoryName** in **Subcategory**
    - **EnglishProductCategoryName** in **Category**

1. Nella barra di stato verificare che la query includa 6 colonne e 397 righe.

### **Attività 5: Configurare la query Reseller**

In questa attività si configurerà la query **Reseller** .

1. Selezionare la query **DimReseller e rinominare** **Reseller**.

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. Espandere la colonna **DimGeography** per includere **solo** le tre colonne seguenti:

    - City
    - StateProvinceName
    - EnglishCountryRegionName

1. Nell'intestazione **di colonna Tipo business** selezionare la freccia giù e quindi esaminare i valori di colonna distinti e notare entrambi i valori **Warehouse** e **Ware House**.

1. Fare clic con il pulsante destro del mouse sull'intestazione di colonna **Business Type** e quindi scegliere **Sostituisci valori**.

1. Nella finestra **Sostituisci valori** configurare i valori seguenti:

    - Nella casella **Valore da trovare** immettere **Ware House**
    - Nella casella **Sostituisci con** immettere **Warehouse**

     ![Finestra di dialogo Sostituisci valori](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image40.png)

1. Rinominare le 4 colonne seguenti:

    - **BusinessType** in **Business Type** (includere uno spazio)
    - **ResellerName** in **Reseller**
    - **StateProvinceName** in **State-Province**
    - **EnglishCountryRegionName** in **Country-Region**

1. Nella barra di stato verificare che la query includa 6 colonne e 701 righe.

### **Attività 6: Configurare la query Region**

In questa attività verrà configurata la query **Region**.

1. Selezionare la query **DimSalesTerritory** e rinominare la query in **Region**.

1. Applicare un filtro alla colonna **SalesTerritoryAlternateKey** per rimuovere il valore 0 (zero).
    
    *Verrà rimossa una riga.*

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. Rinominare le tre colonne seguenti:

    - **SalesTerritoryRegion** in **Region**
    - **SalesTerritoryCountry** in **Country**
    - **SalesTerritoryGroup** in **Group**

1. Nella barra di stato verificare che la query includa 4 colonne e 10 righe.

### **Attività 7: Configurare la query Sales**

In questa attività verrà configurata la query **Sales** .

1. Selezionare la query **FactResellerSales** e rinominarla **Sales**.

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - SalesOrderNumber
    - OrderDate
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct
        
        *Nota: è possibile ricordare nel lab **Prepare Data in Power BI Desktop** che una piccola percentuale di righe **FactResellerSales** contiene valori **TotalProductCost** mancanti. La colonna **DimProduct** è stata inclusa per recuperare la colonna costo standard del prodotto per facilitare la correzione dei valori mancanti.*

1. Espandere la colonna **DimProduct**, deselezionare tutte le colonne e quindi includere la colonna **StandardCost**.

1. Per creare una colonna personalizzata, nella scheda **Aggiungi colonna** della barra multifunzione selezionare **Colonna personalizzata** all'interno del gruppo **Generale**.

     ![Immagine 5664](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image47.png)

1. Nella finestra **Colonna personalizzata** nella casella **Nome nuova colonna** sostituire il testo con **Cost**.

1. Nella casella **Formula colonna personalizzata** immettere l'espressione seguente (dopo il simbolo di uguale).
    - *È possibile copiare l'espressione dal file **D:\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Assets\Snippets.txt** .*
    - *Questa espressione verifica se il valore **TotalProductCost** non è presente. Se mancante, produce un valore moltiplicando il valore **OrderQuantity** per il valore **StandardCost** ; in caso contrario, usa il valore **TotalProductCost** esistente.*
    

    `
    if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
    `

1. Rimuovere le due colonne seguenti:

    - TotalProductCost
    - StandardCost

1. Rinominare le tre colonne seguenti:

    - **OrderQuantity** in **Quantity**
    - **UnitPrice** in **Unit Price** (includere uno spazio)
    - **SalesAmount** in **Sales**

1. Per modificare il tipo di dati della colonna, nell'intestazione **di colonna Quantity** , a sinistra del nome della colonna selezionare l'icona **1.2** e quindi selezionare **Numero intero**.
    
    *La configurazione del tipo di dati corretto è importante. Anche quando la colonna contiene un valore numerico è importante scegliere il tipo corretto se si prevede di eseguire calcoli matematici.*

     ![Immagine 5667](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image50.png)

1. Modificare i tipi di dati delle tre colonne seguenti in **Numero decimale fisso**.
    
    *Il tipo di dati numerico decimale fisso consente 19 cifre e consente una maggiore precisione per evitare errori di arrotondamento. È importante usare il tipo di numero decimale fisso per i valori finanziari o i tassi ,ad esempio i tassi di cambio.*

    - Unit Price
    - Sales
    - Cost

1. Nella barra di stato verificare che la query includa 10 colonne e più di 999 righe.
    
    *Un massimo di 1000 righe verrà caricato come dati di anteprima per ogni query.*

### **Attività 8: Configurare la query Targets**

In questa attività verrà configurata la query **Targets**.

1. Selezionare la query **ResellerSalesTargets** e rinominare **Targets**.

1. Per trasformare tramite UnPivot le colonne dei 12 mesi (**M01**-**M12**), selezionare prima di tutto le intestazioni di colonna **Year** e **EmployeeID**.

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Trasforma altre colonne tramite UnPivot** dal menu di scelta rapida.

1. Si noti che i nomi di colonna vengono ora visualizzati nella colonna **Attribute** e i valori vengono visualizzati nella colonna **Value**.

1. Applicare un filtro alla colonna **Value** per rimuovere i valori trattino (-).

    *Si ricorderà che il carattere trattino è stato usato nel file CSV di origine per rappresentare lo zero (0).*

1. Rinominare le due colonne seguenti:

    - **Attributo** a **MonthNumber** (non è disponibile spazio)
    - **Value** in **Target**

1. Per preparare i valori della colonna **MonthNumber**, fare clic con il pulsante destro del mouse sull'intestazione di colonna **MonthNumber** e quindi scegliere **Sostituisci valori**.
        
    *Verranno ora applicate le trasformazioni per produrre una colonna della data. La data verrà derivata dalle colonne **Year** e **MonthNumber**. La colonna verrà creata usando la funzionalità **Colonna da esempi**.*

1. Nella finestra **Sostituisci valori** immettere **M** e lasciare **la casella** **Sostituisci con** vuoto.

1. Modificare il tipo di dati della colonna **MonthNumber** in **Numero intero**.

1. Nella scheda **Aggiungi** barra multifunzione Colonna selezionare l'icona **Colonna da esempi** all'interno del gruppo **Generale**.

    ![Immagine 5675](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image59.png)

1. Si noti che la prima riga è relativa all'anno **2017** e al numero del mese **7**.

1. Nella colonna **Column1**, nella prima cella della griglia, immettere **7/1/2017** e quindi premere **INVIO**.
    
    *La macchina virtuale usa le impostazioni regionali degli Stati Uniti, quindi questa data è infatti il 1 luglio 2017. Altre impostazioni internazionali possono richiedere **un valore 0** prima della data.*

1. Si noti che le celle della griglia vengono aggiornate con i valori stimati.
    
    *La funzionalità ha previsto in modo accurato che si stanno combinando i valori dalle colonne **Year** e **MonthNumber** .*

1. Si noti anche la formula visualizzata sopra la griglia della query.

     ![Immagine 5679](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image60.png)

1. Per rinominare la nuova colonna, fare doppio clic sull'intestazione Di colonna **Unita** e rinominare la colonna come **TargetMonth**.

1. Rimuovere le colonne seguenti:

    - Year
    - MonthNumber

1. Modificare i tipi di dati delle colonne seguenti:

    - **Target** come numero decimale fisso
    - **TargetMonth** come data

1. Per moltiplicare i valori di **destinazione** per 1000, selezionare l'intestazione Di colonna di destinazione e quindi nella scheda **Trasforma** barra multifunzione, dall'interno del gruppo **Numero colonna** selezionare **Standard** e quindi **Moltiplica**.****
    
    *Si ricorderà che i valori di destinazione sono stati archiviati come migliaia.*

     ![Immagine 5682](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image63.png)

1. Nella finestra **Moltiplica** nella casella **Valore** immettere **1000** e selezionare **OK**.

1. Nella barra di stato verificare che la query includa tre colonne e 809 righe.

### **Attività 9: Configurare la query ColorFormats**

In questa attività verrà configurata la query **ColorFormats**.

1. Selezionare la query **ColorFormats** e notare che la prima riga contiene i nomi di colonna.

1. Nella scheda **Home** della barra multifunzione selezionare **Usa prima riga come intestazioni** all'interno del gruppo **Trasforma**.

     ![Immagine 5688](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image68.png)

1. Nella barra di stato verificare che la query includa tre colonne e 10 righe.

### **Attività 10: Aggiornare la query Product**

In questa attività verrà aggiornata la query **Product** tramite l'unione della query **ColorFormats**.

1. Selezionare la query **Product**.

1. Per unire la query **ColorFormats** , nella scheda **Barra** multifunzione Home selezionare **la freccia** combinata verso il basso e quindi selezionare **Merge Query**.
    
    *Il merge delle query consente l'integrazione di dati, in questo caso da origini dati diverse (SQL Server e un file CSV).*

     ![Immagine 5654](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image71.png)

1. Nella finestra **Merge** nella griglia della query **Product** selezionare l'intestazione di colonna **Color**.

     ![Immagine 5655](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image72.png)

1. Nell'elenco a discesa della griglia della query **Product** selezionare la query **ColorFormats**.

     ![Figura 21](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image73.png)

1. Nella griglia della query **ColorFormats** selezionare l'intestazione di colonna **Color**.

1. Quando viene visualizzata la finestra **Livelli di privacy** , per ognuna delle due origini dati, nell'elenco a discesa corrispondente selezionare **Organizzazione**, quindi **Salva**.
    
    *I livelli di privacy possono essere configurati per l'origine dati per determinare se i dati possono essere condivisi tra origini. Se necessario, l'impostazione di ogni origine dati come **organizzazione** consente loro di condividere i dati. Le origini dati private non possono mai essere condivise con altre origini dati. Non significa che i dati privati non possono essere condivisi; significa che il motore di Power Query non può condividere i dati tra le origini.*

     ![Immagine 5691](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image74.png)

1. Nella finestra **Merge** usare il **tipo di join** predefinito: mantiene la selezione di Left Outer e selezionare **OK**.

1. Espandere la colonna **ColorFormats** per includere le due colonne seguenti:

    - Background Color Format
    - Font Color Format

1. Nella barra di stato verificare che la query includa ora otto colonne e 397 righe.

### **Attività 11: Aggiornare la query ColorFormats**

In questa attività si aggiornerà la query **ColorFormats** per disabilitarne il caricamento.

1. Selezionare la query **ColorFormats**.

1. Nel riquadro **Impostazioni query** selezionare il collegamento **Tutte le proprietà**.

     ![Immagine 322](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image80.png)

1. Nella finestra **Proprietà query** deselezionare la casella di controllo **Abilita caricamento nel report**.
    
    *La disabilitazione del carico significa che non verrà caricata come tabella nel modello di dati. Questa operazione viene eseguita perché la query è stata unita alla query **Product** , abilitata per il caricamento nel modello di dati.*

     ![Immagine 323](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image81.png)

### **Attività 12: Completare il lab**

In questa attività si completerà il lab.

1. Verificare di avere otto query, denominate correttamente come indicato di seguito:

    - Salesperson
    - SalespersonRegion
    - Product
    - Reseller
    - Region
    - Sales
    - Targets
    - ColorFormats (che non verrà caricata nel modello di dati)

1. Per eseguire il caricamento nel modello di dati, nella visualizzazione Backstage **File** selezionare **Chiudi e applica**.
    
    *Tutte le query abilitate per il caricamento sono ora caricate nel modello di dati.*

     ![Immagine 326](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image83.png)

1. Nel riquadro **Campi** (a destra) si notino le sette tabelle caricate nel modello di dati.

     ![Immagine 3](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image84.png)

1. Salvare il file di Power BI Desktop.

*Le tabelle e le relazioni del modello di dati verranno configurate nel lab **Modellare i dati in Power BI Desktop**.*
