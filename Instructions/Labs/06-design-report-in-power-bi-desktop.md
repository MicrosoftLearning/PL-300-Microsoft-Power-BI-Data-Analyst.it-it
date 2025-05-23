---
lab:
  title: Progettare un report in Power BI Desktop
  module: Create Reports in Power BI Desktop
---

# Progettare un report in Power BI Desktop

## Presentazione del lab

In questo lab verrà creato un report di tre pagine. Verrà quindi pubblicato in Power BI, in cui si aprirà e si interagirà con il report.

Contenuto del lab:

- Progettare un report
- Configurare campi visivi e proprietà del formato

**Il lab dovrebbe richiedere circa 45 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/06-design-report-in-power-bi-desktop/06-design-report.zip`


Estrarre la cartella nella **cartella C:\Users\Student\Downloads\06-design-report** .

Aprire il **file 06-Starter-Sales Analysis.pbix** .

> ***Nota**: è possibile ignorare l'accesso selezionando **Annulla**. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche.*

## Progettare la pagina 1

In questo esercizio verrà progettata la prima pagina del report. Completata la progettazione, la pagina sarà simile alla seguente:

![Immagine della pagina 1, che comprende un logo, due filtri dei dati e tre oggetti visivi.](Linked_image_Files/06-finished-report-page.png)

1. In Power BI Desktop rinominare la pagina, in basso a sinistra fare clic con il pulsante destro del mouse sulla **pagina 1**, quindi **rinominare** la pagina come **Panoramica**.

    > *Suggerimento: è anche possibile fare doppio clic sul nome della pagina per rinominarlo.*

1. Per aggiungere un'immagine, nella scheda della barra multifunzione **Inserisci** selezionare **Immagine** all'interno del gruppo **Elementi**.

    ![Immagine 1](Linked_image_Files/07-design-report-in-power-bi-desktop_image15.png)

1. **Nella finestra Apri** passare alla **cartella C:\Users\Student\Downloads\06-design-report**.

1. Selezionare il file **AdventureWorksLogo.jpg** e quindi **Apri**.

1. Trascinare l'immagine per posizionarla nell'angolo superiore sinistro, quindi trascinare anche i marcatori per ridimensionarla.

     ![Figura 12](Linked_image_Files/07-design-report-in-power-bi-desktop_image17.png)

1. Per aggiungere un filtro dei dati, deselezionare prima di tutto l'immagine facendo clic su un'area vuota della pagina del report, quindi selezionare il **** filtro dei **dati nel riquadro Visualizzazioni**.

     ![Immagine 49](Linked_image_Files/07-design-report-in-power-bi-desktop_image18.png)

1. **Nel riquadro Dati** trascinare il **campo Data \| Year** (non il **livello Anno** della gerarchia) nel **** campo filtro dei dati nel riquadro Visualizzazioni.

    > *I lab usano una notazione abbreviata per fare riferimento a un campo. Sarà simile al seguente: **Data \| Anno**. In questo esempio Date **** è il nome della tabella e **Year** è il nome del campo.*

1. Per convertire il filtro dei dati da un elenco a discesa, passare a **Visualizzazioni > Formato oggetto visivo > Impostazioni filtro dei dati di Visual > > Stile** e quindi selezionare **Elenco a discesa** dal menu a discesa.

    ![Stile filtro dei dati](Linked_image_Files/06_slicer_style.png)

1. Ridimensionare e posizionare il filtro dei dati in modo che si trovi sotto l'immagine e abbia la stessa larghezza dell'immagine.

     ![Figura 19](Linked_image_Files/07-design-report-in-power-bi-desktop_image20.png)

1. Nel filtro dei dati **Year** aprire l'elenco a discesa, selezionare **FY2020** e quindi comprimere l'elenco a discesa.
    > *La pagina del report è ora filtrata in base all'anno **FY2020**.*

     ![Figura 20](Linked_image_Files/07-design-report-in-power-bi-desktop_image21.png)

1. Deselezionare il filtro dei dati facendo clic su un'area vuota della pagina del report.

1. Creare un secondo filtro dei dati in base al campo **Region \| Region** (non in base al livello **Region** della gerarchia).

1. Lasciare il filtro dei dati come elenco, quindi ridimensionarlo e posizionarlo sotto il filtro dei dati **Year**.

     ![Figura 21](Linked_image_Files/07-design-report-in-power-bi-desktop_image22.png)

1. Deselezionare il filtro dei dati facendo clic su un'area vuota della pagina del report.

1. Per aggiungere un grafico alla pagina, nel riquadro **Visualizzazioni** selezionare il tipo di oggetto visivo **Grafico a linee e istogramma in pila**.

     ![Immagine 51](Linked_image_Files/07-design-report-in-power-bi-desktop_image26.png)

1. Ridimensionare e posizionare l'oggetto visivo in modo che si trovi a destra del logo, riempiendo la pagina del report in larghezza.

     ![Immagine 26](Linked_image_Files/07-design-report-in-power-bi-desktop_image27.png)

1. Trascinare i campi seguenti nell'oggetto visivo:

     - **Date \| Month**
     - **Sales \| Sales**

1. Nel riquadro campi visivi (che si trova sotto il **riquadro Visualizzazioni**), si noti che i campi vengono assegnati all'asse **** X e **alle aree asse y** della colonna.

    > *Trascinando i campi in un oggetto visivo, verranno aggiunti a aree/aree predefinite. Per la precisione, è possibile trascinare i campi direttamente nei pozzi/aree, come si farà successivamente.*

     ![Figura 27](Linked_image_Files/07-design-report-in-power-bi-desktop_image28_N.png)

1. **Dal riquadro Dati** trascinare il **campo Sales \| Profit Margin** nell'area **/area asse y** linea.

     ![Immagine 28](Linked_image_Files/07-design-report-in-power-bi-desktop_image29.png)

1. Si noti che l'oggetto visivo ha solo 11 mesi.

    > *L'ultimo mese dell'anno, 2020 giugno, non ha ancora vendite (ancora). Per impostazione predefinita, l'oggetto visivo ha eliminato mesi con vendite BLANK. Si configurerà ora l'oggetto visivo per visualizzare tutti i mesi.*

1. Nel riquadro campi visivi, nell'area area/area dell'area **** asse X, per il **campo Mese** selezionare la freccia rivolta verso il basso e quindi selezionare **Mostra elementi senza dati**.

    > *Si noti che ora viene visualizzato il mese **2020 giugno** .*

     ![Immagine 52](Linked_image_Files/07-design-report-in-power-bi-desktop_image30.png)

1. Deselezionare il grafico facendo clic su un'area vuota della pagina del report.

1. Per aggiungere un grafico alla pagina, nel **riquadro Visualizzazioni** selezionare il **tipo di oggetto visivo Istogramma** in pila.

     ![Immagine 53](Linked_image_Files/07-stacked-column-chart.png)

1. Ridimensionare e posizionare l'oggetto visivo in modo che si trovi sotto l'istogramma o grafico a linee, riempiendo per metà il grafico al di sopra.

     ![Immagine 33](Linked_image_Files/07-design-report-in-power-bi-desktop_image32.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

     - Asse X: **Paese dell'area \|**
     - Asse Y: **Sales Sales \|**
     - Legenda: **Categoria prodotto \|**

1. Deselezionare il grafico facendo clic su un'area vuota della pagina del report.

1. Per aggiungere un grafico alla pagina, nel riquadro **Visualizzazioni** fare clic sul tipo di oggetto visivo **Grafico a barre in pila**.

     ![Immagine 54](Linked_image_Files/07-design-report-in-power-bi-desktop_image33.png)

1. Ridimensionare e posizionare l'oggetto visivo in modo da riempire lo spazio rimanente della pagina del report.

     ![Figura 35](Linked_image_Files/07-design-report-in-power-bi-desktop_image34.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

     - Asse Y: **Categoria prodotto \|**
     - Asse X: **Sales \| Quantity**

1. Per formattare l'oggetto visivo, aprire il riquadro **Formato**.

     ![Immagine 3](Linked_image_Files/07-design-report-in-power-bi-desktop_image35.png)

1. Espandere il gruppo **Barre** e quindi il gruppo **Colori**, quindi impostare la proprietà **Colore predefinito** su un colore appropriato, a complemento del grafico a linee o dell'istogramma.

1. **Attivare** la proprietà **Etichette dati**.

     ![Immagine 2](Linked_image_Files/07-design-report-in-power-bi-desktop_image36.png)

1. Salvare il file di Power BI Desktop.

*La progettazione della prima pagina è stata completata.*

## Progettare la pagina 2

In questo esercizio verrà progettata la seconda pagina del report. Completata la progettazione, la pagina sarà simile alla seguente:

 ![Immagine della pagina 2, che comprende un filtro dei dati e una matrice.](Linked_image_Files/07-design-report-in-power-bi-desktop_image37.png)

> ***Importante**: quando sono già state fornite istruzioni dettagliate nei lab, i passaggi del lab forniranno istruzioni più concise. Se sono necessarie le istruzioni dettagliate, è possibile fare riferimento ad altre attività in questo lab.*

1. Per creare una nuova pagina, in basso a sinistra selezionare l'icona con il segno più e rinominare la nuova pagina in **Profit**.

1. Aggiungere un filtro dei dati basato sul campo **Region \| Region**.

1. Usare il **riquadro Formato** per abilitare l'opzione "Seleziona tutto" (nelle impostazioni filtro dei **dati > gruppo Selezione** ).

1. Ridimensionare e posizionare il filtro dei dati in modo che si trovi sul lato sinistro della pagina del report, a circa metà altezza della pagina.

     ![Immagine 44](Linked_image_Files/07-design-report-in-power-bi-desktop_image40.png)

1. Aggiungere un oggetto visivo matrice, ridimensionarlo e posizionarlo in modo da riempire lo spazio rimanente della pagina del report

     ![Immagine 45](Linked_image_Files/07-design-report-in-power-bi-desktop_image41.png)

1. Aggiungere la gerarchia **Date \| Fiscal** all'area **Righe** della matrice.

     ![Immagine 46](Linked_image_Files/07-design-report-in-power-bi-desktop_image42.png)

1. Aggiungere i cinque campi seguenti della tabella **Sales** all'area **Valori**:

     - **Ordini** (dalla **cartella Conteggi** )
     - **Vendite**
     - **Costii**
     - **Profitto** (dalla **cartella Prezzi** )
     - **Profit Margin** (dalla **cartella Pricing** )


     ![Immagine 55](Linked_image_Files/07-design-report-in-power-bi-desktop_image43.png)

1. Nel riquadro **Filtri** (situato a sinistra del riquadro **Visualizzazioni**) osservare l'area **Filtri in questa pagina** (potrebbe essere necessario scorrere verso il basso).

     ![Immagine 57](Linked_image_Files/07-design-report-in-power-bi-desktop_image44.png)

1. Dal riquadro Dati trascinare il campo Categoria prodotto nell'area Filtro in questa pagina.From the **Data** pane, drag the **Product \| Category** field into the **Filter On This Page** well/area.

    > *I campi aggiunti al **riquadro Filtri** possono ottenere lo stesso risultato di un filtro dei dati. Una differenza è che non occupano spazio nella pagina del report. Un'altra differenza consiste nel fatto che possono essere configurati per ottenere requisiti di filtro più sofisticati.*

1. All'interno della scheda Filtro in alto a destra selezionare la freccia per comprimere la scheda.

1. Aggiungere ognuno dei campi seguenti della tabella **Product** all'area **Filtri in questa pagina**, comprimendoli tutti, direttamente sotto la scheda **Category**:

     - **Sottocategoria**
     - **Prodotto**
     - **Color**

     ![Immagine 60](Linked_image_Files/07-design-report-in-power-bi-desktop_image46.png)

1. Salvare il file di Power BI Desktop.

*La progettazione della seconda pagina è stata completata.*

## Progettare la pagina 3

In questo esercizio verrà progettata la terza pagina del report e la pagina finale. Completata la progettazione, la pagina sarà simile alla seguente:

 ![Immagine della pagina 3, che comprende un filtro dei dati e tre oggetti visivi.](Linked_image_Files/07-design-report-in-power-bi-desktop_image47.png)

1. Creare una nuova pagina, quindi rinominarla **My Performance**.

1. Per simulare le prestazioni dei filtri di sicurezza a livello di riga, trascinare il campo **Salesperson (Performance) \| Salesperson** nei filtri a livello di pagina nel riquadro dei filtri.

     ![Immagine del campo Salesperson nel riquadro dei filtri.](Linked_image_Files/07-design-report-in-power-bi-desktop_image999.png)

1. Selezionare **Michael Blythe**. I dati nella pagina del report **My Performance** verranno ora filtrati per visualizzare solo i dati di Michael Blythe.

1. Aggiungere un filtro dei dati a discesa basato sul campo **Date \| Year**, quindi ridimensionarlo e posizionarlo nell'angolo in alto a sinistra della pagina.

     ![Immagine 70](Linked_image_Files/07-design-report-in-power-bi-desktop_image49.png)

1. Nel filtro dei dati impostare la pagina in modo da filtrare in base a **FY2019**.

     ![Immagine 71](Linked_image_Files/07-design-report-in-power-bi-desktop_image50.png)

1. Aggiungere un oggetto visivo **Scheda con più righe**, quindi ridimensionarlo e riposizionarlo in modo che si trovi a destra del filtro dei dati e riempia la larghezza rimanente della pagina.

     ![Immagine 56](Linked_image_Files/07-design-report-in-power-bi-desktop_image51.png)

     ![Immagine 74](Linked_image_Files/07-design-report-in-power-bi-desktop_image52.png)

1. Aggiungere i quattro campi seguenti all'oggetto visivo:

     - **Sales \| Sales**
     - **Destinazione di destinazione \|**
     - **Varianza destinazioni \|**
     - **Margine di varianza destinazioni \|**

1. Formattare l'oggetto visivo:

     - Nel gruppo **Valori callout** aumentare la proprietà **Dimensione testo** a **28pt**

     - **Nel gruppo Generale > Effetti > sfondo** impostare Color **** su un colore grigio chiaro (ad esempio "Bianco, 20% più scuro) per assegnare il contrasto

         ![Immagine 79](Linked_image_Files/07-design-report-in-power-bi-desktop_image53.png)

1. Aggiungere un oggetto visivo **Grafico a barre raggruppate**, quindi ridimensionarlo e posizionarlo in modo che si trovi sotto l'oggetto visivo Scheda con più righe e riempia l'altezza rimanente della pagina e metà della larghezza dell'oggetto visivo scheda con più righe.

     ![Immagine 59](Linked_image_Files/07-design-report-in-power-bi-desktop_image54.png)

     ![Immagine 78](Linked_image_Files/07-design-report-in-power-bi-desktop_image55.png)

1. Aggiungere i campi seguenti nelle aree dell'oggetto visivo:

     - Asse Y: **Mese data \|**
     - Asse X: **Sales Sales \|** and **Targets \| Target**

         ![Immagine 80](Linked_image_Files/07-design-report-in-power-bi-desktop_image56.png)

1. Per creare una copia dell'oggetto visivo, premere **CTRL + C**, quindi premere **CTRL + V**.

1. Posizionare il nuovo oggetto visivo a destra dell'oggetto visivo originale.

     ![Immagine 82](Linked_image_Files/07-design-report-in-power-bi-desktop_image57.png)

1. Per modificare il tipo di visualizzazione, nel riquadro **Visualizzazioni** selezionare **Istogramma a colonne raggruppate**.

     > *È ora possibile visualizzare gli stessi dati espressi da due tipi di visualizzazione diversi.*

     ![Immagine 61](Linked_image_Files/07-design-report-in-power-bi-desktop_image58.png)

 *La progettazione della pagina finale è stata completata.*

## Pubblicare ed esplorare il report

In questo esercizio si pubblicherà il report nel servizio Power BI ed si esaminerà il comportamento del report pubblicato.

> **Nota**: è possibile esaminare il resto dell'esercizio, anche se non si ha accesso al servizio Power BI online per eseguire direttamente le attività.

1. Selezionare la **pagina Panoramica** e quindi salvare il file di Power BI Desktop.

1. Nella scheda della barra multifunzione **Home** selezionare **Pubblica** all'interno del gruppo **Condividi**.

    > *Se non è già stato eseguito l'accesso a Power BI Desktop, è necessario eseguire l'accesso per la pubblicazione.*

     ![Immagine 67](Linked_image_Files/07-design-report-in-power-bi-desktop_image59.png)

1. Nella finestra **Pubblica in Power BI** si noti che l'opzione **Area di lavoro** è selezionata.

    > *Non verranno illustrati in dettaglio i diversi elementi all'interno del servizio Power BI in questo lab.*

1. Per pubblicare il report, selezionare **Seleziona**. L'operazione potrebbe richiedere alcuni istanti.

1. Al termine della pubblicazione, fare clic su **Chiudi**.

1. Aprire un browser Microsoft Edge, quindi accedere all'indirizzo `https://app.powerbi.com`.

