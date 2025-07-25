---
lab:
  title: 'Pulire, trasformare e caricare i dati in Power BI'
  module: 'Clean, transform, and load data in Power BI'
---

# Pulire, trasformare e caricare i dati in Power BI

## Presentazione del lab

In questo lab si useranno tecniche di pulizia e trasformazione dei dati per iniziare a modellare il modello di dati. Si applicheranno quindi le query per caricare ognuna come tabella al modello semantico.

Contenuto del lab:

- Applicare varie trasformazioni dei dati.
- Caricare le query nel modello semantico.

**Il lab dovrebbe richiedere circa 45 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/02-transform-data-power-bi/02-transform-data.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\02-transform-data** .

Aprire il **file 02-Starter-Sales Analysis.pbix** .

> ***Nota**: è possibile ignorare l'accesso selezionando **Annulla**. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche.*

## Configurare la query Salesperson

In questa attività si userà editor di Power Query per configurare la **query Salesperson**.

> ***Importante**: quando viene richiesto di rinominare le colonne, è importante rinominarle esattamente come descritto.*

1. Per aprire la finestra **Editor di Power Query**, nella scheda della barra multifunzione **Home**, nel gruppo **Query** selezionare l'icona **Trasforma dati**.

    ![Trasforma dati nella barra multifunzione Home](Linked_image_Files/02-transform-data-power-bi_image10.png)

1. Nella finestra **Editor di Power Query**, nel riquadro **Query**, selezionare la query **DimEmployee**.

    ![Immagine 1](Linked_image_Files/02-transform-data-power-bi_image11.png)

    > **Nota:** se viene visualizzato un messaggio di avviso che chiede di specificare come connettersi, selezionare **Modifica credenziali**, connettersi usando le credenziali correnti e selezionare **OK** per usare una connessione non crittografata.
 
1. Per rinominare la query, nel riquadro **Impostazioni query** (situato a destra), nella casella **Nome** sostituire il testo con **Salesperson** e quindi premere **INVIO**. Verificare quindi che il nome sia stato aggiornato nel **riquadro Query** .

    > *Il nome della query determina il nome della tabella del modello. È consigliabile definire nomi concisi e descrittivi.*

1. Per individuare una colonna specifica, nella scheda **Home** della barra multifunzione, dal gruppo **Gestisci colonne** selezionare la freccia rivolta verso il basso **Scegli colonne** e quindi selezionare **Vai a colonna**.

    > *Vai a Colonna è una funzionalità utile con molte colonne. In caso contrario, è possibile scorrere orizzontalmente le colonne.*

    ![Gestire le colonne > Scegliere le colonne > Vai alla colonna](Linked_image_Files/02-transform-data-power-bi_image13.png)

1. **Nella finestra Vai a colonna**, per ordinare l'elenco in base al nome della colonna, selezionare il **pulsante az** sort e quindi selezionare **Nome** e **SalesPersonFlag**. Fare clic su **OK**.

    ![Passare alle opzioni di ordinamento delle colonne](Linked_image_Files/02-transform-data-power-bi_image14.png)

1. Individuare la **colonna SalesPersonFlag** , quindi filtrare la colonna per selezionare solo Salespeople (vale **a dire TRUE**) e fare clic su **OK**.

1. Nel riquadro **Impostazioni query**, nell'elenco **Passaggi applicati** notare l'aggiunta del passaggio **Filtrate righe**.

    > *Ogni trasformazione creata genera risultati in un altro passaggio logico. È possibile modificare o eliminare i passaggi. È anche possibile selezionare un passaggio per visualizzare in anteprima i risultati della query in tale fase della trasformazione della query.*

    ![Passaggi applicati](Linked_image_Files/02-transform-data-power-bi_image17.png)

1. Per rimuovere colonne, nella scheda **Home** della barra multifunzione, dall'interno del gruppo **Gestisci colonne** selezionare l'icona **Scegli colonne**.

1. Nella finestra **Scegli colonne**, per deselezionare tutte le colonne, deselezionare l'opzione **(Seleziona tutte le colonne)**.

1. Per includere colonne, selezionare le sei colonne seguenti:

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - FirstName
    - LastName
    - Titolo
    - EmailAddress

1. Nell'elenco **Passaggi applicati** si noti l'aggiunta di un altro passaggio della query.

    ![Rimozione di altre colonne](Linked_image_Files/02-transform-data-power-bi_image21.png)

