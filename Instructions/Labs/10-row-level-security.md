---
lab:
  title: Applicare la sicurezza a livello di riga
  module: Enforce Row-Level Security
---

# Applicare la sicurezza a livello di riga

## Presentazione del lab

In questo lab verrà applicata la sicurezza a livello di riga per garantire che un venditore possa analizzare solo i dati delle vendite per le aree assegnate.

Contenuto del lab:

- Applicare la sicurezza a livello di riga
- Scegliere tra metodi dinamici e statici

**Questo lab dovrebbe richiedere circa 20 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare la cartella ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/10-row-level-security/10-row-level-security.zip`

Estrarre la cartella nella **cartella C:\Users\Student\Downloads\10-row-level-security** .

Aprire il **file 10-Starter-Sales Analysis.pbix** .

> ***Nota**: è possibile ignorare l'accesso selezionando **Annulla**. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche.*

## Applicare la sicurezza a livello di riga

In questa attività verrà applicata la sicurezza a livello di riga per garantire che un venditore possa visualizzare solo le vendite effettuate nelle aree assegnate.

1. Passare alla visualizzazione Tabella.

   ![Immagine 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. **Nel riquadro Dati** selezionare la **tabella Salesperson (Performance).**

1. Esaminare i dati. Si noti che il valore UPN di Michael Blythe (EmployeeKey 281) è: **`michael-blythe@adventureworks.com`**
    
    > *È possibile ricordare che Michael Blythe è assegnato a tre aree di vendita: Stati Uniti nord-orientali, Stati Uniti centrali e Stati Uniti sud-orientali.*

1. Nella scheda Home** della **barra multifunzione selezionare **Gestisci ruoli** nel **gruppo Sicurezza**.

    ![Immagine 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. Nella sezione Ruoli** della ****finestra Gestisci ruoli** di sicurezza selezionare **Nuovo**.

1. Nella casella sostituire il testo selezionato con il nome del ruolo Salespeople **** e quindi premere **INVIO**.

   ![Immagine 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. Per assegnare un filtro, selezionare la **tabella Salesperson (Performance)** e quindi selezionare **Passa all'editor** DAX nella **sezione Filtra dati** .

   ![Screenshot 2024-04-18 144345](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/1308d47f-2cca-4f88-9237-b02b66b4cf1e)

1. Nella casella editor DAX immettere l'espressione seguente:

    ```DAX
    [UPN] = USERPRINCIPALNAME()
    ```

   ![Immagine 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

    > *USERPRINCIPALNAME() è una funzione DAX (Data Analysis Expressions) che restituisce il nome dell'utente autenticato. Significa che la **tabella Salesperson (Performance)** filtra in base al nome dell'entità utente (UPN) dell'utente che esegue una query sul modello.*

1. Selezionare **Salva** e **Chiudi**.

1. Per testare il ruolo di sicurezza, nella scheda Home della **barra multifunzione selezionare **Visualizza come** all'interno del **gruppo Sicurezza**.**

   ![Immagine 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

1. Nella finestra **Visualizza come ruoli** selezionare l'elemento **Altro utente** e quindi nella casella corrispondente immettere: **`michael-blythe@adventureworks.com`**

1. Controllare il **ruolo Venditori** e quindi **OK**.
    
    > *Questa configurazione comporta l'uso del ruolo **Salespeople** e la rappresentazione dell'utente con il nome di Michael Blythe.*

   ![Immagine 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

1. Si noti il banner giallo sopra la pagina del report, che descrive il contesto di sicurezza del test.

   ![Immagine 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

1. Nell'oggetto visivo tabella si noti che è elencato solo il venditore **Michael Blythe**.

   ![Immagine 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

1. Per arrestare il test, selezionare **Arresta visualizzazione** sul lato destro del banner giallo.

   ![Picture 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

1. Per eliminare il **ruolo Venditori**, nella scheda Home** della **barra multifunzione selezionare **Gestisci ruoli** all'interno del **gruppo Sicurezza**.

   ![Immagine 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. **Nella finestra Gestisci ruoli** di sicurezza selezionare i puntini di sospensione (...) nel **ruolo Venditori** e selezionare **Elimina**. Quando viene richiesto di confermare l'eliminazione, selezionare **Sì, Elimina**.

   ![Screenshot 2024-04-18 145556](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/deeb4eac-b639-433d-a9d4-29c8e127008e)

*Nota: quando il file di Power BI Desktop viene pubblicato nel servizio Power BI, è necessario completare un'attività post-pubblicazione per eseguire il mapping delle entità di sicurezza al **ruolo Venditori**. Questa operazione non verrà eseguita in questo lab.*

## Lab completato
