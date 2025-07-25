---
lab:
  title: (Facoltativo) Creare dashboard in Power BI
  module: Create dashboards in Power BI
---

# Creare dashboard in Power BI

## Presentazione del lab

In questo lab si creerà il **dashboard Sales Monitoring** nel servizio Power BI usando un report esistente.

Contenuto del lab:

- Aggiungere oggetti visivi a un dashboard.
- Usare Q&A per creare riquadri del dashboard.

**Questo lab dovrebbe richiedere circa 30 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/12-create-power-bi-dashboard/12-create-dashboard.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\12-create-dashboard** .

> _**Nota**: per pubblicare il report sarà necessaria almeno una **licenza gratuita** di Power BI. Aprire il browser Microsoft Edge, quindi accedere all'indirizzo `https://app.powerbi.com`. Quando viene chiesto di risolvere un puzzle o di avviare una versione di valutazione gratuita di Fabric, è possibile ignorare questo e chiudere il browser.

## **Pubblicare il report**

In questa attività si configurerà l'ambiente per il lab creando un modello semantico.

1. Nella finestra del browser Microsoft Edge, nella servizio Power BI, passare a **Area di lavoro** personale.

1. Selezionare **Importa > Report o Report impaginato > da questo computer**.

1. Passare alla **cartella C:\Users\Student\Downloads\12-create-dashboard** .

1. Selezionare il **file 12-Starter-Sales Analysis.pbix** e quindi selezionare **Apri**.

    > *Se viene richiesto di sostituire il modello semantico, selezionare **Sostituisci**.*

## **Creare un dashboard**

In questa attività si creerà il **dashboard Di monitoraggio** vendite. Si aggiungerà un oggetto visivo dal report e si aggiungerà un riquadro in base a un URI di dati dell'immagine e si userà Domande e risposte per creare un riquadro.

1. Nella servizio Power BI aprire il **report 12-Starter-Sales Analysis**.

1. Nella pagina **Overview** impostare il filtro dei dati **Year** su **FY2020**.

    ![Immagine 4](Linked_image_Files/12-create-power-bi-dashboard_image17.png)

1. Impostare il filtro dei dati **Region** su **Select All**.

    > *Gli oggetti visivi aggiunti vengono impostati con il contesto di filtro al momento del pin. Se l'oggetto visivo sottostante cambia, è necessario aggiornare anche il riquadro del dashboard. Per i filtri basati sul tempo, è consigliabile usare un filtro dei dati di data relativo (o Q&A usando una domanda relativa basata sul tempo).*

1. Per creare un dashboard e aggiungere un oggetto visivo, passare il cursore sull'oggetto **visivo Sales and Profit Margin by Month** (colonna/riga) e selezionare la puntina da disegno.

    ![Immagine 43](Linked_image_Files/12-create-power-bi-dashboard_image18.png)

1. **Nella finestra Aggiungi al dashboard** immettere **Sales Monitoring** nella **casella Nome** dashboard e quindi selezionare **Aggiungi**.

    ![Immagine 3](Linked_image_Files/12-create-power-bi-dashboard_image19.png)

1. Aprire **Area di lavoro** personale e aprire il **dashboard Di monitoraggio** vendite.

1. Si noti che il dashboard ha un solo riquadro.

    ![Immagine 45](Linked_image_Files/12-create-power-bi-dashboard_image22.png)

1. Per aggiungere un riquadro basato su una domanda, nella parte superiore sinistra del dashboard selezionare **Porre una domanda sui dati**. 

    *È possibile usare la funzionalità Q&A per porre una domanda e Power BI risponderà con un oggetto visivo.*

    ![Immagine 7](Linked_image_Files/12-create-power-bi-dashboard_image23.png)

1. Selezionare una delle domande suggerite sotto la casella domande e risposte ed esaminare la risposta.

1. Rimuovere tutto il testo dalla casella Q&A e immettere quanto segue: **Sales YTD**

