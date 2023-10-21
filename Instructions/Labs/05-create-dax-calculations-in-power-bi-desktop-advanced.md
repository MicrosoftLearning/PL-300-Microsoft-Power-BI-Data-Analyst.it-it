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

**Questo lab richiede circa 45 minuti.**

## **Usare il contesto di filtro**

*Importante: se si continua dal lab precedente (e il lab è stato completato correttamente), non completare questa attività; Continuare invece dall'attività successiva.*

1. Aprire Power BI Desktop.

    ![icona Power BI Desktop](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *Suggerimento: per impostazione predefinita, la finestra di dialogo Introduzione viene visualizzata davanti a Power BI Desktop. È possibile scegliere di eseguire l'accesso e quindi chiudere il popup.*

1. Per aprire il file di Power BI Desktop iniziale, selezionare file **> Apri report > Sfoglia report**.

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Starter**  e aprire il file **Sales Analysis** .

1. Chiudere eventuali finestre aperte di carattere informativo.

1. Si noti il messaggio di avviso giallo sotto la barra multifunzione. 

    *Questo messaggio avvisa il fatto che le query non sono state applicate al caricamento come tabelle del modello. Le query verranno applicate più avanti in questo lab.*
    
    *Per ignorare il messaggio di avviso, a destra del messaggio di avviso giallo selezionare **X**.*

1. Per creare una copia del file, passare a **File > Salva con** nome e salvare nella cartella **D:\PL300\MySolution** .

## **Creare un oggetto visivo matrice**

In questa attività verrà creato un oggetto visivo matrice per supportare il test delle nuove misure.

1. In Power BI Desktop nella vista Report creare una nuova pagina del report.

1. In **Pagina 3** aggiungere un oggetto visivo matrice.

    ![Immagine 13](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image10.png)

1. Ridimensionare l'oggetto visivo matrice in modo da riempire l'intera pagina.

1. Per configurare i campi visivi matrice, dal riquadro **Dati** trascinare la gerarchia **Aree \|** geografiche e rilasciarla all'interno dell'oggetto visivo.
    
    *Nei lab viene usata una notazione abbreviata per fare riferimento a un campo o a una gerarchia, simile al seguente: **Region \| Regions**. In questo esempio, **Region** è il nome della tabella e **Regions** è il nome della gerarchia.*

1. Aggiungere anche il campo **Sales \| Sales**.

1. Per espandere l'intera gerarchia, nell'angolo superiore destro dell'oggetto visivo matrice fare clic sull'icona con la freccia con biforcazione.
    
    *Si ricorderà che la gerarchia **Regions** include i livelli **Group**, **Country** e **Region**.*

    ![Immagine 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

1. Per formattare l'oggetto visivo, nel riquadro **Visualizzazioni** selezionare il riquadro **Formato**.

    ![Immagine 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

1. Nella casella **Cerca** immettere **Con rientri**.

1. Impostare la proprietà **Layout con rientri** su **Disattivato**.

    ![Immagine 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

1. Verificare che l'oggetto visivo matrice ora includa quattro intestazioni di colonna.

    ![Immagine 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    *In Adventure Works le aree di vendita sono organizzate in gruppi, paesi e aree geografiche. Tutti i paesi, ad eccezione degli Stati Uniti, hanno una sola area il cui nome corrisponde al nome del paese. Poiché gli Stati Uniti sono un territorio di vendita di grandi dimensioni, sono suddivisi in cinque aree di vendita.*

    *In questo esercizio verranno create diverse misure che vengono quindi testate aggiungendole all'oggetto visivo matrice.*

## **Modificare il contesto del filtro**

In questa attività verranno create diverse misure con espressioni DAX che usano la funzione CALCULATE() per modificare il contesto di filtro.

1. Aggiungere una misura alla tabella **Sales** basata sull'espressione seguente:
    
     *Per praticità, tutte le definizioni DAX in questo lab possono essere copiate dal file **D:\PL300\Labs\05-create-dax-calculations-in-power-bi-desktop-advanced\Assets\Snippets.txt**.*


    **DAX**


    ```
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```


    *La funzione CALCULATE() è una funzione avanzata usata per modificare il contesto di filtro. Il primo argomento accetta un'espressione o una misura (una misura è semplicemente un'espressione con nome). Gli argomenti successivi consentono di modificare il contesto di filtro.*

    *La funzione REMOVEFILTERS() rimuove i filtri attivi. Può essere senza argomenti o accettare una tabella, una colonna o più colonne come argomento.*

    *In questa formula la misura calcola la somma della colonna **Sales** in un contesto di filtro modificato che rimuove tutti i filtri applicati alle colonne della tabella **Region**.*

1. Aggiungere la misura **Sales All Region** all'oggetto visivo matrice.

    ![Immagine 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

1. Si noti che la misura **Sales All Region** calcola il totale di tutte le vendite dell'area per ogni area, paese (subtotale) e gruppo (subtotale).

    *La nuova misura restituisce ancora un risultato utile. Quando le vendite di un gruppo, di un paese o di un'area sono divise in base a questo valore, verrà prodotta una percentuale utile chiamata "percentuale del totale complessivo".*

1. Nel riquadro **Dati** verificare che la misura **Sales All Region** sia selezionata (se selezionata, avrà uno sfondo grigio scuro) e quindi nella barra della formula sostituire il nome della misura e la formula con la formula seguente:

    *Suggerimento: per sostituire la formula esistente, copiare prima il frammento di codice. Selezionare quindi all'interno della barra della formula e premere **CTRL+A** per selezionare tutto il testo. Premere **quindi CTRL+V** per incollare il frammento di codice per sovrascrivere il testo selezionato. Quindi premere **INVIO**.*


    **DAX**


    ```
    Sales % All Region =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region)  
     )  
    )
    ```

    *La misura è stata rinominata per riflettere accuratamente la formula aggiornata. La funzione DIVIDE() divide la misura **Sales** (non modificata dal contesto di filtro) per la misura **Sales** di un contesto modificato che rimuove tutti i filtri applicati alla tabella **Region**.*

1. Nell'oggetto visivo matrice si noti che la misura è stata rinominata e che ora viene visualizzato un valore diverso per ogni gruppo, paese e area geografica.

1. Formattare la misura **Sales % All Region** come percentuale con due cifre decimali.

1. Nell'oggetto visivo matrice esaminare i valori della misura **Sales% All Region**.

    ![Immagine 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

1. Aggiungere un'altra misura alla tabella **Sales** basata sull'espressione seguente e formattata come percentuale:


    **DAX**

    ```
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

    *La differenza è che il denominatore modifica il contesto di filtro rimuovendo i filtri nella colonna **Region** della tabella **Region** , non tutte le colonne della tabella **Region** . Significa che tutti i filtri applicati alle colonne del gruppo o del paese vengono mantenuti. Otterrà un risultato che rappresenta le vendite come percentuale di paese.*

1. Aggiungere la misura **Sales % Country** all'oggetto visivo matrice.

1. Si noti che solo le aree Stati Uniti producono un valore che non è 100%.
    
    *È possibile ricordare che solo il Stati Uniti ha più aree. Tutti gli altri paesi comprendono una singola regione, che spiega perché sono tutti del 100%.*

    ![Immagine 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    

1. Per migliorare la leggibilità di questa misura nell'oggetto visivo, sovrascrivere la misura **Sales % Country** con questa formula migliorata.


    **DAX**


    ```
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


    *La funzione IF() usa la funzione ISINSCOPE() per verificare se la colonna region è il livello in una gerarchia di livelli. Se true, viene valutata la funzione DIVIDE(). Se false, viene restituito un valore vuoto perché la colonna region non è nell'ambito.*

1. Si noti che la misura **Sales % Country** ora restituisce un valore solo quando un'area è nell'ambito.

    ![Immagine 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

1. Aggiungere un'altra misura alla tabella **Sales** basata sull'espressione seguente e formattata come percentuale:


    **DAX**


    ```
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


    *Per visualizzare le vendite come percentuale del gruppo, è possibile applicare due filtri per rimuovere efficacemente i filtri in due colonne.*

1. Aggiungere la misura **Sales % Group** all'oggetto visivo matrice.

1. Per migliorare la leggibilità di questa misura nell'oggetto visivo, sovrascrivere la misura **Sales % Group** con questa formula migliorata.


    **DAX**


    ```
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

*Le misure aggiunte alla tabella **Sales** hanno modificato il contesto di filtro per ottenere la navigazione gerarchica. Si noti che il criterio per ottenere il calcolo di un subtotale richiede la rimozione di alcune colonne dal contesto di filtro. Inoltre, per visualizzare un totale complessivo, tutte le colonne devono essere rimosse.*

## **Usare Business Intelligence per le gerarchie temporali**

In questo esercizio si creerà una misura di crescita annuale delle vendite (YTD) e una misura di crescita annuale (YoY).

## **Creare una misura YTD**

In questa attività si creerà una misura sales YTD.

1. Nella vista Report in **Pagina 2** osservare l'oggetto visivo matrice che visualizza varie misure con anni e mesi raggruppati nelle righe.

2. Aggiungere una misura alla tabella **Sales** basata sull'espressione seguente e formattata con zero cifre decimali:


    **DAX**


    ```
    Sales YTD =  
    TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```


    *La funzione TOTALYTD() valuta un'espressione, in questo caso la somma della colonna **Sales**, su una determinata colonna di data. La colonna data deve appartenere a una tabella data contrassegnata come tabella data, come è stato fatto nel lab **Creare calcoli DAX in Power BI Desktop**.*

    *La funzione può anche accettare un terzo argomento facoltativo che rappresenta l'ultima data di un anno. L'assenza di questa data significa che il 31 dicembre è l'ultima data dell'anno. Per Adventure Works, poiché giugno è l'ultimo mese dell'anno, viene usato "6-30".*

3. Aggiungere il campo **Sales** e la misura **Sales YTD** all'oggetto visivo matrice.

4. Si noti l'accumulo dei valori delle vendite nell'anno.

    ![Immagine 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

    *La funzione TOTALYTD() esegue la modifica del filtro, in particolare la modifica dei filtri temporali. Ad esempio, per calcolare le vendite YTD per settembre 2017 (il terzo mese dell'anno fiscale), tutti i filtri nella tabella **Date** vengono rimossi e sostituiti con un nuovo filtro di date che inizia all'inizio dell'anno (1 luglio 2017) e si estende fino all'ultima data del periodo di date nel contesto (30 settembre 2017).*

    *In DAX sono disponibili numerose funzionalità di Business Intelligence per le gerarchie temporali per supportare le modifiche di filtri temporali comuni.*

## **Creare una misura di crescita YoY**

In questa attività si creerà una misura di crescita YoY di vendita.

1. Aggiungere un'altra misura alla tabella **Sales** , in base all'espressione seguente:


    **DAX**


    ```
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


    *La misura **Sales YoY Growth** usa una variabile. Le variabili consentono di semplificare la formula e di essere più efficienti se si usa la logica più volte all'interno di una formula.*

    *Le variabili vengono dichiarate con un nome univoco e l'espressione di misura deve quindi essere restituita dopo la parola chiave **RETURN** . A differenza di altre variabili del linguaggio di codifica, le variabili DAX possono essere usate solo all'interno della singola formula.*

    *La variabile **SalesPriorYear** viene assegnata un'espressione che calcola la somma della colonna **Sales** in un contesto modificato che usa la funzione PARALLELPERIOD() per spostare 12 mesi da ogni data nel contesto del filtro.*

1. Aggiungere la misura **Sales YoY Growth** all'oggetto visivo matrice.

1. Si noti che la nuova misura restituisce BLANK per i primi 12 mesi (perché nessuna vendita è stata registrata prima dell'anno fiscale 2017).

1. Si noti che il valore della misura **Sales YoY Growth** per **2018 Jul** è il valore **Sales** per **2017 Jul**.

    ![Immagine 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    *Ora che la "parte difficile" della formula è stata testata, è possibile sovrascrivere la misura con la formula finale che calcola il risultato della crescita.*

1. Per completare la misura, sovrascrivere la misura **Sales YoY Growth** con questa formula e formattarla come percentuale con due cifre decimali:


    **DAX**


    ```
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

    *La misura di crescita YoY identifica quasi il 400% (o 4x) aumento delle vendite durante lo stesso periodo dell'anno precedente.*

1. Nella vista Modello inserire le due nuove misure in una cartella di visualizzazione denominata **Time Intelligence**.

    ![Immagine 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

### **Completare il lab**

In questa attività si completerà il lab.

1. Per eseguire la pulizia della soluzione pronta per lo sviluppo di report, fare clic con il pulsante destro del mouse sulla scheda **Pagina 2** in basso a sinistra e quindi scegliere **Elimina pagina**. Quando viene richiesto di eliminare la pagina, selezionare **Elimina**.

1. Eliminare anche la **pagina 3**.

1. Nella pagina rimanente, per cancellare la pagina, selezionare l'oggetto visivo tabella e premere il tasto **CANC**.

1. Salvare il file di Power BI Desktop.

1. Se si intende iniziare il lab successivo, lasciare aperto Power BI Desktop.

*Verrà creato un report basato sul modello di dati nel lab **Progettazione di un report in Power BI Desktop** lab.*