1. Nella finestra del browser Microsoft Edge nel servizio Power BI espandere **Area di lavoro personale** nel **riquadro di spostamento** (a sinistra, potrebbe essere compresso).

    ![Screenshot 2024-04-18 101424](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/346415bc-e559-4559-84b5-ef3a1f808461)

1. Esaminare il contenuto dell'area di lavoro.

    - Esistono quattro tipi di elementi che possono esistere in un'area di lavoro e si parla di **report** e **modelli semantici**.

    - Potrebbe essere necessario aggiornare il browser Microsoft Edge se il modello semantico non è visibile.

    - Quando è stato pubblicato il file di Power BI Desktop, il modello di dati è stato pubblicato come modello semantico.

1. Per esplorare il report, selezionare il **report Sales Analysis** .

1. A sinistra, nel riquadro **Pagine** selezionare la pagina **Overview**.

1. Nel filtro dei dati **Regions** tenendo premuto il tasto **CTRL** selezionare più aree.

1. Nel grafico a linee o nell'istogramma selezionare una colonna del mese per applicare un filtro incrociato alla pagina.

1. Quando si preme CTRL****, selezionare un altro mese.

     > *Nota: per impostazione predefinita, il filtro incrociato filtra tutti gli altri oggetti visivi nella pagina.*