1. Si noti la risposta **(Blank)**.

    > *È possibile ricordare di aver aggiunto la **misura Sales YTD** nel **lab Creare calcoli DAX avanzati in Power BI Desktop** . Questa misura è un'espressione di Business Intelligence per le gerarchie temporali e quindi richiede un filtro sulla **tabella Date** per produrre un risultato.*

    ![Immagine 14](Linked_image_Files/12-create-power-bi-dashboard_image25.png)

1. Estendere la domanda con: **in year FY2020**.

1. Si noti che la risposta è ora **$33M**.

    ![Immagine 13](Linked_image_Files/12-create-power-bi-dashboard_image27.png)

1. Per aggiungere la risposta al dashboard, nell'angolo superiore destro selezionare **Aggiungi oggetto visivo**.

    ![Immagine 15](Linked_image_Files/12-create-power-bi-dashboard_image28.png)

1. Quando viene richiesto di aggiungere il riquadro al **dashboard Di monitoraggio** vendite, selezionare **Aggiungi**.

1. Per tornare al dashboard, nell'angolo superiore sinistro selezionare **Esci da Q&amp;A**.

1. Per aggiungere il logo aziendale, nella barra dei menu selezionare **Modifica** e quindi aggiungi **riquadro**.
    
    > *L'uso di questa tecnica per aggiungere un riquadro del dashboard consente di migliorare il dashboard con contenuti multimediali, inclusi contenuti Web, immagini, caselle di testo formattate in modo avanzato e video (usando i collegamenti YouTube o Vimeo).*

1. **Nel riquadro Aggiungi riquadro riquadro** (situato a destra), selezionare il **riquadro Immagine** e quindi **Avanti**.

1.Passare alla **cartella C:\Users\Student\Downloads\12-create-dashboard** e aprire il **file AdventureWorksLogo_DataURL.txt** . 

2. **Nel riquadro Aggiungi riquadro** immagine, nella **casella URL** incollare l'URL dal file di testo e quindi **applica**.
    
    > *È possibile incorporare un'immagine usando il relativo URL oppure un URL di dati che incorpora il contenuto inline.*

1. Per ridimensionare il riquadro del logo, trascinare l'angolo inferiore destro e ridimensionare il riquadro in modo che diventi un'unità larga e un'unità alta.
    
    > *Le dimensioni dei riquadri sono limitate a una forma rettangolare.*

1. Organizzare i riquadri in modo che il logo venga visualizzato in alto a sinistra, con il riquadro **Sales YTD** al di sotto e il riquadro **Sales, Profit Margin** a destra.

    ![Immagine 52](Linked_image_Files/12-create-power-bi-dashboard_image35.png)

## **Modificare i dettagli del riquadro**

In questa attività verranno modificati i dettagli di due riquadri.

1. Posizionare il cursore sul riquadro **Sales YTD** e quindi nella parte superiore destra del riquadro selezionare i puntini di sospensione e selezionare **Modifica dettagli**.

    ![Immagine 50](Linked_image_Files/12-create-power-bi-dashboard_image36.png)

1. **Nel riquadro Dettagli** riquadro (situato a destra), nella **casella Sottotitolo** immettere **FY2020** e quindi selezionare **Applica**.

1. Si noti che il riquadro **Sales YTD** visualizza un sottotitolo.

    ![Figura 21](Linked_image_Files/12-create-power-bi-dashboard_image39.png)

1. Modificare i dettagli **del riquadro Vendite, Profit Margin** .

1. **Nel riquadro Dettagli** riquadro, nella **sezione Funzionalità**, selezionare **Visualizza ora ultimo aggiornamento** e quindi **Applica**.

    ![Figura 22](Linked_image_Files/12-create-power-bi-dashboard_image40.png)

1. Si noti che il riquadro descrive l'ora dell'ultimo aggiornamento effettuato durante il caricamento del modello di dati in Power BI Desktop.

