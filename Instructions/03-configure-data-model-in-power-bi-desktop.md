---
lab:
  title: Modellare i dati in Power BI Desktop
  module: Module 4 - Design a Data Model in Power BI
ms.openlocfilehash: 1617d6a1a50e37a5dc7d9094eaa86057b2ddeee2
ms.sourcegitcommit: 9ea1e7e21b9b3c718030c94b1693d153a2010ec7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "147015366"
---
# <a name="model-data-in-power-bi-desktop"></a>**Modellare i dati in Power BI Desktop**

**Il tempo stimato per il completamento del lab è di 45 minuti**

In questo lab si inizierà a sviluppare il modello di dati. Il processo includerà la creazione di relazioni tra le tabelle e poi la configurazione delle proprietà delle tabelle e delle colonne per migliorare l'accessibilità e l'usabilità del modello di dati. Verranno anche create gerarchie e misure rapide.

Contenuto del lab:

- Creare le relazioni del modello

- Configurare le proprietà delle tabelle e delle colonne

- Creare gerarchie


### <a name="lab-story"></a>**Presentazione del lab**

Questo lab fa parte di una serie che comprende molti lab progettati come attività completa, dalla preparazione dei dati alla pubblicazione come report e dashboard. È possibile completare i lab nell'ordine desiderato. Se tuttavia si intende seguire più lab, è consigliabile procedere in questo ordine:

1. Preparare i dati in Power BI Desktop

2. Caricare i dati in Power BI Desktop

3. **Modellare i dati in Power BI Desktop**

5. Creare calcoli DAX in Power BI Desktop - Parte 1

6. Creare calcoli DAX in Power BI Desktop - Parte 2

7. Progettare un report in Power BI Desktop - Parte 1

8. Progettare un report in Power BI Desktop - Parte 2

9. Creare un dashboard di Power BI

10. Eseguire l'analisi dei dati in Power BI Desktop

11. Applicare la sicurezza a livello di riga

## <a name="exercise-1-create-model-relationships"></a>**Esercizio 1: Creare le relazioni del modello**

In questo esercizio verranno create le relazioni del modello.

### <a name="task-1-get-started"></a>**Attività 1: Operazioni preliminari**

In questa attività si configurerà l'ambiente per il lab.

*Importante: se si sta continuando dal lab precedente (e il lab è stato completato correttamente), non completare questa attività, ma passare a quella successiva.*

