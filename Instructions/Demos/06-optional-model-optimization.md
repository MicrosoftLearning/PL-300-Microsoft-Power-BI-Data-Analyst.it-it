---
demo:
  title: (Facoltativo) Ottimizzare le prestazioni del modello in Power BI
  module: Optimize model performance in Power BI
---

# (Facoltativo) Ottimizzare le prestazioni del modello

## Esaminare il progetto di un modello DirectQuery

> **Nota**: questa demo usa un file di Power BI Desktop diverso.

1. Aprire il file D:\Allfiles\Demo\Resources\AW Sales Analysis.pbix.

1. Se viene richiesto di connettersi all'origine dati, fare clic su Connetti.

1. Nell'angolo in basso a destra, fare notare che il modello di dati comprende tabelle DirectQuery.

1. Salvare il file di Power BI Desktop nella cartella D:\Allfiles\Demo\MySolution.

1. Nella vista Modello presentare il progetto del modello, che include due tabelle correlate.

1. Nella vista Report interagire con il report selezionando elementi diversi nel filtro dei dati Fiscal Year.

1. Scorrere qualsiasi colonna del mese per rivelare i dettagli dell'ordine.

1. Tornare alla pagina Sales Summary.

## Esaminare le prestazioni delle query

1. Nella scheda Visualizza della barra multifunzione mostrare il riquadro Analizzatore prestazioni.

1. Aggiornare gli oggetti visivi e quindi espandere l'oggetto visivo Sales by Month e Sales by Month.

1. Indicare che è stata usata la modalità DirectQuery (i dati sono stati richiesti dall'origine dati).

## Configurare le tabelle di archiviazione doppie

1. Nella vista Modello selezionare la tabella Date, quindi selezionare Dual come modalità di archiviazione.

1. Una volta importati i dati, passare alla vista Report, quindi nel riquadro Analizzatore prestazioni aggiornare gli oggetti visivi.

1. Segnalare che ora le query vengono eseguite nella tabella Date a partire dalla cache del modello.

## Creare aggregazioni

1. Aprire la finestra dell'editor di Power Query e nel riquadro Query duplicare la query Reseller Sales.

1. Rinominare la nuova query Reseller Sales Agg.

1. Applicare una trasformazione per gruppo, come segue:

    - Raggruppare per OrderDate.

    - Nuova colonna: Sales, che rappresenta la somma della colonna SalesAmount.

1. Chiudere e applicare le query.

1. Nella vista Modello impostare la modalità di archiviazione per la tabella Reseller Sales Agg su Importazione.

1. Creare una relazione dalla tabella Date, colonna Date alla tabella Reseller Sales Agg, colonna OrderDate. Assicurarsi che la cardinalità della colonna sia impostata su da uno-a-molti, con la tabella Date sul lato uno.

1. Gestire le aggregazioni nella tabella Reseller Sales Agg:

    - OrderDate: raggruppare in base alla tabella Reseller Sales, colonna OrderDate.

    - Sales: sommare la tabella Reseller Sales, colonna SalesAmount.

1. Segnalare che la tabella di aggregazione è ora nascosta.

1. Passare alla vista Report e nel riquadro Analizzatore prestazioni aggiornare gli oggetti visivi.

1. Segnalare che ora le query vengono eseguite nella tabella Sales by Month a partire dalla cache del modello.

1. Eseguire il drill through da qualsiasi mese, e far notare che i dettagli nella tabella sono richiesti come DirectQuery dall'origine dati.

1. Salvare il file di Power BI Desktop.

1. Chiudere Power BI Desktop.

> **Nota**: questa soluzione Power BI Desktop non verrà più usata.