1. Per creare una singola colonna del nome, selezionare prima l'intestazione di colonna **FirstName**. Tenendo premuto il tasto **CTRL** selezionare la colonna **LastName**.

    ![Selezione multipla di due colonne per creare una singola colonna](Linked_image_Files/02-transform-data-power-bi_image22.png)

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Merge di colonne** dal menu di scelta rapida.

    > *È possibile applicare molte trasformazioni comuni facendo clic con il pulsante destro del mouse sull'intestazione di colonna e scegliendole dal menu di scelta rapida. Si noti, tuttavia, che nella barra multifunzione sono disponibili altre trasformazioni.*

1. Nella finestra **Merge di colonne** selezionare **Spazio** nell'elenco a discesa **Separatore**.

1. Nella casella **Nome nuova colonna** sostituire il testo con **Salesperson**.

1. Per rinominare la **colonna EmployeeNationalIDAlternateKey** , fare doppio clic sull'intestazione di **colonna EmployeeNationalIDAlternateKey** e sostituire il testo con **EmployeeID**, quindi premere **INVIO**.

1. Usare i passaggi precedenti per rinominare la colonna **EmailAddress** in **UPN**.

    > *UPN è l'acronimo di User Principal Name.*

**Nella barra di stato in basso a sinistra verificare che la query abbia 5 colonne e 18 righe.**

## **Configurare la query SalespersonRegion**

In questa attività verrà configurata la query **SalespersonRegion**.

1. Nel riquadro **Query** selezionare la query **DimEmployeeSalesTerritory**.

1. Nel riquadro **Impostazioni query** rinominare la query in **SalespersonRegion**.

1. Per rimuovere le ultime due colonne, selezionare prima di tutto l'intestazione di colonna **DimEmployee**.

1. Tenendo premuto il tasto **CTRL** selezionare l'intestazione di colonna **DimSalesTerritory**.

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Rimuovi colonne** dal menu di scelta rapida.

**Nella barra di stato verificare che la query abbia 2 colonne e 39 righe.**

## Configurare la query Product

In questa attività verrà configurata la query **Product**.

> ***Importante**: quando sono già state fornite istruzioni dettagliate, i passaggi del lab forniranno istruzioni più concise. Se sono necessarie le istruzioni dettagliate, è possibile fare riferimento ai passaggi delle attività precedenti.*

1. Selezionare la **query DimProduct** e rinominare la query in **Product**.

1. Individuare la colonna **FinishedGoodsFlag** e quindi filtrare la colonna per recuperare i prodotti che sono prodotti finiti (ovvero TRUE).

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Color
    - DimProductSubcategory

1. Si noti che la colonna **DimProductSubcategory** rappresenta una tabella correlata (contiene collegamenti a **Value**).

1. Nell'intestazione di colonna **DimProductSubcategory**, a destra del nome della colonna, selezionare il pulsante di espansione.

    ![Icona di espansione della colonna](Linked_image_Files/02-transform-data-power-bi_image31.png)

1. Vedere l'elenco completo delle colonne, quindi selezionare la **casella Seleziona tutte le colonne** per deselezionare tutte le colonne.

1. Selezionare EnglishProductSubcategoryName e DimProductCategory** e deselezionare la **casella di controllo Usa nome colonna originale come prefisso** prima di selezionare **OK**.**** **

    ![Colonna Espandi](Linked_image_Files/02-transform-data-power-bi_image23.png)

    > *Selezionando queste due colonne, verrà applicata una trasformazione per il join alla **tabella DimProductSubcategory** e quindi include queste colonne. La **colonna DimProductCategory** è, infatti, un'altra tabella correlata nell'origine dati.*

    > *I nomi delle colonne di query devono essere sempre univoci. Se selezionata, questa casella di controllo prefissi ogni colonna con il nome della colonna espansa (in questo caso **DimProductSubcategory**). Poiché è noto che i nomi di colonna selezionati non si scontrano con i nomi di colonna nella **query Product** , l'opzione è deselezionata.*

1. Si noti che la trasformazione ha determinato l'aggiunta di due colonne e che la colonna **DimProductSubcategory** è stata rimossa.

1. Espandere la colonna **DimProductCategory** e quindi introdurre solo la colonna **EnglishProductCategoryName**.

1. Rinominare le quattro colonne seguenti:

    - **EnglishProductName** in **Product**
    - **StandardCost** in **Standard Cost** (includere uno spazio)
    - **EnglishProductSubcategoryName** in **Subcategory**
    - **EnglishProductCategoryName** in **Category**

