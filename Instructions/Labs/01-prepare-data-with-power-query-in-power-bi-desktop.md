---
lab:
  course: 'PL-300, DP-605'
  title: Ottenere i dati in Power BI Desktop
  module: Get Data in Power BI
---

# Ottenere i dati in Power BI Desktop

## **Presentazione del lab**

Questo lab è progettato per presentare l'applicazione Power BI Desktop, come connettersi ai dati e come usare le tecniche di anteprima dei dati per comprendere le caratteristiche e la qualità dei dati di origine. Gli obiettivi di apprendimento sono:

- Aprire Power BI Desktop
- Connettersi a origini dati diverse
- Visualizzare in anteprima i dati di origine con Power Query
- Usare le funzionalità di profilatura dei dati in Power Query

**Questo lab dovrebbe richiedere circa 30 minuti.**

## **Introduzione a Power BI Desktop**

 In questa attività si inizia aprendo un file power BI di avvio (con estensione pbix). Il file di avvio non contiene dati, ma è stato configurato appositamente per completare il lab. Nel file starter sono state disabilitate le impostazioni a livello di report seguenti:

- Caricamento dati > Importare relazioni da origini dati al primo caricamento
- Caricamento dati > rilevamento automatico di nuove relazioni dopo il caricamento dei dati

*Nota: anche se queste due opzioni sono abilitate può essere utile quando si sviluppa un modello di dati, le opzioni sono state disabilitate in precedenza per supportare l'esperienza del lab. Quando si creano relazioni nel **lab Carica dati trasformati in Power BI Desktop** , si apprenderà perché aggiungerli.*