*Il modello semantico verrà aggiornato nell'esercizio successivo. A seconda dei dati e dei report, è possibile eseguire un aggiornamento dati ad hoc in qualsiasi momento o impostare una pianificazione. Tuttavia, gli aggiornamenti pianificati richiedono che i gateway non siano in grado di configurare per questo lab. Da Power BI Desktop si eseguirà quindi un aggiornamento manuale dei dati e quindi si caricherà il file nell'area di lavoro.*

## **Aggiornare il modello semantico**

In questo esercizio si caricheranno prima i dati degli ordini di vendita per giugno 2020 nel database **AdventureWorksDW2020**. Si aprirà quindi il file di Power BI Desktop, si eseguirà un aggiornamento dei dati e quindi si caricherà il file nell'area di lavoro.

> ***Nota**: se non è possibile connettersi al database, è possibile usare il **file 12-Solution-Sales-Analysis.pbix** . Anziché aggiornare il database e aggiornare il modello semantico, caricare il file **della soluzione nell'area di lavoro** personale e visualizzare le modifiche a cui si fa riferimento nelle attività seguenti.*

## **Aggiornare il database del lab**

In questa attività verrà eseguito uno script di PowerShell per aggiornare i dati nel database **AdventureWorksDW2020**.

1. In Esplora file, all'interno della **cartella C:\Users\Student\Downloads\12-create-dashboard** fare clic con il pulsante destro del mouse sul **file UpdateDatabase-2-AddSales.ps1** e quindi selezionare **Esegui con PowerShell**.

    ![Immagine 28](Linked_image_Files/12-create-power-bi-dashboard_image46.png)

1. Se viene richiesto di modificare i criteri di esecuzione, premere**A**.

1. Quando viene richiesto di premere un tasto qualsiasi per chiudere, premere di nuovo **INVIO**.

*Il database **AdventureWorksDW2020** include ora gli ordini di vendita effettuati a giugno 2020.*

## **Aggiornare il file di Power BI Desktop**

In questa attività si aprirà il **file di Power BI Desktop 12-Starter-Sales Analysis** , si eseguirà un aggiornamento dei dati e quindi si caricherà il file nell'area **di lavoro Analisi vendite** .

1. Nel riquadro Dati del file di Power BI Desktop fare clic con il **pulsante destro del mouse sulla **tabella Sales** e quindi scegliere **Aggiorna dati**.**

    ![Immagine 55](Linked_image_Files/12-create-power-bi-dashboard_image47.png)

1. Al termine dell'aggiornamento, salvare il file di Power BI Desktop.

1. Per pubblicare il file nell'area di lavoro, nella scheda Home della **barra multifunzione, dall'interno del **gruppo Condividi** selezionare **Pubblica** e quindi selezionare **Seleziona** per** pubblicare.

    ![Immagine 59](Linked_image_Files/12-create-power-bi-dashboard_image48.png)

1. Quando viene richiesto di sostituire il modello semantico, selezionare **Sostituisci**.

1. Chiudere Power BI Desktop.

*Il modello semantico nel servizio Power BI include ora i dati sulle vendite di giugno 2020.*

### **Esaminare il dashboard**

In questa attività si esaminerà il dashboard per notare le vendite aggiornate.

1. Nella finestra del browser Microsoft Edge aprire servizio Power BI e quindi esaminare il **dashboard Monitoraggio** vendite in **Area di lavoro** personale.

2. **Nel riquadro Sales, Profit Margin**, in linea con il sottotitolo, si noti che i dati sono stati **Aggiornati: NOW**.

3. Si noti anche che ora è presente una colonna per **jun** 2020.

    > *Se i dati relativi a giugno 2020 non vengono visualizzati, potrebbe essere necessario premere **F5** per ricaricare il Web browser.*

    ![Immagine 33](Linked_image_Files/12-create-power-bi-dashboard_image50.png)

## Lab completato