**Nella barra di stato verificare che la query abbia 6 colonne e 397 righe.**

## Configurare la query Reseller

In questa attività verrà configurata la **query Reseller** .

1. Selezionare la **query DimReseller** e rinominare **Reseller**.

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. Espandere la **colonna DimGeography** per includere **solo** le tre colonne seguenti:

    - Città
    - StateProvinceName
    - EnglishCountryRegionName

1. Nell'intestazione **di colonna Tipo di** business selezionare la freccia rivolta verso il basso e quindi esaminare i valori distinti delle colonne e notare entrambi i valori **Warehouse** e **Ware House**.

1. Fare clic con il pulsante destro del mouse sull'intestazione di colonna **Business Type** e quindi scegliere **Sostituisci valori**.

1. Nella **finestra Sostituisci valori** configurare i valori seguenti:

    - Nella casella **Valore da trovare** immettere **Ware House**
    - Nella casella **Sostituisci con** immettere **Warehouse**

    ![Finestra di dialogo Sostituisci valori](Linked_image_Files/02-transform-data-power-bi_image40.png)

1. Rinominare le quattro colonne seguenti:

    - **BusinessType** in **Business Type** (includere uno spazio)
    - **ResellerName** in **Reseller**
    - **StateProvinceName** in **State-Province**
    - **EnglishCountryRegionName** in **Country-Region**

**Nella barra di stato verificare che la query abbia 6 colonne e 701 righe.**

## Configurare la query Region

In questa attività verrà configurata la query **Region**.

1. Selezionare la **query DimSalesTerritory** e rinominare la query in **Region**.

1. Applicare un filtro alla colonna **SalesTerritoryAlternateKey** per rimuovere il valore 0 (zero).

    > *Verrà rimossa una riga.*

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. Rinominare le tre colonne seguenti:

    - **SalesTerritoryRegion** in **Region**
    - **SalesTerritoryCountry** in **Country**
    - **SalesTerritoryGroup** in **Group**

**Nella barra di stato verificare che la query abbia 4 colonne e 10 righe.**

## Configurare la query Sales

In questa attività verrà configurata la **query Sales** .

1. Selezionare la query FactResellerSales** e rinominarla sales****.**

1. Rimuovere tutte le colonne, **ad eccezione** delle seguenti:

    - SalesOrderNumber
    - DataOrdine
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct

    > ***Nota**: è possibile ricordare nel **lab Prepare Data in Power BI Desktop** che una piccola percentuale di **righe FactResellerSales contiene valori TotalProductCost** mancanti****. La **colonna DimProduct** è stata inclusa per recuperare la colonna costo standard del prodotto per facilitare la correzione dei valori mancanti.*

1. Espandere la colonna **DimProduct**, deselezionare tutte le colonne e quindi includere la colonna **StandardCost**.

1. Per creare una colonna personalizzata, nella scheda **Aggiungi colonna** della barra multifunzione, nel gruppo **Generale** selezionare **Colonna personalizzata**.

    ![Immagine 5664](Linked_image_Files/02-transform-data-power-bi_image47.png)

1. Nella finestra **Colonna personalizzata** nella casella **Nome nuova colonna** sostituire il testo con **Cost**.

1. **Nella casella Formula** colonna personalizzata immettere l'espressione seguente (dopo il simbolo di uguale), quindi salvare la nuova colonna:

   ` if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost] `

    > ***Nota**: è possibile copiare l'espressione dal **file Snippets.txt** nella cartella 02-transform-data.*

    > *Questa espressione verifica se il **valore TotalProductCost** è mancante. Se mancante, produce un valore moltiplicando il **valore OrderQuantity** per il **valore StandardCost**. In caso contrario, usa il valore TotalProductCost** esistente**.*

1. Rimuovere le due colonne seguenti:

    - TotalProductCost
    - StandardCost

1. Rinominare le tre colonne seguenti:

    - **OrderQuantity** in **Quantity**
    - **UnitPrice** in **Unit Price** (includere uno spazio)
    - **SalesAmount** in **Sales**

1. Per modificare il tipo di dati della colonna, nell'intestazione di colonna **Quantity**, a sinistra del nome della colonna, selezionare l'icona **1.2** e quindi selezionare **Numero intero**.

    > *La configurazione del tipo di dati corretto è importante. Quando la colonna contiene un valore numerico, è anche importante scegliere il tipo corretto se si prevede di eseguire calcoli matematici.*

    ![Immagine 5667](Linked_image_Files/02-transform-data-power-bi_image50.png)