1. Apri Power BI Desktop.

    ![Icona di Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. Per aprire il file di Power BI Desktop di avvio, selezionare Apri **> Sfoglia questo dispositivo**.

1. **Nella finestra Apri** passare alla **cartella D:\Allfiles\Labs\01-prepare-data-with-power-query-in-power-bi-desktop\Starter**.

1. Selezionare il file **Sales Analysis**.

    *Nota: a questo punto, Power BI chiederà di accedere se non è già stato fatto. È possibile accedere o selezionare **Annulla** e continuare il lab.*

1. Salvare una copia del file con **File > Salva con** nome nella **cartella D:\Allfiles\MySolution** .

## **Ottenere dati da SQL Server**

Questa attività illustra come connettersi a un database di SQL Server e importare tabelle, che creano query in Power Query.

1. Nella scheda **Home** della barra multifunzione selezionare **SQL Server** nel gruppo **Dati**.

     ![Icona Recupera dati di SQL Server](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

1. **Nella finestra Database** di SQL Server, nella **casella Server** immettere **localhost** e lasciare **vuoto Database**, quindi selezionare **OK**.

    *Nota: in questo lab si connetterà al database di SQL Server usando **localhost** perché le origini dati del gateway non possono risolvere **localhost**. Questa non è una procedura consigliata quando si creano soluzioni personalizzate.*

1. Se vengono richieste le credenziali, nella **finestra Database** di SQL Server selezionare **Usa le credenziali** correnti e quindi **Connetti**.

1. Nel riquadro Strumento di navigazione **** espandere il **database AdventureWorksDW2020**.

    *Nota: il **database AdventureWorksDW2020** si basa sul **database di esempio AdventureWorksDW2017** . È stato modificato per supportare gli obiettivi di apprendimento dei lab del corso.*

1. Selezionare la **tabella DimEmployee e osservare** l'anteprima dei dati della tabella.

     ![Database AdventureWorksDW2020 con DimEmployee indicato](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

    *Nota: i dati di anteprima consentono di visualizzare le colonne e un esempio di righe.*

1. Per importare i dati della tabella, **selezionare la casella** di controllo accanto alle sei tabelle seguenti:

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. Completare questa attività selezionando **Trasforma dati**, che verrà aperto editor di Power Query.

A questo punto si è connessi ai dati e si ha il editor di Power Query aperto per l'attività successiva.

## **Anteprima dei dati in editor di Power Query**

Questa attività introduce il editor di Power Query e consente di esaminare e profilare i dati. Ciò consente di determinare come pulire e trasformare i dati in un secondo momento. Verranno inoltre esaminate entrambe le tabelle delle dimensioni precedute da "Dim" e dalle tabelle dei fatti precedute da "Fact".

1. Nella finestra **Editor di Power Query**, a sinistra, osservare il riquadro **Query**. Il riquadro **Query** contiene una query per ogni tabella selezionata.

     ![Elenco di query caricate](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

1. Selezionare la prima query **DimEmployee**.

    *La **tabella DimEmployee** nel database di SQL Server archivia una riga per ogni dipendente. Un subset delle righe di questa tabella rappresenta i venditori, che saranno rilevanti per il modello che verrà sviluppato.*

1. Nell'angolo inferiore sinistro della barra di stato vengono fornite alcune statistiche della tabella, ovvero la tabella contiene 33 colonne e 296 righe.

     ![Numero di 33 colonne, 296 righe](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

1. Nel riquadro di anteprima dei dati scorrere orizzontalmente per esaminare tutte le colonne. Si noti che le ultime cinque colonne contengono i collegamenti **Table** o **Value**.

    *Queste cinque colonne rappresentano relazioni con altre tabelle nel database. Possono essere usati per unire le tabelle. Le tabelle verranno unite nel **lab Carica dati trasformati in Power BI Desktop** .*

1. Per valutare la qualità delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna qualità** nel gruppo **Anteprima dati**. La qualità della colonna consente di determinare facilmente la percentuale di valori validi, con errori o vuoti rilevata nelle colonne.

     ![Selezione qualità colonna nella barra multifunzione](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

1. Si noti che la **colonna Position** ha righe vuote (null) al 94%.

     ![Qualità della colonna che mostra il 94% delle righe vuote](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

1. Per valutare la distribuzione delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Colonna distribuzione** nel gruppo **Anteprima dati**.

1. Esaminare di nuovo la colonna **Position** e osservare che sono presenti quattro valori distinti e un valore univoco.

1. Esaminare la distribuzione delle colonne per la **colonna EmployeeKey** . Sono presenti 296 valori distinti e 296 valori univoci.

    *Quando i conteggi distinti e univoci sono uguali, significa che la colonna contiene valori univoci. Durante la modellazione, è importante che alcune tabelle del modello abbiano colonne univoce. Queste colonne univoco possono essere usate per creare relazioni uno-a-molti, che verranno eseguite nel **lab Model Data in Power BI Desktop** .*

     ![Distribuzione delle colonne con 296 valori distinti, 296 valori univoci](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

1. Nel riquadro **Query** selezionare la query **DimProduct**.

    *La **tabella DimProduct** contiene una riga per prodotto venduta dall'azienda.*

1. Nel riquadro **Query** selezionare la query **DimReseller**.

    *La **tabella DimReseller** contiene una riga per rivenditore. I rivenditori vendono, distribuiscono o aggiungono valore ai prodotti Adventure Works.*

1. Per visualizzare i valori delle colonne, nella scheda **Visualizza** della barra multifunzione selezionare **Profilo colonna** nel gruppo **Anteprima dati**.

1. Selezionare l'intestazione **di colonna BusinessType** e notare il nuovo riquadro sotto il riquadro di anteprima dei dati.

1. Esaminare le statistiche delle colonne e la distribuzione dei valori nel riquadro di anteprima dei dati.

    *Si noti il problema relativo alla qualità dei dati: esistono due etichette per il magazzino (**Warehouse** e Ware House** con errori di ortografia**).*

     ![Distribuzione dei valori per la colonna BusinessType](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

1. Passare il puntatore sulla barra relativa a **Ware House** e osservare che sono presenti cinque righe con questo valore.

    *Si applicherà una trasformazione per etichettare nuovamente queste cinque righe nel **lab Carica dati trasformati in Power BI Desktop** .*

1. Nel riquadro **Query** selezionare la query **DimSalesTerritory**.  

    *La **tabella DimSalesTerritory** contiene una riga per area di vendita, inclusa **la sede** centrale aziendale. Le aree geografiche vengono assegnate a un paese e i paesi vengono assegnati ai gruppi. **Nel lab Model Data in Power BI Desktop** si creerà una gerarchia per supportare l'analisi a livello di area, paese o gruppo.*

1. Nel riquadro **Query** selezionare la query **FactResellerSales**.

    *La **tabella FactResellerSales** contiene una riga per ogni riga dell'ordine di vendita, un ordine di vendita contiene uno o più articoli di riga.*

1. Verificare la qualità della colonna **TotalProductCost** e osservare che l'8% delle righe è vuoto.

    *I valori di colonna TotalProductCost** mancanti **sono un problema di qualità dei dati. Per risolvere il problema, nel **lab Carica dati trasformati in Power BI Desktop** si applicheranno trasformazioni per compilare i valori mancanti usando il costo standard del prodotto archiviato nella tabella DimProduct** correlata**.*

## **Ottenere dati da un file CSV**

In questa attività si creerà una nuova query basata su file CSV.

1. Per aggiungere una nuova query nella finestra **Editor di Power Query**, nella scheda **Home** della barra multifunzione selezionare la freccia a discesa **Nuova origine** nel gruppo **Nuova query** e quindi selezionare **Testo/CSV**.

1. **Nella finestra Apri** passare alla **cartella D:\Allfiles\Resources** e selezionare il **file ResellerSalesTargets.csv**. Selezionare **Apri**.

1. Nella finestra **ResellerSalesTargets.csv** esaminare i dati in anteprima. Seleziona **OK**.

1. Nel riquadro **Query** osservare l'aggiunta della query **ResellerSalesTargets**.

    *Il **file CSV ResellerSalesTargets** contiene una riga per venditore, all'anno. Ogni riga registra 12 obiettivi di vendita mensili (espressi in migliaia). L'anno lavorativo della società Adventure Works inizia il 1° luglio.*

1. Notare anche che nessuna colonna contiene valori vuoti.  Quando non è presente un obiettivo di vendita mensile, viene invece archiviato un trattino.

1. Controllare le icone in ogni intestazione di colonna, a sinistra del nome della colonna. Le icone rappresentano il tipo di dati della colonna. **123** indica un numero intero e **ABC** indica il testo.

     ![Immagine 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

1. Ripetere i passaggi per creare una query basata sul **file D:\Allfiles\Resources\ColorFormats.csv** .

    *Il **file CSV ColorFormats** contiene una riga per colore prodotto. Ogni riga registra i codici HEX per formattare i colori di sfondo e carattere.*

*Ora dovrebbero essere presenti due nuove query, **ResellerSalesTargets** e **ColorFormats**.*

 ![Elenco query](Linked_image_Files/01-all-queries-loaded.png)

### **Fine**

In questa attività si completerà il lab.

1. Nella scheda **Visualizza** della barra multifunzione, nel gruppo **Anteprima dati** deselezionare le tre opzioni di anteprima dei dati abilitate in precedenza in questo lab:

    - Colonna qualità
    - Colonna distribuzione
    - Profilo colonna

     ![Immagine 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

1. **Salvare** il file di Power BI Desktop. Quando viene richiesto di applicare le modifiche in sospeso, selezionare **Applica in seguito**.

    *Suggerimento: l'applicazione delle query caricherà i dati al modello di dati. Non si è pronti a farlo, perché esistono molte trasformazioni che devono essere applicate per prime.*
