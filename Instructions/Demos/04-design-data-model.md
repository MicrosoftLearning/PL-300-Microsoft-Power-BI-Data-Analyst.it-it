---
demo:
  title: Progettazione di un modello di dati in Power BI
  module: Design a data model in Power BI
---
# Progettazione di un modello di dati in Power BI

## Esaminare il modello

1. Nel riquadro Dati espandere tutte le tabelle per visualizzare tutti i campi.

1. Nella tabella Sales indicare la gerarchia OrderDate, che è stata creata automaticamente.

1. Spiegare che nella prossima demo verrà creata una tabella Date.

1. Nella vista Modello, passare il mouse sulla relazione creata automaticamente tra le due tabelle.

1. Spiegare in che modo i filtri si propagano dalla tabella Product alla tabella Sales.

## Creare una gerarchia

1. Creare una gerarchia basata sulla tabella Product, colonna Category.

1. Rinominare la gerarchia in Products.

1. Aggiungere la colonna Product come secondo livello.

## Impostare le proprietà dei modelli

1. Nascondere entrambe le colonne ProductID.

1. Formattare la colonna Quantity per usare il separatore delle migliaia.

1. Selezionare contemporaneamente le colonne Sales e Unit Price e formattarle per usare due posizioni decimali.

## Convalidare il progetto del modello con un oggetto visivo matrice

1. Nella vista Report, aggiungere un oggetto visivo matrice alla pagina, quindi dimensionarlo per occupare l'intera pagina.

1. Aggiungere la gerarchia Products alle righe, quindi aggiungere i campi Quantity, Sales e Unit Price.

1. Espandere tutti i livelli della gerarchia Products.

1. Specificare che i valori Unit Price sono la somma dei prezzi, il che non è corretto.

1. Nel riquadro Dati selezionare il campo Prezzo unitario e configurarne il riepilogo in modo da usare Average.

1. Rimuovere la colonna Sum of Unit Price dall'oggetto visivo matrice, quindi aggiungere nuovamente il campo Unit Price.

1. Salvare il file di Power BI Desktop.

1. Lasciare aperto il file di Power BI Desktop per la prossima demo.