1. Modificare i tipi di dati delle tre colonne seguenti in **Numero decimale fisso**.

    > *Il tipo di dati numerico decimale fisso consente 19 cifre e consente una maggiore precisione per evitare errori di arrotondamento. È importante usare il tipo di numero decimale fisso per i valori finanziari o i tassi (ad esempio i tassi di cambio).*

    - Prezzo unitario
    - Vendite
    - Costo

**Nella barra di stato verificare che la query abbia 10 colonne e 999+ righe.** *Un massimo di 1000 righe verrà caricato come dati di anteprima per ogni query.*

## Configurare la query Targets

In questa attività verrà configurata la query **Targets**.

1. Selezionare la **query ResellerSalesTargets** e rinominare **Targets**.

    > **Nota:** se viene visualizzato un messaggio di avviso che chiede di specificare come connettersi, selezionare **Modifica credenziali** e usare l'accesso anonimo.

1. Per trasformare tramite UnPivot le colonne dei 12 mesi (**M01**-**M12**), selezionare prima di tutto le intestazioni di colonna **Year** e **EmployeeID**.

1. Fare clic con il pulsante destro del mouse su una delle intestazioni di colonna selezionate e quindi scegliere **Trasforma altre colonne tramite UnPivot** dal menu di scelta rapida.

1. Si noti che i nomi di colonna vengono ora visualizzati nella colonna **Attribute** e i valori vengono visualizzati nella colonna **Value**.

1. Applicare un filtro alla colonna **Value** per rimuovere i valori trattino (-).

    > *È possibile ricordare che il carattere trattino è stato usato nel file CSV di origine per rappresentare zero (0).*

