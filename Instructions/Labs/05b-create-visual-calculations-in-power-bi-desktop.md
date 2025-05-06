---
lab:
  title: Creare calcoli visivi in Power BI Desktop
  module: Create Visual Calculations in Power BI Desktop
---

# Creare calcoli visivi in Power BI Desktop

## **Presentazione del lab**

In questo lab verranno creati calcoli visivi usando DAX (Data Analysis Expressions). 

Contenuto del lab:

- Creare e modificare calcoli visivi
- Usare le funzioni PREVIOUS(), RUNNINGSUM() e MOVINGAVERAGE() per creare metriche di confronto tra ogni anno fiscale
- Usare il parametro Axis facoltativo durante la creazione di metriche di confronto.
- Usare il parametro Facoltativo Reset per personalizzare i calcoli cumulativi in un asse multi-livellamento.

**Questo lab dovrebbe richiedere circa 30 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/05b-create-visual-calculations-in-power-bi-desktop/05b-visual-calculations.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\05b-visual-calculations** .

Aprire il **file 05b-Starter-Sales Analysis.pbix** .

> ***Nota**: è possibile ignorare l'accesso selezionando **Annulla**. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche.*

## Creare un oggetto visivo grafico a barre

In questa attività verrà creato un grafico a barre che mostra l'importo delle vendite, il costo totale del prodotto e il profitto per anno fiscale, con le metriche di confronto come descrizioni comando.

1. **Nel riquadro Visualizzazioni** selezionare il tipo di oggetto visivo grafico a barre cluster.

   ![Immagine 01](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image01.png)

1. **Nel riquadro Dati**, dall'interno della **tabella Date**, trascinare il **campo Year** nell'area **/area asse Y**.

1. Trascinare i **campi Sales** e **Cost** dalla **tabella Sales** nell'area **/area asse X** .

    > Si noti che quando si è aggiunto Sales and Cost all'oggetto visivo, la somma di ogni campo è stata calcolata automaticamente.

1. Ordinare il grafico **a barre risultante in base all'anno** crescente usando il menu a tre punti e selezionando **Anno** seguito da **Ordinamento crescente**:

   ![Immagine 02](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image02.png)

    > È ora disponibile un grafico a barre che mostra la somma delle vendite e la somma dei costi per anno ordinati in ordine cronologico.

### Aggiungere calcoli

1. Con il grafico a barre selezionato, selezionare **Nuovo calcolo** visivo nella barra multifunzione:

   ![Immagine 03](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image03.png)

1. Verrà visualizzata la finestra di modifica dei calcoli visivi. Nella barra della formula sopra la matrice visiva immettere l'espressione seguente e quindi immettere per eseguire il commit del calcolo:

    ```DAX
   Profit = [Sum of Sales] – [Sum of Cost]
    ```

1. Verificare di visualizzare ora una colonna Profit nella matrice visiva nella parte inferiore della schermata:

   ![Immagine 04](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image04.png)

1. Espandere il menu in **Nuovo calcolo** visivo e selezionare **Confronto precedente** tra le opzioni del modello:

    > **Rispetto a Previous** confronta un valore con un valore precedente, quindi viene visualizzato il valore Profit rispetto al valore precedente per Year.

   ![Immagine 05](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image05.png)

1. Nella barra della formula sostituire il `[Field]` segnaposto con `[Profit]` due volte ed eseguire il commit del calcolo.

1. Selezionare **Esecuzione della somma** dal menu modelli e sostituire il `[Field]` segnaposto con `[Profit]` ed eseguire il commit del calcolo.

    > **La somma** in esecuzione calcola la somma dei valori, aggiungendo il valore corrente ai valori precedenti, quindi viene visualizzato il totale degli anni correnti e precedenti.

1. Selezionare **Sposta media** dal menu modelli e sostituire il `[Field]` segnaposto con `[Profit]` e il `WindowSize` segnaposto con 2. A questo ora dovrebbe essere configurato quanto segue:

    > **La media** mobile calcola una media di un set di valori in una determinata finestra dividendo la somma dei valori in base alle dimensioni della finestra. Impostando la dimensione della finestra su 2, si calcola la media di due valori consecutivi. In questo esempio, i valori sono profitti annuali, quindi vediamo la media mobile per FY2019 è la media dei profitti per FY2018 e FY2019.

   ![Immagine 06](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image06.png)

