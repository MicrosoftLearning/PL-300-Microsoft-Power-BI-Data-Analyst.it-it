---
lab:
  title: Creare calcoli DAX avanzati in Power BI Desktop
  module: Create Model Calculations using DAX in Power BI
---

# Creare calcoli DAX avanzati in Power BI Desktop

## **Presentazione del lab**

In questo lab verranno create misure con espressioni DAX che coinvolgono la manipolazione del contesto di filtro.

Contenuto del lab:

- Usare la funzione CALCULATE() per modificare il contesto di filtro
- Usare le funzionalità di Business Intelligence per le gerarchie temporali

**Il lab dovrebbe richiedere circa 45 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:


`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/05-create-dax-calculations-in-power-bi-desktop-advanced/05-advanced-dax.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\05-advanced-dax** .

Aprire il **file 05-Starter-Sales Analysis.pbix** .

> ***Nota**: è possibile ignorare l'accesso selezionando **Annulla**. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche.*

## Creare un oggetto visivo matrice

In questa attività si creerà un oggetto visivo matrice per supportare il test delle nuove misure.

1. In Power BI Desktop, **visualizzazione** Report creare una nuova pagina del report.

1. In **Pagina 3** aggiungere un oggetto visivo matrice.

    ![Immagine 13](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

1. Ridimensionare l'oggetto visivo matrice in modo da riempire l'intera pagina.

1. Per configurare i campi visivi matrice, dal **riquadro Dati** trascinare la **gerarchia Aree \|** geografiche e rilasciarla all'interno dell'oggetto visivo.

    > *I lab usano una notazione abbreviata per fare riferimento a un campo o a una gerarchia. Avrà un aspetto simile al seguente: **Aree \| geografiche**. In questo esempio Region **** è il nome della tabella e **Regions** è il nome della gerarchia.*

1. Aggiungere anche il **campo Sales Sales \|** all'area Valori.

1. Per espandere l'intera gerarchia, nell'angolo superiore destro dell'oggetto visivo matrice fare clic sull'icona con la freccia con biforcazione.

    ![Immagine 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

1. Per formattare l'oggetto visivo, nel riquadro **Visualizzazioni** selezionare il riquadro **Formato**.

    ![Immagine 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

1. **Nella casella Cerca** immettere **Layout**.

1. Impostare la **proprietà Layout** su **Tabulare**.

    ![Immagine 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

1. Verificare che l'oggetto visivo matrice disponga ora di 4 intestazioni di colonna.

    ![Immagine 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    > *In Adventure Works le aree di vendita sono organizzate in gruppi, paesi e aree geografiche. Tutti i paesi, ad eccezione del Stati Uniti, hanno solo un'area, denominata in base al paese. Poiché il Stati Uniti è un territorio di vendita così ampio, è suddiviso in cinque aree di vendita.*

In questo esercizio verranno create diverse misure che vengono quindi testate aggiungendole all'oggetto visivo matrice.

## Modificare il contesto di filtro

In questa attività verranno create diverse misure con espressioni DAX che usano la funzione CALCULATE() per modificare il contesto di filtro.

> *La funzione CALCULATE() è una funzione potente usata per modificare il contesto di filtro. Il primo argomento accetta un'espressione o una misura (una misura è semplicemente un'espressione denominata). Gli argomenti successivi consentono di modificare il contesto di filtro.*

1. Aggiungere una misura alla tabella **Sales** basata sull'espressione seguente:

    > **Nota**: *per praticità, tutte le definizioni DAX in questo lab possono essere copiate dal **file C:\Users\Student\Downloads\05-advanced-dax\Snippets.txt** .*

    ```DAX
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```

    >
    > *La funzione REMOVEFILTERS() rimuove i filtri attivi. Non può accettare argomenti o una tabella, una colonna o più colonne come argomento.*
    >
    > *In questa formula la misura calcola la somma della colonna **Sales** in un contesto di filtro modificato che rimuove tutti i filtri applicati alle colonne della tabella **Region**.*

1. Aggiungere la misura **Sales All Region** all'oggetto visivo matrice.

    ![Immagine 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

1. Si noti che la misura **Sales All Region** calcola il totale di tutte le vendite dell'area per ogni area, paese (subtotale) e gruppo (subtotale).

    *La nuova misura è ancora in grado di ottenere un risultato utile. Quando le vendite per un gruppo, un paese o un'area geografica sono divise per questo valore, produrrà un rapporto utile noto come "percentuale del totale complessivo".*

1. **Nel riquadro Dati** verificare che la **misura Sales All Region** sia selezionata (se selezionata, avrà uno sfondo grigio scuro) e quindi nella barra della formula sostituire il nome della misura e la formula con la formula seguente:

    *Suggerimento: per sostituire la formula esistente, copiare prima il frammento di codice. Selezionare quindi all'interno della barra della formula e premere **CTRL+A** per selezionare tutto il testo. Premere **quindi CTRL+V** per incollare il frammento per sovrascrivere il testo selezionato. Quindi premere **INVIO**.*

    ```DAX
    Sales % All Region =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region)  
     )  
    )
    ```

    *La misura è stata rinominata per riflettere in modo accurato la formula aggiornata. La funzione DIVIDE() divide la **misura Sales** (non modificata dal contesto di filtro) per la **misura Sales** in un contesto modificato, che rimuove tutti i filtri applicati alla **tabella Region** .*

1. Nell'oggetto visivo matrice si noti che la misura è stata rinominata e che ora viene visualizzato un valore diverso per ogni gruppo, paese e area geografica.

1. Formattare la misura **Sales % All Region** come percentuale con due cifre decimali.

1. Nell'oggetto visivo matrice esaminare i valori della misura **Sales% All Region**.

    ![Immagine 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

1. Aggiungere un'altra misura alla tabella **Sales** basata sull'espressione seguente e formattata come percentuale:

    ```DAX
    Sales % Country =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
    )
    ```

1. Si noti che la formula della misura **Sales % Country** differisce leggermente dalla formula della misura **Sales % All Region**.

    *La differenza è che il denominatore modifica il contesto di filtro rimuovendo i filtri nella **colonna Region** della **tabella Region, non tutte le colonne della **tabella Region****. Significa che tutti i filtri applicati alle colonne di gruppo o paese vengono mantenuti. Otterrà un risultato che rappresenta le vendite come percentuale di paese.*

1. Aggiungere la misura **Sales % Country** all'oggetto visivo matrice.

1. Si noti che solo le aree Stati Uniti producono un valore che non è 100%.

    ![Immagine 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    > *È possibile ricordare che solo il Stati Uniti ha più aree. Tutti gli altri paesi comprendono una singola regione, che spiega perché sono tutti del 100%.*

1. Per migliorare la leggibilità di questa misura nell'oggetto visivo, sovrascrivere la misura **Sales % Country** con questa formula migliorata.

    ```DAX
    Sales % Country =  
    IF(  
     ISINSCOPE(Region[Region]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
     )  
    )
    ```

    > *La funzione IF() usa la funzione ISINSCOPE() per verificare se la colonna dell'area è il livello in una gerarchia di livelli. Se true, la funzione DIVIDE() viene valutata. Se false, viene restituito un valore vuoto perché la colonna dell'area non è nell'ambito.*

1. Si noti che la misura **Sales % Country** ora restituisce un valore solo quando un'area è nell'ambito.

    ![Immagine 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

1. Aggiungere un'altra misura alla tabella **Sales** basata sull'espressione seguente e formattata come percentuale:

    ```DAX
    Sales % Group =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
    )
    ```

    > *Per ottenere le vendite come percentuale di gruppo, è possibile applicare due filtri per rimuovere in modo efficace i filtri su due colonne.*

1. Aggiungere la misura **Sales % Group** all'oggetto visivo matrice.

1. Per migliorare la leggibilità di questa misura nell'oggetto visivo, sovrascrivere la misura **Sales % Group** con questa formula migliorata.

    ```DAX
    Sales % Group =  
    IF(  
     ISINSCOPE(Region[Region])  
     || ISINSCOPE(Region[Country]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
     )  
    )
    ```

1. Si noti che la misura **Sales % Group** ora restituisce un valore solo quando un'area o un paese è nell'ambito.

1. Nella vista Modello inserire le tre nuove misure in una cartella di visualizzazione denominata **Ratios**.

    ![Immagine 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

1. Salvare il file di Power BI Desktop.

*Le misure aggiunte alla tabella Sales** hanno modificato il **contesto di filtro per ottenere lo spostamento gerarchico. Si noti che il modello per ottenere il calcolo di un subtotale richiede la rimozione di alcune colonne dal contesto di filtro e per arrivare a un totale complessivo, è necessario rimuovere tutte le colonne.*

## Creare una misura YTD

In questa attività si creerà una misura da inizio anno di vendita (YTD) usando le funzioni di Business Intelligence per le gerarchie temporali.

1. Nella vista Report in **Pagina 2** osservare l'oggetto visivo matrice che visualizza varie misure con anni e mesi raggruppati nelle righe.

2. Aggiungere una misura alla tabella **Sales** basata sull'espressione seguente e formattata con zero cifre decimali:

    ```DAX
    Sales YTD =  
    TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```

    > *La funzione TOTALYTD() valuta un'espressione, in questo caso la somma della **colonna Sales** , su una determinata colonna di data. La colonna data deve appartenere a una tabella data contrassegnata come tabella data.*
    >
    > *La funzione può anche accettare un terzo argomento facoltativo che rappresenta l'ultima data di un anno. L'assenza di questa data indica che il 31 dicembre è l'ultima data dell'anno. Per Adventure Works, giugno nell'ultimo mese dell'anno e quindi viene usato "6-30".*

3. Aggiungere il campo **Sales** e la misura **Sales YTD** all'oggetto visivo matrice.

4. Si noti l'accumulo dei valori delle vendite nell'anno.

    ![Immagine 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

*La funzione TOTALYTD() esegue la manipolazione dei filtri, in particolare la manipolazione del filtro temporale. Ad esempio, per calcolare le vendite YTD per settembre 2017 (il terzo mese dell'anno fiscale), tutti i filtri nella **tabella Date** vengono rimossi e sostituiti con un nuovo filtro di date che iniziano all'inizio dell'anno (1 luglio 2017) e si estendono fino all'ultima data del periodo di data nel contesto (30 settembre 2017)  2017).*

*Molte funzioni di Business Intelligence per le gerarchie temporali sono disponibili in DAX per supportare le manipolazioni comuni dei filtri temporali.*

## Creare una misura di crescita YoY

In questa attività si creerà una misura di crescita YoY di vendita usando una variabile.

> *Le variabili consentono di semplificare la formula e sono più efficienti se si usa la logica più volte all'interno di una formula. Le variabili vengono dichiarate con un nome univoco e l'espressione di misura deve quindi essere restituita dopo la **parola chiave RETURN** . A differenza di altre variabili del linguaggio di codifica, le variabili DAX possono essere usate solo all'interno della singola formula.*

1. Aggiungere un'altra misura alla **tabella Sales** , in base all'espressione seguente:

    ```DAX
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     SalesPriorYear
    ```

    > *Alla **variabile SalesPriorYear** viene assegnata un'espressione che calcola la somma della **colonna Sales** in un contesto modificato che usa la funzione PARALLELPERIOD() per spostare 12 mesi da ogni data nel contesto di filtro.*

1. Aggiungere la misura **Sales YoY Growth** all'oggetto visivo matrice.

1. Si noti che la nuova misura restituisce BLANK per i primi 12 mesi (perché nessuna vendita è stata registrata prima dell'anno fiscale 2017).

1. Si noti che il valore della misura **Sales YoY Growth** per **2018 Jul** è il valore **Sales** per **2017 Jul**.

    ![Immagine 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    > *Ora che la "parte difficile" della formula è stata testata, è possibile sovrascrivere la misura con la formula finale che calcola il risultato della crescita.*

1. Per completare la misura, sovrascrivere la misura **Sales YoY Growth** con questa formula e formattarla come percentuale con due cifre decimali:

    ```DAX
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     DIVIDE(  
     (SUM(Sales[Sales]) - SalesPriorYear),  
     SalesPriorYear  
     )
    ```

1. Nella formula nella clausola **RETURN** si noti che viene fatto riferimento due volte alla variabile.

1. Osservare che la crescita YoY per **2018 Jul** è **392.83%**.

    ![Immagine 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    > *La misura di crescita YoY identifica quasi il 400% (o 4x) aumento delle vendite nello stesso periodo dell'anno precedente.*

1. Nella vista Modello inserire le due nuove misure in una cartella di visualizzazione denominata **Time Intelligence**.

    ![Immagine 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

## Lab completato