1. Rinominare le due colonne seguenti:

    - **Attributo** a **MonthNumber** (non c'è spazio)
    - **Value** in **Target**

1. Per preparare i valori della colonna **MonthNumber**, fare clic con il pulsante destro del mouse sull'intestazione di colonna **MonthNumber** e quindi scegliere **Sostituisci valori**.

    > *A questo punto verranno applicate trasformazioni per produrre una colonna data. La data verrà derivata dalle **colonne Year** e **MonthNumber** . Si creerà la colonna usando la **funzionalità Colonne da esempi** .*

1. **Nella finestra Sostituisci valori** immettere **M** e lasciare vuoto la **casella **Sostituisci** con** .

1. Modificare il tipo di dati della colonna **MonthNumber** in **Numero intero**.

1. Nella scheda **Aggiungi colonna** della barra multifunzione, dall'interno del gruppo **Generale** selezionare l'icona **Colonna da esempi**.

    ![Immagine 5675](Linked_image_Files/02-transform-data-power-bi_image59.png)

1. Si noti che la prima riga è relativa all'anno **2017** e al numero del mese **7**.

1. Nella colonna **Column1**, nella prima cella della griglia, immettere **7/1/2017** e quindi premere **INVIO**.

    > ***Nota**: la macchina virtuale usa le impostazioni internazionali degli Stati Uniti, quindi questa data è in effetti il 1° luglio 2017. Altre impostazioni internazionali possono richiedere un valore **0** prima della data.*

1. Si noti che le celle della griglia vengono aggiornate con i valori stimati.

    > *La funzionalità ha stimato accuratamente che si combinano valori dalle **colonne Year** e **MonthNumber** .*

1. Si noti anche la formula visualizzata sopra la griglia della query.

    ![Immagine 5679](Linked_image_Files/02-transform-data-power-bi_image60.png)

1. Per rinominare la nuova colonna, fare doppio clic sull'intestazione **di colonna Unita** e rinominare la colonna come **TargetMonth**.

1. Rimuovere le colonne seguenti:

    - Anno
    - MonthNumber

1. Modificare i tipi di dati delle colonne seguenti:

    - **Target** come numero decimale fisso
    - **TargetMonth** come data

1. Per moltiplicare i valori di **Target** per 1000, selezionare l'intestazione di colonna **Target**, quindi nella scheda della barra multifunzione **Trasforma**, dall'interno del gruppo **Colonna Numero**, selezionare **Standard** e quindi selezionare **Moltiplica**.

    > *È possibile ricordare che i valori di destinazione sono stati archiviati come migliaia.*

    ![Immagine 5682](Linked_image_Files/02-transform-data-power-bi_image63.png)

1. **Nella finestra Moltiplica** nella **casella Valore** immettere **1000** e selezionare **OK**.

**Nella barra di stato verificare che la query abbia 3 colonne e 809 righe.**

## Configurare la query ColorFormats

In questa attività verrà configurata la query **ColorFormats**.

1. Selezionare la **query ColorFormats** e notare che la prima riga contiene i nomi delle colonne.

1. Nella scheda **Home** della barra multifunzione selezionare **Usa prima riga come intestazioni** nel gruppo **Trasforma**.

    ![Immagine 5688](Linked_image_Files/02-transform-data-power-bi_image68.png)

**Nella barra di stato verificare che la query abbia 3 colonne e 10 righe.**

## Aggiornare la query Product

In questa attività verrà aggiornata la query **Product** tramite l'unione della query **ColorFormats**.

1. Selezionare la query **Product**.

1. Per unire la query **ColorFormats**, nella scheda della barra multifunzione **Home** selezionare **Merge di query** nel gruppo **Combina**.

    > *Il merge delle query consente l'integrazione di dati, in questo caso da origini dati diverse (SQL Server e un file CSV).*

    ![Immagine 5654](Linked_image_Files/02-transform-data-power-bi_image71.png)

1. Nella finestra **Merge** nella griglia della query **Product** selezionare l'intestazione di colonna **Color**.

    ![Immagine 5655](Linked_image_Files/02-transform-data-power-bi_image72.png)

1. Nell'elenco a discesa della griglia della query **Product** selezionare la query **ColorFormats**.

    ![Figura 21](Linked_image_Files/02-transform-data-power-bi_image73.png)

1. Nella griglia della query **ColorFormats** selezionare l'intestazione di colonna **Color**.

1. Quando si apre la **finestra Livelli** di privacy, per ognuna delle due origini dati, nell'elenco a discesa corrispondente selezionare **Organizzazione** e quindi **Salva**.

    > *I livelli di privacy possono essere configurati per l'origine dati per determinare se i dati possono essere condivisi tra origini. Se necessario, l'impostazione di ogni origine dati come **organizzazione** consente loro di condividere i dati. Le origini dati private non possono mai essere condivise con altre origini dati. Non significa che i dati privati non possono essere condivisi; significa che il motore di Power Query non può condividere i dati tra le origini.*

    ![Immagine 5691](Linked_image_Files/02-transform-data-power-bi_image74.png)

1. **Nella finestra Merge** usare il tipo** di join predefinito**, mantenendo la selezione di Left Outer e selezionando **OK**.

1. Espandere la colonna **ColorFormats** per includere le due colonne seguenti:

    - Background Color Format
    - Font Color Format

**Nella barra di stato verificare che la query abbia ora 8 colonne e 397 righe.**

## Aggiornare la query ColorFormats

In questa attività si aggiornerà la query **ColorFormats** per disabilitarne il caricamento.

1. Selezionare la query **ColorFormats**.

1. Nel riquadro **Impostazioni query** selezionare il collegamento **Tutte le proprietà**.

    ![Immagine 322](Linked_image_Files/02-transform-data-power-bi_image80.png)

1. Nella finestra **Proprietà query** deselezionare la casella di controllo **Abilita caricamento nel report**.

    > *La disabilitazione del carico significa che non verrà caricata come tabella nel modello di dati. Questa operazione viene eseguita perché la query è stata unita alla **query Product** , che è abilitata per il caricamento nel modello di dati.*

    ![Immagine 323](Linked_image_Files/02-transform-data-power-bi_image81.png)

### Rivedi il prodotto finale

1. In editor di Power Query verificare che siano presenti **8 query, denominate** correttamente come indicato di seguito:

    - Venditore
    - SalespersonRegion
    - Prodotto
    - Reseller
    - Paese
    - Vendite
    - Target
    - ColorFormats (che non verrà caricata nel modello di dati)

1. Selezionare **Chiudi &amp; applica** per caricare i dati nel modello e chiudere editor di Power Query finestra.

    ![Immagine 326](Linked_image_Files/02-transform-data-power-bi_image83.png)

1. È ora possibile visualizzare l'area di disegno in Power BI Desktop, con filtri, visualizzazioni e riquadri dati a destra. Nel riquadro Dati notare le **7 tabelle** caricate nel modello di dati.

    ![Immagine 3](Linked_image_Files/02-transform-data-power-bi_image84.png)

## Lab completato
