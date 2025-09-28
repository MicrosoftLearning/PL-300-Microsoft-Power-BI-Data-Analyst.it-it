---
lab:
  title: Recuperare i dati in Power BI
  module: Get data in Power BI
---

# Recuperare i dati in Power BI

## Presentazione del lab

Questo lab è progettato per presentare l'applicazione Power BI Desktop, come connettersi ai dati e come usare le tecniche di anteprima dei dati per comprendere le caratteristiche e la qualità dei dati di origine.

Contenuto del lab:

- Aprire Power BI Desktop.
- Connettersi a varie origini dati.
- Visualizzare in anteprima i dati di origine con Power Query.
- Usare le funzionalità di profilatura dei dati in Power Query.

**Questo lab dovrebbe richiedere circa 30 minuti.**

## Introduzione a Power BI Desktop

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/01-get-data-in-power-bi/01-get-data.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\01-get-data** .

Aprire il **file 01-Starter-Sales Analysis.pbix** .

- Questo file di avvio è stato appositamente configurato per completare il lab. Nel file starter sono state disabilitate le impostazioni a livello di report seguenti:

  - Caricamento dati > Importare relazioni da origini dati al primo caricamento
  - Caricamento dati > rilevamento automatico di nuove relazioni dopo il caricamento dei dati

## Recuperare i dati da SQL Server

Questa attività illustra come connettersi a un database di SQL Server e importare tabelle, che creano query in Power Query.

1. Nella scheda **Home** della barra multifunzione selezionare **SQL Server** nel gruppo **Dati**.

     ![Icona Recupera dati di SQL Server](Linked_image_Files/01-get-data-in-power-bi_image11.png)

1. **Nella finestra Database** di SQL Server, nella **casella Server** immettere **localhost** e lasciare **vuoto Database**, quindi selezionare **OK**.

    > ***Nota**: in questo lab si connetterà al database di SQL Server usando **localhost**. Anche se questa operazione va bene per il lab, non è considerata una procedura consigliata per le soluzioni reali.*

1. Se vengono richieste le credenziali, selezionare **Windows > Usa le credenziali** correnti e quindi **Connetti**.

1. Selezionare **OK** se viene visualizzato un avviso che indica che non è possibile stabilire una connessione crittografata.

1. Nel riquadro Strumento di navigazione **** espandere il **database AdventureWorksDW2020**.

    > ***Nota**: il **database AdventureWorksDW2020** si basa sul **database di esempio AdventureWorksDW2017** . È stato modificato per supportare gli obiettivi di apprendimento dei lab del corso.*

1. Selezionare la **tabella DimEmployee e osservare** l'anteprima dei dati della tabella.

     ![Database AdventureWorksDW2020 con DimEmployee indicato](Linked_image_Files/01-get-data-in-power-bi_image18.png)

    > ***Nota**: i dati di anteprima consentono di visualizzare le colonne e un esempio di righe.*

1. Selezionare le tabelle seguenti selezionando **le caselle** accanto ai relativi nomi.

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Completare questa attività selezionando **Trasforma dati**, che verrà aperto editor di Power Query. Lasciare aperto per l'attività successiva.

A questo punto si è connessi a sei tabelle da un database di SQL Server.

## Anteprima dei dati in editor di Power Query

Questa attività introduce il editor di Power Query e consente di esaminare e profilare i dati. Ciò consente di determinare come pulire e trasformare i dati in un secondo momento. Verranno inoltre esaminate entrambe le tabelle delle dimensioni precedute da "Dim" e dalle tabelle dei fatti precedute da "Fact".

1. Nella finestra **Editor di Power Query**, a sinistra, osservare il riquadro **Query**. Il riquadro **Query** contiene una query per ogni tabella selezionata.

     ![Elenco di query caricate](Linked_image_Files/01-get-data-in-power-bi_image20.png)

1. Selezionare la **query DimEmployee** .

    > *La **tabella DimEmployee** nel database di SQL Server archivia una riga per ogni dipendente. Un subset delle righe di questa tabella rappresenta i venditori, che saranno rilevanti per il modello che verrà sviluppato.*

1. Nell'angolo inferiore sinistro della barra di stato vengono fornite alcune statistiche della tabella, ovvero la tabella contiene 33 colonne e 296 righe.

     ![Numero di 33 colonne, 296 righe](Linked_image_Files/01-get-data-in-power-bi_image22.png)

1. Nel riquadro di anteprima dei dati scorrere orizzontalmente per esaminare tutte le colonne. Si noti che le ultime cinque colonne contengono i collegamenti **Table** o **Value**.

    > *Queste cinque colonne rappresentano relazioni con altre tabelle nel database. Possono essere usati per unire le tabelle. Queste tabelle verranno unite più avanti nel **lab Carica dati trasformati in Power BI Desktop** .*

1. Per valutare la qualità delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna qualità** nel gruppo **Anteprima dati**. La qualità della colonna consente di determinare facilmente la percentuale di valori validi, con errori o vuoti rilevata nelle colonne.

     ![Selezione qualità colonna nella barra multifunzione](Linked_image_Files/01-get-data-in-power-bi_image23.png)

1. Si noti che la **colonna Position** ha righe vuote (null) al 94%.

     ![Qualità della colonna che mostra il 94% delle righe vuote](Linked_image_Files/01-get-data-in-power-bi_image24.png)

1. Per valutare la distribuzione delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna distribuzione** nel gruppo **Anteprima dati**.

