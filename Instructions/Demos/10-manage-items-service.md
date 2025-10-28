---
demo:
  title: Gestire file e modelli semantici in Power BI
  module: Deploy and manage Power BI service items
---
# Gestire file e modelli semantici in Power BI

## Configurare il gateway (modalità personale)

1. Nella servizio Power BI ricaricare (F5) la pagina delle impostazioni del modello semantico.

1. Espandere la sezione Connessione gateway e indicare che non è installato alcun gateway.

1. Usare l'elenco a discesa dei download (situato in alto a destra) e selezionare Gateway dati.

1. Nella nuova pagina Web scaricare il gateway in modalità personale.

1. Una volta scaricato il file, aprirlo.

1. Completare la configurazione del gateway usando l'account aziendale.

1. Dopo l'installazione, tornare alla pagina delle impostazioni del modello semantico e ricaricarla.

1. Assegnare il gateway personale e modificare le credenziali per le due origini dati.

1. Per entrambe le origini dati, impostare il metodo di autenticazione su**WindowsWithoutImpersonation** e impostare il livello di privacy su**Aziendale**.

1. Facoltativamente, espandere la sezione**Aggiornamento pianificato** e mostrare come configurare una pianificazione ricorrente.

## Aggiornare il modello semantico

1. Prima di aggiornare il modello semantico, aprire il**dashboard Di monitoraggio** vendite.

1. Modificare i dettagli del riquadro Sales, Profit Margin per visualizzare l'ora dell'ultimo aggiornamento.

1. Fare clic con il pulsante destro del mouse sul`D:\Allfiles\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1` file e quindi eseguire con PowerShell. *Questo script caricherà i dati delle vendite di dicembre 2020 nel database.*

1. Nel servizio Power BI per l'insegnante, nel riquadro di spostamento aggiornare il**modello semantico Sales Analysis**.

1. Al termine dell'aggiornamento, indica come viene visualizzato il riquadro**del dashboard dicembre 2020** e che l'ora di aggiornamento è**ORA**.
