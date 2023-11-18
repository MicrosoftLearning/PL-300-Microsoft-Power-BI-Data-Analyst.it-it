---
lab:
  "\_\_ title": Create measures using DAX in Power BI
  "\_\_ module": Create measures using DAX in Power BI
---
# Creare misure con DAX in Power BI

> **Suggerimento**: tutti i calcoli possono essere copiati dal file D:\PL300\Demo\Resources\Snippets-Demo-05.txt.

## Creare una tabella calcolata

1. Creare una tabella calcolata usando l'espressione seguente:

```dax
Date = CALENDARAUTO()
```

1. Passare alla visualizzazione dati ed esaminare la tabella, che comprende una colonna a data singola.

Creare colonne calcolate

1. Aggiungere una colonna calcolata alla tabella Date:

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Aggiungere un'altra colonna calcolata alla tabella Date:

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. Nella vista Modello creare una relazione trascinando la tabella Date, colonna Date sulla tabella Sales, colonna OrderDate.

1. Nascondere la tabella Sales, colonna OrderDate.

1. Nella tabella Date creare la gerarchia Calendar, con i livelli Year e Month.

1. Nella vista Report contrassegnare la tabella Date come tabella delle date, usando la colonna Date.

1. Nell'oggetto visivo matrice rimuovere la gerarchia Products e sostituirla con la gerarchia Calendar.

1. Aggiungere una colonna calcolata alla tabella Sales:

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Formattare la colonna Cost con due cifre decimali.

## Creare una misura rapida

1. Aggiungere una misura rapida alla tabella Sales, sottraendo la colonna Cost dalla colonna Profit.

1. Rinominare la misura Profit.

1. Spiegare che la misura non memorizza dati nel modello.

Creare misure regolari

1. Aggiungere una misura alla tabella Sales:

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Formattare la colonna Profit Margin come percentuale.

1. Aggiungere un'altra misura alla tabella Sales:

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Formattare la colonna Sales YTD con due cifre decimali.

## Convalidare i calcoli con l'oggetto visivo matrice

1. Aggiungere i campi Cost, Profit, Profit Margin e Sales YTD all'oggetto visivo matrice.

1. Salvare il file di Power BI Desktop.

1. Lasciare aperto il file di Power BI Desktop per una demo successiva.
