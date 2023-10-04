---
demo:
  "\_\_ title": Manage files and datasets in Power BI
  "\_\_ module": Deploy and manage Power BI service items
---
# Gestire file e set di dati in Power BI

## Predisporre l'aggiornamento dati del gateway

> **Si noti** che i passaggi seguenti non sono necessari quando si usa il gateway dati in modalità personale. È possibile procedere direttamente al prossimo obiettivo (impostare il gateway).

1. In Power BI Desktop aprire la finestra dell'editor di Power Query e selezionare la query **ProductCost**.

1. Modificare il passaggio Origine e quindi modificare il percorso del file per usare la condivisione file, come indicato di seguito:

    `\\DATA-AI\Data\ProductCost.xlsx`

1. Chiudere e applicare la finestra dell'editor di Power Query.

1. Salvare il file di Power BI Desktop.

1. Pubblicare il file di Power BI Desktop nell'area di lavoro, sovrascrivendo il set di dati e il report nel servizio.

## Configurare il gateway (modalità personale)

1. Nel servizio Power BI per l'istruttore, ricaricare (F5) la pagina delle impostazioni del set di dati.

1. Espandere la sezione Connessione gateway e far notare che non è installato alcun gateway.

1. Usare l'elenco a discesa dei download (situato in alto a destra) e selezionare Gateway dati.

1. Nella nuova pagina Web scaricare il gateway in modalità personale.

1. Una volta scaricato il file, aprirlo.

1. Completare la configurazione del gateway usando le credenziali dell'account dell'istruttore.

1. Terminata la configurazione, tornare alla pagina delle impostazioni del set di dati e ricaricarla.

1. Assegnare il gateway personale e modificare le credenziali per le due origini dati.

1. Per entrambe le origini dati, impostare il metodo di autenticazione su **WindowsWithoutImpersonation** e impostare il livello di privacy su **Aziendale**.

1. Facoltativamente, espandere la sezione **Aggiornamento pianificato** e mostrare come configurare una pianificazione ricorrente.

## Aggiornare il set di dati

1. Prima di aggiornare il set di dati, aprire il dashboard **Sales Monitoring**.

1. Modificare i dettagli del riquadro Sales, Profit Margin per visualizzare l'ora dell'ultimo aggiornamento.

1. Fare clic con il pulsante destro del mouse sul `D:\PL300\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1` file e quindi eseguire con PowerShell. *Questo script caricherà i dati di vendita di dicembre 2020 nel database.*

1. Nel servizio Power BI per il docente, dal riquadro di spostamento aggiornare il set di dati **Sales Analysis**.

1. Al termine dell'aggiornamento, indica come viene visualizzato il riquadro del dashboard **di dicembre 2020** e che l'ora di aggiornamento è **ORA**.
