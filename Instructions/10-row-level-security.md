---
lab:
  title: Applicare la sicurezza a livello di riga
  module: Module 12 - Row-Level Security
ms.openlocfilehash: 6ccc19e9835dca06ec613e386c82fb0270a28ed5
ms.sourcegitcommit: 51f448b208842f1333cb683b7775618edb41c126
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2022
ms.locfileid: "141580174"
---
# <a name="enforce-row-level-security"></a>**Applicare la sicurezza a livello di riga**

**Il tempo stimato per il completamento del lab è di 45 minuti**

In questo lab verrà creata una relazione molti-a-molti tra la tabella **Salesperson** e la tabella **Sales**. Verrà anche applicata la sicurezza a livello di riga per garantire che un venditore possa analizzare solo i dati di vendita per le rispettive aree assegnate.

Contenuto del lab:

- Configurare relazioni molti-a-molti

- Applicare la sicurezza a livello di riga

### <a name="lab-story"></a>**Presentazione del lab**

Questo lab fa parte di una serie che comprende molti lab progettati come attività completa, dalla preparazione dei dati alla pubblicazione come report e dashboard. È possibile completare i lab nell'ordine desiderato. Se tuttavia si intende seguire più lab, per i primi 10 è consigliabile procedere in questo ordine:

1. Preparare i dati in Power BI Desktop

2. Caricare i dati in Power BI Desktop

3. Modellare i dati in Power BI Desktop

5. Creare calcoli DAX in Power BI Desktop - Parte 1

6. Creare calcoli DAX in Power BI Desktop - Parte 2

7. Progettare un report in Power BI Desktop - Parte 1

8. Progettare un report in Power BI Desktop - Parte 2

9. Creare un dashboard di Power BI

10. Eseguire l'analisi dei dati in Power BI Desktop

11. **Applicare la sicurezza a livello di riga**

## <a name="exercise-1-enforce-row-level-security"></a>**Esercizio 1: Applicare la sicurezza a livello di riga**

In questo esercizio si applicherà la sicurezza a livello di riga per assicurarsi che un venditore possa visualizzare solo le vendite realizzate nelle proprie aree.

### <a name="task-1-get-started"></a>**Attività 1: Operazioni preliminari**

In questa attività si configurerà l'ambiente per il lab.

*Importante: se si sta continuando dal lab precedente (e il lab è stato completato correttamente), non completare questa attività, ma passare a quella successiva.*

1. Per aprire Power BI Desktop, sulla barra delle applicazioni fare clic sul collegamento Microsoft Power BI Desktop.

    ![Immagine 8](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image1.png)

1. Per chiudere la finestra introduttiva, fare clic su **X** nella parte superiore sinistra della finestra.

    ![Immagine 7](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image2.png)

1. Per aprire il file di avvio di Power BI Desktop, selezionare la scheda della barra multifunzione **File** per aprire la visualizzazione Backstage.

1. Selezionare **Apri report**.

    ![Immagine 6](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image3.png)

1. Fare clic su **Esplora report**.

    ![Figura 5](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image4.png)

1. Nella finestra **Apri** passare alla cartella **D:\PL300\Labs\10-row-level-security\Starter**.

1. Selezionare il file **Sales Analysis**.

1. Fare clic su **Apri**.

    ![Immagine 4](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image5.png)

1. Chiudere eventuali finestre aperte di carattere informativo.

1. Per creare una copia del file, fare clic sulla scheda della barra multifunzione **File** per aprire la visualizzazione Backstage.

1. Selezionare **Salva con nome**.

    ![Immagine 3](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image6.png)

1. Se viene richiesto di applicare le modifiche, fare clic su **Applica**.

    ![Immagine 15](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image7.png)

1. Nella finestra **Salva con nome** passare alla cartella **D:\PL300\MySolution**.

1. Fare clic su **Save** (Salva).

    ![Figura 2](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image8.png)