1. Esaminare di nuovo la colonna **Position** e osservare che sono presenti quattro valori distinti e un valore univoco.

1. Esaminare la distribuzione delle colonne per la **colonna EmployeeKey** . Sono presenti 296 valori distinti e 296 valori univoci.

     ![Distribuzione delle colonne con 296 valori distinti, 296 valori univoci](Linked_image_Files/01-get-data-in-power-bi_image26.png)

    > ***Nota**: quando i conteggi distinti e univoci sono uguali, significa che la colonna contiene valori univoci. Quando si esegue la modellazione, è importante che alcune tabelle del modello contengano colonne univoche. Queste colonne univoco possono essere usate per creare relazioni uno-a-molti, che verranno eseguite nel **lab Model Data in Power BI Desktop** .*

1. Nel riquadro **Query** selezionare la query **DimProduct**.

    > *La **tabella DimProduct** contiene una riga per prodotto venduta dall'azienda.*

1. Nel riquadro **Query** selezionare la query **DimReseller**.

    > *La **tabella DimReseller** contiene una riga per rivenditore. I rivenditori vendono, distribuiscono o aggiungono valore ai prodotti Adventure Works.*

1. Per visualizzare i valori delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Profilo colonna** nel gruppo **Anteprima dati**.

1. Selezionare l'intestazione **di colonna BusinessType** e notare il nuovo riquadro sotto il riquadro di anteprima dei dati. Esaminare le statistiche delle colonne e la distribuzione dei valori nel riquadro di anteprima dei dati.

    > *Si noti il problema relativo alla qualità dei dati: esistono due etichette per il magazzino (**Warehouse** e Ware House** con errori di ortografia**).*

     ![Distribuzione dei valori per la colonna BusinessType](Linked_image_Files/01-get-data-in-power-bi_image31.png)

1. Passare il puntatore sulla barra relativa a **Ware House** e osservare che sono presenti cinque righe con questo valore.

1. Nel riquadro **Query** selezionare la query **DimSalesTerritory**.  

    > *La **tabella DimSalesTerritory** contiene una riga per area di vendita, inclusa **la sede** centrale aziendale. Le aree geografiche vengono assegnate a un paese e i paesi vengono assegnati ai gruppi. **Nel lab Model Data in Power BI Desktop** si creerà una gerarchia per supportare l'analisi a livello di area, paese o gruppo.*

1. Nel riquadro **Query** selezionare la query **FactResellerSales**.

    > *La **tabella FactResellerSales** contiene una riga per ogni riga dell'ordine di vendita, un ordine di vendita contiene uno o più articoli di riga.*

1. Verificare la qualità della colonna **TotalProductCost** e osservare che l'8% delle righe è vuoto.

    > *I valori di colonna TotalProductCost** mancanti **sono un problema di qualità dei dati.*

## Recuperare i dati da un file CSV

In questa attività si creerà una nuova query basata su file CSV.

1. Per aggiungere una nuova query nella finestra **Editor di Power Query**, nella scheda **Home** della barra multifunzione selezionare la freccia a discesa **Nuova origine** nel gruppo **Nuova query** e quindi selezionare **Testo/CSV**.

1. Passare alla **cartella Download > 01-get-data** estratta in precedenza e selezionare il **file ResellerSalesTargets.csv** . Selezionare **Open** (Apri).

1. Nella finestra **ResellerSalesTargets.csv** esaminare i dati in anteprima. Seleziona **OK**.

1. Nel riquadro **Query** osservare l'aggiunta della query **ResellerSalesTargets**.

    > *Il **file CSV ResellerSalesTargets** contiene una riga per venditore, all'anno. Ogni riga registra 12 obiettivi di vendita mensili (espressi in migliaia). L'anno lavorativo della società Adventure Works inizia il 1° luglio.*

1. Notare anche che nessuna colonna contiene valori vuoti.  Se manca una destinazione di vendita mensile, nella colonna viene visualizzato un trattino.

1. Controllare le icone in ogni intestazione di colonna, a sinistra del nome della colonna. Le icone rappresentano il tipo di dati della colonna. **123** indica un numero intero e **ABC** indica il testo.

     ![Tipo di dati colonna](Linked_image_Files/01-get-data-in-power-bi_image38.png)

1. Ripetere i passaggi per creare una query in base al **file ColorFormats.csv** .

    > *Il **file CSV ColorFormats** contiene una riga per colore prodotto. Ogni riga registra i codici HEX per formattare i colori di sfondo e carattere.*

Ora dovrebbero essere presenti due nuove query, **ResellerSalesTargets** e **ColorFormats**.

 ![Elenco query](Linked_image_Files/01-get-data-in-power-bi_image43.png)

## Lab completato

È possibile scegliere di salvare il report di Power BI, anche se non è necessario per questo lab. Nell'esercizio successivo si userà un file di avvio predefinito.

1. Passare al **menu "File"** nell'angolo in alto a sinistra e selezionare **"Salva con nome".** 
1. Selezionare **Esplora il dispositivo**
1. Selezionare la cartella in cui si desidera salvare il file e assegnargli un nome descrittivo. 
1. Selezionare il **pulsante Salva** per salvare il report come file con estensione pbix. 
1. Se viene visualizzata una finestra di dialogo che richiede di applicare modifiche alle query in sospeso, selezionare **Applica**.
1. Chiudere Power BI Desktop.