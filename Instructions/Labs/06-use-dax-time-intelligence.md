---
lab:
  title: Usare le funzioni di Business Intelligence per le gerarchie temporali DAX in Power BI
  module: Use DAX time intelligence functions in Power BI
---

# Usare le funzioni di Business Intelligence per le gerarchie temporali DAX in Power BI

## Presentazione del lab

In questo lab si creeranno misure con espressioni DAX che coinvolgono l'intelligenza temporale.

In questo lab si apprenderà come:

 - Usare varie funzioni di Business Intelligence per le gerarchie temporali per modificare il contesto di filtro che riguarda le date specifiche.

**Questo lab dovrebbe richiedere circa 15 minuti.**

## Operazioni preliminari

Per completare questo esercizio, aprire prima un Web browser e immettere l'URL seguente per scaricare il file ZIP:

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/06-use-dax-time-intelligence/06-time-intelligence.zip`

Estrarre il file nella **cartella C:\Users\Student\Downloads\06-time-intelligence** .

Aprire il **file 06-Starter-Sales Analysis.pbix** .

> _**Nota**: è possibile che venga visualizzata una finestra di dialogo di accesso durante il caricamento del file. Selezionare **Annulla** per chiudere la finestra di dialogo di accesso. Chiudere qualsiasi altra finestra informativa. Selezionare **Applica in seguito**, se richiesto di applicare le modifiche._

## Creare una misura YTD

In questa attività si creerà una misura da inizio anno di vendita (YTD) usando le funzioni di Business Intelligence per le gerarchie temporali.

1. Nella visualizzazione** Report di Power BI Desktop, **nella **pagina 2**, si noti l'oggetto visivo matrice che visualizza varie misure con anni e mesi raggruppati sulle righe.

2. Aggiungere una misura alla tabella, in base all'espressione `Sales` seguente e formattata in zero cifre decimali:

    ```dax
    Sales YTD =
    TOTALYTD(
        SUM(Sales[Sales]),
        'Date'[Date],
        "6-30"
    )
    ```

    > _La `TOTALYTD` funzione valuta un'espressione, in questo caso la somma della `Sales` colonna, su una determinata colonna di data. La colonna data deve appartenere a una tabella data contrassegnata come tabella data._
    >
    > _La funzione può anche accettare un terzo argomento facoltativo che rappresenta l'ultima data di un anno. L'assenza di questa data indica che il 31 dicembre è l'ultima data dell'anno. Per Adventure Works, giugno è nell'ultimo mese dell'anno e quindi viene usato "6-30"._

3. Aggiungere il `Sales` campo e la `Sales YTD` misura all'oggetto visivo matrice.

4. Si noti l'accumulo dei valori delle vendite nell'anno.

    ![Immagine 1](Linked_image_Files/06-use-dax-time-intelligence-functions_image21.png)

> _La `TOTALYTD` funzione esegue la manipolazione dei filtri, in particolare la manipolazione del filtro temporale. Ad esempio, per calcolare le vendite YTD per settembre 2017 (il terzo mese dell'anno fiscale), tutti i filtri sulla `Date` tabella vengono rimossi e sostituiti con un nuovo filtro di date che iniziano all'inizio dell'anno (1 luglio 2017) e si estendono fino all'ultima data del periodo di data nel contesto (30 settembre 2017)._
>
> _Molte [funzioni](/dax/time-intelligence-functions-dax/?azure-portal=true) di Business Intelligence per le gerarchie temporali sono disponibili in DAX per supportare le manipolazioni comuni dei filtri temporali._

## Creare una misura di crescita YoY

In questa attività si creerà una misura di crescita YoY di vendita usando una variabile.

> Le variabili consentono di semplificare la formula e sono più efficienti se si usa la logica più volte all'interno di una formula. Le variabili vengono dichiarate con un nome univoco e l'espressione di misura deve quindi essere restituita dopo la `RETURN` parola chiave . A differenza di altre variabili del linguaggio di codifica, le variabili DAX possono essere usate solo all'interno del singolo formula._

1. Aggiungere un'altra misura alla `Sales` tabella in base all'espressione seguente:

    ```dax
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

    > _Alla `SalesPriorYear` variabile viene assegnata un'espressione che calcola la somma della `Sales` colonna in un contesto modificato. Tale contesto usa la `PARALLELPERIOD` funzione per tornare a 12 mesi da ogni data nel contesto di filtro._

1. Aggiungere la `Sales YoY Growth` misura all'oggetto visivo matrice.

1. Si noti che la nuova misura restituisce `BLANK` per i primi 12 mesi (perché non sono state registrate vendite prima dell'anno fiscale 2017).

1. Si noti che il valore della `Sales YoY Growth` misura per _il 2018 Jul_ è il valore di vendita per _il 2017 Jul_.

    ![Immagine 2](Linked_image_Files/06-use-dax-time-intelligence-functions_image22.png)

    > _Ora che la "parte difficile" della formula è stata testata, è possibile sovrascrivere la misura con la formula finale che calcola il risultato della crescita._

1. Per completare la misura, sovrascrivere la `Sales YoY Growth` misura con questa formula, formattandola come percentuale con due posizioni decimali:

    ```dax
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

1. Nella formula, nella `RETURN` clausola , si noti che la variabile fa riferimento due volte.

1. Verificare che la crescita YoY per _il 2018 Jul_ sia del 392,83%.

    ![Immagine 3](Linked_image_Files/06-use-dax-time-intelligence-functions_image23.png)

    > _La misura di crescita YoY identifica quasi il 400% (o 4x) dell'aumento delle vendite nello stesso periodo dell'anno precedente._

1. Nella **visualizzazione** Modello posizionare le due nuove misure in una cartella di visualizzazione denominata _Business Intelligence per le gerarchie_ temporali.

    ![Immagine 4](Linked_image_Files/06-use-dax-time-intelligence-functions_image24.png)

1. Salvare il file di Power BI Desktop.

## Lab completato

È possibile scegliere di salvare il report di Power BI, anche se non è necessario per questo lab. Nell'esercizio successivo si userà un file di avvio predefinito.

1. Passare al **menu "File"** nell'angolo in alto a sinistra e selezionare **"Salva con nome".** 
1. Selezionare **Esplora il dispositivo**
1. Selezionare la cartella in cui si desidera salvare il file e assegnargli un nome descrittivo. 
1. Selezionare il **pulsante Salva** per salvare il report come file con estensione pbix. 
1. Se viene visualizzata una finestra di dialogo che richiede di applicare modifiche alle query in sospeso, selezionare **Applica**.
1. Chiudere Power BI Desktop.