1. Si noti che il grafico a barre è filtrato ed evidenziato e che la parte in grassetto delle barre rappresenta i mesi filtrati.

1. Passare il puntatore del mouse sull'oggetto visivo grafico a barre e quindi sull'icona del filtro in alto a destra.

    > *L'icona del filtro consente di comprendere tutti i filtri applicati all'oggetto visivo, inclusi i filtri dei dati e i filtri incrociati di altri oggetti visivi.*

1. Passare il cursore su una barra, quindi osservare le informazioni della descrizione comando.

1. Per annullare il filtro incrociato, fare clic su un'area vuota dell'oggetto visivo nel grafico a linee o nell'istogramma.

1. Passare il cursore sull'oggetto visivo istogramma in pila e quindi in alto a destra selezionare l'icona **Modalità** messa a fuoco.

    > *La modalità messa a fuoco consente di ingrandire l'oggetto visivo alle dimensioni della pagina complete.*

     ![Immagine 96](Linked_image_Files/07-published-report-visual-filter.png)

1. Passare il puntatore del mouse su segmenti diversi dei grafici a barre per visualizzare le descrizioni comando.

1. Per tornare alla pagina del report, fare clic su **Torna al report** in alto a sinistra.

     ![Immagine 86](Linked_image_Files/07-design-report-in-power-bi-desktop_image66.png)