1. Per aprire Power BI Desktop, sulla barra delle applicazioni fare clic sul collegamento Microsoft Power BI Desktop.

    ![Figura 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

1. Per chiudere la finestra introduttiva, fare clic su **X** nella parte superiore sinistra della finestra.

    ![Immagine 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

1. Per aprire il file di avvio di Power BI Desktop, selezionare la scheda della barra multifunzione **File** per aprire la visualizzazione Backstage.

1. Selezionare **Apri report**.

    ![Immagine 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

1. Fare clic su **Esplora report**.

    ![Immagine 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Labs\03-configure-data-model-in-power-bi-desktop\Starter**.

1. Selezionare il file **Sales Analysis**.

1. Fare clic su **Apri**.

    ![Immagine 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

1. Chiudere eventuali finestre aperte di carattere informativo.

1. Per creare una copia del file, fare clic sulla scheda della barra multifunzione **File** per aprire la visualizzazione Backstage.

1. Selezionare **Salva con nome**.

    ![Figura 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

1. Se viene richiesto di applicare le modifiche, fare clic su **Applica**.

    ![Immagine 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

1. Nella finestra **Salva con nome** passare alla cartella **D:\PL300\MySolution**.

1. Fare clic su **Salva**.

    ![Immagine 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### <a name="task-2-create-model-relationships"></a>**Attività 2: Creare le relazioni del modello**

In questa attività verranno create le relazioni del modello.

1. Nella parte sinistra di Power BI Desktop fare clic sull'icona della visualizzazione **Modello**.

    ![Immagine 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. Se non vengono visualizzate tutte e sette le tabelle, scorrere orizzontalmente a destra, quindi trascinare e disporre le tabelle in modo più ravvicinato in modo che possano essere visualizzate tutte contemporaneamente.

    *Suggerimento: è anche possibile usare il controllo zoom disponibile nella parte inferiore della finestra.*

    *Nella visualizzazione Modello è possibile visualizzare ogni tabella e qualsiasi relazione (connettori tra le tabelle). Attualmente non sono presenti relazioni perché nel lab **Preparare i dati in Power BI Desktop** sono state disabilitate le opzioni per la relazione di caricamento dei dati.*

3. Per tornare alla visualizzazione Report, a sinistra, fare clic sull'icona della visualizzazione **Report**.

    ![Immagine 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. Per visualizzare tutti i campi delle tabelle, nel riquadro **Campi** fare clic con il pulsante destro del mouse su un'area vuota e quindi scegliere **Espandi tutto**.

    ![Immagine 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. Per creare un oggetto visivo Tabella, nel riquadro **Campi**, dall'interno della tabella **Product** selezionare il campo **Category**.

    ![Immagine 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

    *Nei lab viene usata una notazione abbreviata per fare riferimento a un campo, simile al seguente: **Product \| Category**. In questo esempio **Product** è il nome della tabella e **Category** è il nome del campo.*

6. Per aggiungere una colonna alla tabella, nel riquadro **Campi** selezionare il campo **Sales \| Sales**.

7. Si noti che l'oggetto visivo Tabella elenca quattro categorie di prodotti e che il valore Sales è lo stesso per ognuno e lo stesso per il totale.

    ![Immagine 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

    *Il problema è che la tabella è basata su campi da tabelle diverse. Si prevede che ogni categoria di prodotto visualizzi le vendite per tale categoria. Tuttavia, poiché non esiste una relazione del modello tra queste tabelle, la tabella **Sales** non viene filtrata. Si aggiungerà ora una relazione per propagare i filtri tra le tabelle.*

8. Nella scheda della barra multifunzione **Modellazione**, nel gruppo **Relazioni**, fare clic su **Gestisci relazioni**.

    ![Immagine 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. Nella finestra **Gestisci relazioni** si noti che non sono ancora state definite relazioni.

10. Per creare una relazione, fare clic su **Nuova**.

    ![Immagine 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. Nella finestra **Crea relazione**, nel primo elenco a discesa selezionare la tabella **Product**.

    ![Immagine 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. Nel secondo elenco a discesa (sotto la griglia della tabella **Product**) selezionare la tabella **Sales**.

    ![Immagine 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. Si noti che sono state selezionate automaticamente le colonne **ProductKey** in ogni tabella.

    *Le colonne sono state selezionate automaticamente perché condividono lo stesso nome e tipo di dati.*

14. Nell'elenco a discesa **Cardinalità** si noti che è selezionata l'opzione **Uno a molti (1:*)**.

    *La cardinalità è stata rilevata automaticamente, perché Power BI rileva che la colonna **ProductKey** della tabella **Product** contiene valori univoci. Le relazioni uno-a-molti rappresentano la cardinalità più comune e tutte le relazioni create in questo lab saranno di questo tipo.*

15. Nell'elenco a discesa **Direzione filtro incrociato** si noti che è selezionata l'opzione **Singola**.

    *La direzione di filtro singola indica che i filtri vengono propagati dal lato "uno" al lato "molti". In questo caso, significa che i filtri applicati alla tabella **Product** verranno propagati alla tabella **Sales**, ma non nell'altra direzione.*

16. Si noti che è selezionata l'opzione **Imposta come relazione attiva**.

    *Le relazioni attive propagheranno i filtri. È possibile contrassegnare una relazione come inattiva, in modo che i filtri non vengano propagati. Le relazioni inattive possono esistere quando sono presenti più percorsi di relazione tra le tabelle. In tal caso, i calcoli del modello possono usare funzioni speciali per attivarle.*

17. Fare clic su **OK**.

    ![Immagine 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. Nella finestra **Gestisci relazioni** osservare che la nuova relazione è elencata e quindi fare clic su **Chiudi**.

    ![Immagine 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. Nel report si noti che l'oggetto visivo Tabella è stato aggiornato per visualizzare valori diversi per ogni categoria di prodotto.

    ![Immagine 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

    *I filtri applicati alla tabella **Product** vengono ora propagati alla tabella **Sales**.*

20. Passare alla visualizzazione Modello e notare che è ora presente un connettore tra le due tabelle (non importa se le tabelle sono posizionate una accanto all'altra).

    ![Immagine 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. Nel diagramma si noterà che è possibile interpretare la cardinalità, rappresentata dagli indicatori **1** e *****.

    *La direzione del filtro è rappresentata dalla punta della freccia. Una linea continua rappresenta una relazione attiva, mentre una linea tratteggiata rappresenta una relazione inattiva.*

22. Passare il puntatore del mouse sulla relazione per evidenziare le colonne correlate.

    *Esiste un modo più semplice per creare una relazione. Nel diagramma del modello è possibile trascinare e rilasciare le colonne per creare una nuova relazione.*

23. Per creare una nuova relazione usando una tecnica diversa, dalla tabella **Reseller** trascinare la colonna **ResellerKey** alla colonna **ResellerKey** della tabella **Sales**.

    ![Immagine 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

    *Suggerimento: a volte non si riesce a trascinare una colonna. In questa situazione, selezionare una colonna diversa, quindi selezionare la colonna da trascinare e riprovare. Verificare che la nuova relazione aggiunta sia visibile nel diagramma.*

24. Usare la nuova tecnica per creare le due relazioni tra modelli seguenti:

    - Da **Region \| SalesTerritoryKey** a **Sales \| SalesTerritoryKey**

    - Da **Salesperson \| EmployeeKey** a **Sales \| EmployeeKey**

25. Nel diagramma disporre le tabelle in modo che la tabella **Sales** sia posizionata al centro del diagramma e che le tabelle correlate siano disposte attorno ad essa. Posizionare le tabelle disconnesse a lato.

    ![Immagine 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)


26. Salvare il file di Power BI Desktop.

## <a name="exercise-2-configure-tables"></a>**Esercizio 2: Configurare le tabelle**

In questo esercizio verrà configurata ogni tabella creando gerarchie e nascondendo, formattando e categorizzando le colonne.

### <a name="task-1-configure-the-product-table"></a>**Attività 1: Configurare la tabella Product**

In questa attività verrà configurata la tabella **Product**.

1. Nella visualizzazione Modello, se necessario, espandere la tabella **Product** nel riquadro **Campi** per visualizzare tutti i campi.

2. Per creare una gerarchia, nel riquadro **Campi** fare clic con il pulsante destro del mouse sulla colonna **Category** e quindi scegliere **Crea gerarchia**.

    ![Immagine 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. Nel riquadro **Proprietà** (a sinistra del riquadro **Campi**), nella casella **Nome** sostituire il testo con **Prodotti**.

    ![Immagine 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. Per aggiungere il secondo livello alla gerarchia, nel riquadro **Proprietà**, nell'elenco a discesa **Gerarchia** selezionare **Subcategory** (potrebbe essere necessario scorrere verso il basso all'interno del riquadro).

5. Per aggiungere il terzo livello alla gerarchia, nell'elenco a discesa **Gerarchia** selezionare **Product**.

6. Per completare la progettazione della gerarchia, fare clic su **Applica modifiche al livello**.

    ![Immagine 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

    *Suggerimento: non dimenticare di fare clic su **Applica modifiche al livello**. È un errore comune dimenticarsi di questo passaggio.*

7. Nel riquadro **Campi** osservare la gerarchia di **Products**.

    ![Immagine 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. Per visualizzare i livelli della gerarchia, espandere la gerarchia di **Products**.

    ![Immagine 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. Per organizzare le colonne in una cartella di visualizzazione, nel riquadro **Campi** selezionare prima di tutto la colonna **Background Color Format**.

10. Tenendo premuto il tasto **CTRL** selezionare la colonna **Font Color Format**.

11. Nel riquadro **Proprietà**, nella casella **Cartella di visualizzazione**, immettere **Formatting**.

    ![Immagine 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. Nel riquadro **Campi** si noti che le due colonne si trovano ora all'interno di una cartella.

    ![Immagine 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

    *Le cartelle di visualizzazione sono un ottimo modo per fare ordine tra le tabelle, in particolare quelle che contengono molti campi.*

### <a name="task-2-configure-the-region-table"></a>**Attività 2: Configurare la tabella Region**

In questa attività verrà configurata la tabella **Region**.

1. Nella tabella **Region** creare una gerarchia denominata **Regions** con i tre livelli seguenti:

    - Group

    - Country

    - Region

    ![Immagine 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. Selezionare la colonna **Country** (non il livello della gerarchia **Country**).

3. Nel riquadro **Proprietà** espandere la sezione **Avanzate** nella parte inferiore del riquadro e quindi nell'elenco a discesa **Categoria dati** selezionare **Country/Region**.

    ![Immagine 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

    *La categorizzazione dei dati può fornire suggerimenti per la progettazione dei report. In questo caso, la classificazione della colonna come paese o area geografica fornisce informazioni più accurate a Power BI durante il rendering di una visualizzazione mappa.*

### <a name="task-3-configure-the-reseller-table"></a>**Attività 3: Configurare la tabella Reseller**

In questa attività verrà configurata la tabella **Reseller**.

1. Nella tabella **Reseller** creare una gerarchia denominata **Resellers** con i due livelli seguenti:

    - Business Type

    - Reseller

    ![Immagine 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. Creare una seconda gerarchia denominata **Geography** con i quattro livelli seguenti:

    - Country-Region

    - State-Province

    - City

    - Reseller

    ![Immagine 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. Impostare la **Categoria dati** per le colonne **Country-Region**, **State-Province** e **City** (non il livello di gerarchia) su **Paese**, **Stato o provincia** e **Città** rispettivamente. 

### <a name="task-4-configure-the-sales-table"></a>**Attività 4: Configurare la tabella Sales**

In questa attività verrà configurata la tabella **Sales**.

1. Nella tabella **Sales** selezionare la colonna **Cost**.

2. Nel riquadro **Proprietà** nella casella **Descrizione** immettere: **Based on standard cost**

    ![Immagine 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

    *Le descrizioni possono essere applicate a tabelle, colonne, gerarchie o misure. Nel riquadro **Campi** il testo della descrizione viene visualizzato in una descrizione comando quando l'autore del report passa il cursore sul campo.*

3. Selezionare la colonna **Quantity**.

4. Nel riquadro **Proprietà**, nella sezione **Formattazione**, impostare l'interruttore per la proprietà **Separatore delle migliaia** su **Sì**.

    ![Immagine 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. Selezionare la colonna **Unit Price**.

6. Nel riquadro **Proprietà**, nella sezione **Formattazione**, impostare la proprietà **Posizioni decimali** su **2**.

7. Nel gruppo **Avanzate** (potrebbe essere necessario scorrere verso il basso per individuarlo), nell'elenco a discesa **Riepiloga per** selezionare **Media**.

    ![Immagine 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

    *Per impostazione predefinita, le colonne numeriche verranno riepilogate sommandone i valori. Questo comportamento predefinito non è adatto per una colonna come **Unit Price**, che rappresenta una tariffa. L'impostazione del riepilogo predefinito su Media consentirà di ottenere un risultato significativo.*

### <a name="task-5-bulk-update-properties"></a>**Attività 5: Aggiornamento delle proprietà in blocco**

In questa attività verranno aggiornate più colonne con singoli aggiornamenti in blocco. Questo approccio verrà usato per nascondere le colonne e formattare i valori delle colonne.

1. Nel riquadro **Campi** selezionare la colonna **Product \| ProductKey**.

2. Tenendo premuto **CTRL** selezionare le 13 colonne seguenti (in più tabelle):

    - Region \| SalesTerritoryKey

    - Reseller \| ResellerKey

    - Sales \| EmployeeKey
    
    - Sales \| ProductKey

    - Sales \| ResellerKey

    - Sales \| SalesOrderNumber

    - Sales \| SalesTerritoryKey

    - Salesperson \| EmployeeID

    - Salesperson \| EmployeeKey

    - Salesperson \| UPN

    - SalespersonRegion \| EmployeeKey

    - SalespersonRegion \| SalesTerritoryKey

    - Targets \| EmployeeID

3. Nel riquadro **Proprietà** impostare l'interruttore della proprietà **È nascosto** su **Sì**.

    ![Immagine 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

    *Le colonne sono state nascoste perché vengono usate dalle relazioni o verranno usate nella configurazione della sicurezza a livello di riga o nella logica di calcolo.*

    *Nel lab **Creare calcoli DAX in Power BI Desktop - Parte 1** si userà **SalesOrderNumber** in un calcolo.*

4. Selezionare le tre colonne seguenti:

    - Product \| Standard Cost

    - Sales \| Cost

    - Sales \| Sales

5. Nel riquadro **Proprietà**, nella sezione **Formattazione**, impostare l'interruttore per la proprietà **Posizioni decimali** su **0** (zero).

    ![Immagine 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## <a name="exercise-3-review-the-model-interface"></a>**Esercizio 3: Esaminare l'interfaccia del modello**

In questo esercizio si passerà alla visualizzazione Report per esaminare l'interfaccia del modello.

### <a name="task-1-review-the-model-interface"></a>**Attività 1: Esaminare l'interfaccia del modello**

In questa attività si passerà alla visualizzazione Report per esaminare l'interfaccia del modello.

1. Passare alla visualizzazione Report.

2. Nel riquadro **Campi** notare quanto segue:

    - Le colonne, le gerarchie e i relativi livelli sono campi che possono essere usati per configurare gli oggetti visivi dei report

    - Sono visibili solo i campi rilevanti per la creazione di report

    - La tabella **SalespersonRegion** non è visibile perché tutti i relativi campi sono nascosti

    - I campi spaziali nelle tabelle **Region** e **Reseller** sono contrassegnati dall'icona di dati spaziali

    - I campi contrassegnati dal simbolo sigma (Ʃ) verranno riepilogati per impostazione predefinita

    - Viene visualizzata una descrizione comando quando si passa il puntatore del mouse sul campo **Sales \| Cost**

3. Espandere il campo **Sales \| OrderDate** notando che viene visualizzata una gerarchia di date.

    ![Immagine 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

    *Il campo **Targets \| TargetMonth** rappresenta una gerarchia simile. Queste gerarchie non sono state create dall'utente, ma vengono create automaticamente. È però presente un problema. L'anno finanziario di Adventure Works inizia il 1° luglio ogni anno. Tuttavia, in queste gerarchie di date create automaticamente, l'anno della gerarchia inizia il 1° gennaio ogni anno.*

    *Si vedrà ora come disattivare questo comportamento automatico. Nel lab **Creare calcoli DAX in Power BI Desktop - Parte 1**, si userà DAX per creare una tabella di date e configurarla per definire il calendario di Adventure Works.*

4. Per disattivare la data/ora automatica, fare clic sulla scheda **File** della barra multifunzione per aprire la visualizzazione backstage.

5. A sinistra selezionare **Opzioni e impostazioni** e quindi **Opzioni**.

    ![Immagine 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. Nella finestra **Opzioni**, a sinistra, nel gruppo **File corrente** selezionare **Caricamento dati**.

    ![Immagine 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. Nella sezione **Funzionalità di Business Intelligence per le gerarchie temporali** deselezionare **Data/ora automatica**.

    ![Immagine 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. Fare clic su **OK**.

    ![Figura 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. Nel riquadro **Campi** notare che le gerarchie di date non sono più disponibili.

    ![Immagine 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)


## <a name="exercise-4-create-quick-measures"></a>**Esercizio 4: Creare misure rapide**

In questo esercizio si creeranno due misure rapide.

### <a name="task-1-create-quick-measures"></a>**Attività 1: Creare misure rapide**

In questa attività verranno create due misure rapide per calcolare il profitto e il margine di profitto.

1. Nel riquadro **Campi** fare clic con il pulsante destro del mouse sulla tabella **Sales** e quindi scegliere **Nuova misura rapida**.

    ![Immagine 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

2. Nella finestra **Misure rapide**, nell'elenco a discesa **Calcolo**, dall'interno del gruppo **Operazioni matematiche** selezionare **Sottrazione**.

    ![Immagine 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

3. Nel riquadro **Campi** della finestra **Misure rapide** espandere la tabella **Sales**.

4. Trascinare il campo **Sales** nella casella **Valore di base**.

5. Trascinare il campo **Cost** nella casella **Valore da sottrarre**.

    ![Immagine 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

6. Fare clic su **OK**.

    ![Immagine 369](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image49.png)

    *Una misura rapida crea automaticamente la formula per il calcolo. Sono semplici e veloci da creare per calcoli semplici e comuni. Si creeranno misure senza usare questo strumento nel lab **Creare calcoli DAX in Power BI Desktop - Parte 1**.*

7. Nel riquadro **Campi**, all'interno della tabella **Sales**, notare la nuova misura.

    ![Immagine 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

    *Le misure sono contrassegnate dall'icona a forma di calcolatrice.*

8. Per rinominare la misura, fare clic con il pulsante destro del mouse su di essa e quindi scegliere **Rinomina**.

    ![Immagine 371](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image51.png)

    *Suggerimento: per rinominare un campo, è anche possibile fare doppio clic su di esso oppure selezionarlo e premere **F2**.*

9. Rinominare la misura in **Profit** e quindi premere **INVIO**.

10. Nella tabella **Sales** aggiungere una seconda misura rapida in base ai requisiti seguenti:

    - Usare l'operazione matematica **Divisione**

    - Impostare **Numeratore** sul campo **Sales \| Profit**

    - Impostare **Denominatore** sul campo **Sales \| Sales**

    - Rinominare la misura **Profit Margin**

    ![Immagine 372](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image52.png)

    ![Immagine 373](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image53.png)

11. Verificare che sia selezionata la misura **Profit Margin**, quindi sulla barra multifunzione contestuale **Strumenti misura** impostare il formato su **Percentuale**, con due posizioni decimali.

    ![Immagine 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

12. Per testare le due misure, selezionare prima l'oggetto visivo Tabella nella pagina del report.

13. Nel riquadro **Campi** selezionare le due misure.

    ![Immagine 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

14. Fare clic e trascinare la guida a destra per allargare l'oggetto visivo Tabella.

    ![Immagine 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

15. Verificare che le misure producano un risultato ragionevole formattato correttamente.

    ![Immagine 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### <a name="task-2-create-a-many-to-many-relationship"></a>**Attività 2: Creare una relazione molti-a-molti**

In questa attività verrà creata una relazione molti-a-molti tra la tabella **Salesperson** e la tabella **Sales**.

1. In Power BI Desktop, nella visualizzazione Report, nel riquadro **Campi** selezionare i due campi seguenti per creare un oggetto visivo Tabella:

    - Salesperson \| Salesperson

    - Sales \| Sales

    *Nei lab viene usata una notazione abbreviata per fare riferimento a un campo, simile al seguente: **Salesperson \| Salesperson** . In questo esempio, **Salesperson** è il nome della tabella e **Salesperson** è il nome del campo.*

    ![Immagine 1](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image9.png)

    *Nella tabella vengono visualizzate le vendite effettuate da ogni venditore. Tuttavia, esiste un'altra relazione tra i venditori e le vendite. Alcuni venditori appartengono a una, due o più aree di vendita. Inoltre, le aree di vendita possono avere più venditori assegnati.*

    *Dal punto di vista della gestione delle prestazioni, le vendite di un venditore (basate sulle rispettive aree assegnate) devono essere analizzate e confrontate con gli obiettivi di vendita. Nell'esercizio successivo verranno create le relazioni per supportare questa analisi.*

2. Si noti che Michael Blythe ha realizzato vendite per quasi 9 milioni di dollari.

3. Passare alla vista Modello.

    ![Immagine 10](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image10.png)

4. Trascinare la tabella **SalespersonRegion** per posizionarla tra le tabelle **Region** e **Salesperson**.

5. Usare la tecnica di trascinamento della selezione per creare le due relazioni tra modelli seguenti:

    - Da **Salesperson \| EmployeeKey** a **SalespersonRegion \| EmployeeKey**

    - Da **Region \| SalesTerritoryKey** a **SalespersonRegion \| SalesTerritoryKey**

    *La tabella **SalespersonRegion** può essere considerata una tabella ponte.*

6. Passare alla visualizzazione Report e notare che l'oggetto visivo non è stato aggiornato. Il risultato delle vendite per Michael Blythe non è cambiato.

7. Tornare alla visualizzazione Modello e quindi seguire le direzioni del filtro delle relazioni (punta della freccia) dalla tabella **Salesperson**.

    *Tenere presente che la tabella **Salesperson** filtra la tabella **Sales**. Filtra anche la tabella **SalespersonRegion**, ma non continua la propagazione dei filtri alla tabella **Region** (la freccia punta nella direzione sbagliata).*

    ![Immagine 380](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image11.png)

8. Per modificare la relazione tra le tabelle **Region** e **SalespersonRegion**, fare doppio clic sulla relazione.

9. Nella finestra **Modifica relazione**, nell'elenco a discesa **Direzione filtro incrociato** selezionare **Entrambe**.

10. Selezionare la casella di controllo **Applica filtro di sicurezza in entrambe le direzioni**.

    ![Immagine 381](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image12.png)

11. Fare clic su **OK**.

    ![Immagine 335](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image13.png)

12. Si noti che la relazione ha una freccia con due punte.

    ![Immagine 382](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image14.png)

13. Passare alla visualizzazione Report e notare che i valori delle vendite non sono ancora cambiati.

    *Il problema è ora correlato al fatto che esistono due possibili percorsi di propagazione dei filtri tra le tabelle **Salesperson** e **Sales**. Questa ambiguità viene risolta internamente, in base a una valutazione "minor numero di tabelle". Per essere chiari, è sconsigliabile progettare modelli con questo tipo di ambiguità. Il problema verrà in parte risolto più avanti in questo lab ed entro la fine del lab **Creare calcoli DAX in Power BI Desktop - Parte 1**.*

14. Passare alla vista Modello.

15. Per forzare la propagazione dei filtri tramite la tabella ponte, modificare (fare doppio clic) la relazione tra le tabelle **Salesperson** e **Sales**.

16. Nella finestra **Modifica relazione** deselezionare la casella di controllo **Imposta come relazione attiva**.

    ![Immagine 383](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image15.png)

17. Fare clic su **OK**.

    ![Immagine 5696](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image16.png)

    *La propagazione del filtro seguirà ora l'unico percorso attivo.*

18. Nel diagramma si noti che la relazione inattiva è rappresentata da una linea tratteggiata.

    ![Immagine 5697](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image17.png)

19. Passare alla visualizzazione Report e notare che le vendite di Michael Blythe sono ora pari a circa 22 milioni di dollari.

    ![Immagine 5698](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image18.png)

20. Si noti anche che le vendite per ogni venditore, se sommate, sarebbero maggiori del totale della tabella.

    *Questa è un'osservazione comune che riguarda le relazioni molti-a-molti, a causa del conteggio doppio, triplo e così via dei risultati delle vendite internazionali. Si consideri Brian Welcker, il secondo venditore elencato. L'importo delle vendite da lui realizzate è uguale all'importo totale delle vendite. Si tratta del risultato corretto semplicemente perché è il responsabile delle vendite e quindi le sue vendite vengono misurate in base alle vendite di tutte le aree.*

    *Mentre la relazione molti-a-molti a questo punto funziona, ora non è possibile analizzare le vendite effettuate da un venditore (perché la relazione è inattiva). Sarà possibile riattivare la relazione quando si introdurrà una tabella calcolata che consentirà di analizzare le vendite effettuate nelle aree assegnate al venditore (per l'analisi delle prestazioni) nel lab **Creare calcoli DAX in Power BI Desktop - Parte 1**.*

21. Passare alla visualizzazione Modello e quindi nel diagramma selezionare la tabella **Salesperson**.

22. Nel riquadro **Proprietà**, nella casella **Nome** sostituire il testo con **Salesperson (prestazioni)**.

    *La tabella rinominata ora riflette lo scopo: viene usata per segnalare e analizzare le prestazioni dei venditori in base alle vendite delle aree di vendita assegnate.*

### <a name="task-3-relate-the-targets-table"></a>**Attività 3: Correlare la tabella Targets**

In questa attività verrà creata una relazione con la tabella **Targets**

1. Creare una relazione dalla colonna **Salesperson (Performance) \| EmployeeID** alla colonna **Targets \| EmployeeID**.

2. Nella visualizzazione Report aggiungere il campo **Targets \| Target** all'oggetto visivo tabella.

3. Ridimensionare l'oggetto visivo tabella in modo che tutte le colonne siano visibili.

    ![Immagine 5699](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image19.png)

    *È ora possibile visualizzare le vendite e i target, ma prestare attenzione per due motivi. In primo luogo, non è presente alcun filtro per un periodo di tempo, quindi i target includono anche importi target futuri. In secondo luogo, i target non sono additivi, quindi il totale non deve essere visualizzato. Può essere disabilitato formattando l'oggetto visivo o rimosso usando la logica di calcolo. Si seguirà il secondo approccio nel lab **Creare calcoli DAX in Power BI Desktop - Parte 2** creando una misura di destinazione che restituisce BLANK quando viene filtrato più di un venditore.*

### <a name="task-4-finish-up"></a>**Attività 4: Completare il lab**

In questa attività si completerà il lab.

1. Salvare il file di Power BI Desktop.

2. Se viene richiesto di applicare le query, fare clic su **Applica più tardi**.

3. Se si intende iniziare il lab successivo, lasciare aperto Power BI Desktop.