1. Nell'area area/area dell'asse **** X selezionare l'icona di visibilità dei campi seguenti per nasconderli dall'oggetto visivo:

    - Sum of Sales
    - Sum of Cost
    - Margine

   ![Immagine 07](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image07.png)

    > Si noti che i campi e i calcoli nascosti non vengono più visualizzati nell'oggetto visivo.

1. **Nel riquadro Visualizzazioni** trascinare **Running sum** (Somma in esecuzione) e **Moving average (Media** mobile) nell'area **/area delle descrizioni comando**.  

1. Verificare che l'oggetto visivo soddisfi ora gli obiettivi. Uscire dalla schermata di modifica dei calcoli visivi nel report:

   ![Immagine 08](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image08.png)

    > È ora disponibile un grafico a barre con i valori seguenti: Somma delle vendite, Somma dei costi, Profitto e Profitto *rispetto alle descrizioni comando per La somma* in esecuzione profit e Media mobile* Profit**.*

## Creare un oggetto visivo matrice

In questa attività verrà creato un oggetto visivo matrice che confronta l'importo delle vendite per categoria rispetto al primo anno fiscale per ognuno degli anni successivi.

1. Nella **visualizzazione** Report creare una nuova pagina del report.

1. Nella **pagina 2** aggiungere un oggetto visivo matrice.

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

    - Righe: **Categoria prodotto \|**
    - Colonne: **Data \| Anno**
    - Valori: **Sales Sales \|**

    > *I lab usano una notazione abbreviata per fare riferimento a un campo. Sarà simile al seguente: **Data \| Anno**. In questo esempio Date **** è il nome della tabella e **Year** è il nome del campo.*

### Aggiungere calcoli

1. Con la matrice selezionata, selezionare **Nuovo calcolo** visivo nella barra multifunzione.

1. Nella finestra di modifica dei calcoli visivi digitare e salvare il calcolo seguente:

    ```DAX
   Versus first = [Sum of Sales] - FIRST([Sum of Sales])
    ```

    > Si noti che la matrice mostra la differenza nell'importo delle vendite per ogni categoria rispetto alla prima categoria.

1. Selezionare il campo **Rispetto prima** nell'area **Area/area Valori** e aggiornare il calcolo aggiungendo il valore ROWS per il parametro Axis a FIRST:

    ```DAX
   Versus first = [Sum of Sales] - FIRST([Sum of Sales], ROWS)
    ```

    > Si noti che nulla cambia perché ROWS è il valore predefinito per il parametro Axis.

1. Sostituire ROWS con COLUMNS e osservare che il calcolo confronta ora l'importo delle vendite per categoria rispetto al primo anno fiscale:

   ![Immagine 11](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image11.png)

    > Si noti che la **prima** colonna Versus per Total **Sales** restituisce zero anziché la differenza rispetto al primo anno fiscale. **Total Sales** si trova su un livello gerarchico diverso rispetto alle somme annuali, quindi considerato la prima colonna a tale livello.

1. Uscire dalla schermata di modifica dei calcoli visivi nel report.

## Creare un oggetto visivo grafico a linee

In questa attività verrà creato un grafico a linee che mostra la somma in esecuzione per le vendite. Questa somma verrà reimpostata all'inizio di ogni anno fiscale.

1. Nella **visualizzazione** Report creare una nuova pagina del report.

1. Nella **pagina 3** aggiungere un oggetto visivo grafico a linee.

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

    - Asse X: **Date \| Year** e **Date \| Quarter**
    - Asse Y: **Sales Sales \|**

### Aggiungere la somma in esecuzione

1. Con il grafico a linee selezionato, espandere il menu in **Nuovo calcolo** visivo e selezionare **Esecuzione somma** dalle opzioni del modello.

1. Sostituire il `[Field]` segnaposto con `[Sum of Sales]` ed eseguire il commit della modifica. L'oggetto visivo dovrebbe essere simile al seguente:

   ![Immagine 09](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image09.png)

### Aggiornare la somma in esecuzione per riavviare ogni nuovo anno fiscale

1. Mentre è ancora nella finestra di modifica dei calcoli visivi, selezionare il **campo Somma in esecuzione** sotto **asse** Y e aggiornare l'espressione per questo calcolo aggiungendo il parametro di reimpostazione HIGHESTPARENT ed eseguendo il commit delle modifiche:

    ```DAX
   Running sum = RUNNINGSUM([Sum of Sales], HIGHESTPARENT)
    ```

Verificare che la somma in esecuzione si riavvii per ogni nuovo anno fiscale:

   ![Immagine 10](Linked_image_Files/05b-create-visual-calculations-in-power-bi-desktop_image10.png)

## Lab completato
