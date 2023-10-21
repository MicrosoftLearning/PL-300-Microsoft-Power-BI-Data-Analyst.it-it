---
lab:
  "\_\_ title": 'Clean, transform, and load data in Power BI'
  "\_\_ module": 'Clean, transform, and load data in Power BI'
---
# Pulire, trasformare e caricare i dati in Power BI

## Applicare trasformazioni alle query

1. In primo luogo applicare le trasformazioni alla query Product.

1. Rimuovere le colonne RetailPrice, Photo e Sales.

1. Modificare il tipo di dati della colonna Channels in Numero intero.

1. Rinominare le colonne seguenti:

    - ProductSKU in SKU

    - ProductName in Product

    - ProductCategory in Category

    - ItemGroup in Item Group

    - KitType in Kit Type

1. In secondo luogo, applicare le trasformazioni alla query Sales.

1. Rimuovere tutte le colonne, a eccezione di:

    - OrderDate

    - ProductID

    - Quantity

    - UnitPrice

1. Modificare il tipo di dati della colonna UnitPrice in Numero decimale fisso.

1. Rinominare la colonna UnitPrice come Unit Price.

1. Selezionare contemporaneamente le colonne Quantity e Unit Price e aggiungere una nuova colonna basata sulla loro moltiplicazione.

1. Assegnare alla nuova colonna il nome Sales.

## Integrare le query

1. Creare una nuova query usando il connettore di Excel, collegandosi al file D:\PL300\Demo\Data\ProductCost.xlsx.

1. Rimuovere la colonna Product.

1. Modificare il tipo di dati della colonna ProductCost in Numero decimale fisso.

1. Selezionare la query Product, quindi unirla alla query ProductCost, collegando le colonne SKU.

1. Nella finestra Livelli di privacy impostare il livello della privacy per D:\ su Aziendale.

1. Espandere la colonna ProductCost per includere la colonna ProductCost (dalla query ProductCost).

1. Assegnare alla nuova colonna il nome Cost.

## Disabilitare e caricare query nel modello di dati

1. Nel riquadro Query disabilitare la query ProductCost.

1. Nella scheda Home della barra multifunzione fare clic sull'icona Chiudi & Applica.

1. In Power BI Desktop, indicare le due tabelle nel riquadro Dati.

1. Salvare il file di Power BI Desktop.

1. Lasciare aperto il file di Power BI Desktop per la prossima demo.