1. Passare di nuovo il cursore su uno degli oggetti visivi, quindi in alto a destra selezionare i puntini di sospensione (...), quindi notare le opzioni di menu. Provare ognuna delle opzioni, ad eccezione di quelle all'interno **di Condividi**.

     ![Immagine 97](Linked_image_Files/07-design-report-in-power-bi-desktop_image67.png)

1. A sinistra, nel riquadro **Pagine** selezionare la pagina **Profit**.

     ![Immagine 84](Linked_image_Files/07-design-report-in-power-bi-desktop_image68.png)

1. Si noti che il filtro dei dati **Region** ha una selezione diversa rispetto al filtro dei dati **Region** nella pagina **Overview**.

    > *I filtri dei dati non sono sincronizzati. Si modificherà la progettazione del report per assicurarsi che vengano sincronizzate tra le pagine nel **lab Migliorare un report in Power BI Desktop** .*

1. Nel riquadro **Filtri** a destra espandere una scheda filtro e applicare alcuni filtri.

    > *Il riquadro **Filtri** consente di definire più filtri che potrebbero adattarsi a una pagina come filtri dei dati.*

1. Nell'oggetto visivo matrice usare il pulsante più (+) per esaminare la gerarchia **Fiscal**.

1. Selezionare la pagina **My Performance**.

     ![Immagine 89](Linked_image_Files/07-design-report-in-power-bi-desktop_image69.png)

1. In alto a destra nella barra dei menu fare clic su **Visualizza** e quindi selezionare **Schermo intero**.

     ![Immagine 98](Linked_image_Files/07-design-report-in-power-bi-desktop_image70.png)

1. Interagire con la pagina modificando il filtro dei dati e applicando un filtro incrociato alla pagina.

1. Nella parte inferiore della finestra notare i comandi per cambiare pagina, spostarsi avanti o indietro tra le pagine o uscire dalla modalità schermo intero.

1. Selezionare l'icona a destra per uscire dalla modalità schermo intero.

     ![Immagine 91](Linked_image_Files/07-design-report-in-power-bi-desktop_image71.png)

## Lab completato