### <a name="task-2-enforce-row-level-security"></a>**Attività 2: Applicare la sicurezza a livello di riga**

In questa attività si applicherà la sicurezza a livello di riga per assicurarsi che un venditore possa visualizzare solo le vendite realizzate nelle proprie aree.

1. Passa alla vista Dati.

    ![Immagine 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

2. Nel riquadro **Campi** selezionare la tabella **Salesperson (Performance)**.

3. Esaminare i dati. Si noti che il valore UPN di Michael Blythe (EmployeeKey 281) è: **michael-blythe@adventureworks.com**

    *Si ricordi che Michael Blythe è assegnato a tre aree di vendita: US Northeast, US Central e US Southeast.*

4. Passare alla vista Report.

5. Nella scheda della barra multifunzione **Modellazione**, nel gruppo **Sicurezza** fare clic su **Gestisci ruoli**.

    ![Immagine 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

6. Nella finestra **Gestisci ruoli** fare clic su **Crea**.

    ![Immagine 5702](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image22.png)

7. Nella casella sostituire il testo selezionato con il nome del ruolo: **Salespeople** e quindi premere **INVIO**.

    ![Immagine 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

8. Per assegnare un filtro per la tabella **Salesperson (Performance)** , fare clic sul carattere puntini di sospensione (...) e quindi selezionare **Aggiungi filtro \| [UPN]** .

    ![Immagine 5704](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image24.png)

9. Nella casella **Espressione DAX filtro tabella** modificare l'espressione sostituendo **"Value"** con **USERPRINCIPALNAME()** .

    ![Immagine 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

    *USERPRINCIPALNAME() è una funzione DAX (Data Analysis Expressions) che restituisce il nome dell'utente autenticato. La tabella **Salesperson (Performance)** verrà quindi filtrata in base al nome dell'entità utente (UPN) dell'utente che esegue una query sul modello.*

10. Fare clic su **Save** (Salva).

    ![Immagine 5706](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image26.png)

11. Per testare il ruolo di sicurezza, nella scheda della barra multifunzione **Modellazione**, nel gruppo **Sicurezza** fare clic su **Visualizza come**.

    ![Immagine 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

12. Nella finestra **Visualizza come ruoli** selezionare l'elemento **Altro utente** e quindi nella casella corrispondente immettere: **michael-blythe@adventureworks.com**

13. Selezionare il ruolo **Salespeople**.

    ![Immagine 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

    *Questa configurazione comporta l'uso del ruolo **Salespeople** e la rappresentazione dell'utente con il nome di Michael Blythe.*

14. Fare clic su **OK**.

    ![Immagine 5710](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image29.png)

15. Si noti il banner giallo sopra la pagina del report, che descrive il contesto di sicurezza del test.

    ![Immagine 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

16. Nell'oggetto visivo tabella si noti che è elencato solo il venditore **Michael Blythe**.

    ![Immagine 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

17. Per arrestare il test, fare clic su **Arresta visualizzazione** sul lato destro del banner giallo.

    ![Picture 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

    *Dopo la pubblicazione del file di Power BI Desktop nel servizio Power BI, sarà necessario completare un'attività per eseguire il mapping delle entità di sicurezza al ruolo **Salespeople**. Tale attività non verrà eseguita in questo lab.*

18. Per eliminare il ruolo, nella scheda della barra multifunzione **Modellazione**, nel gruppo **Sicurezza** selezionare **Gestisci ruoli**.

    ![Immagine 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

19. Nella finestra **Gestisci ruoli** fare clic su **Elimina**.

    ![Figura 17](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image34.png)

20. Quando viene richiesto di confermare l'eliminazione, fare clic su **Sì, elimina**.

21. Fare clic su **Save** (Salva).

    ![Figura 18](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image35.png)

### <a name="task-3-finish-up"></a>**Attività 3: Completare il lab**

In questa attività si completerà il lab.

1. Salvare il file di Power BI Desktop.
