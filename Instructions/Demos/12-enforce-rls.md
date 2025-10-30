---
demo:
  title: Applicare la sicurezza a livello di riga in Power BI
  module: Secure data access in Power BI
---

# Applicare la sicurezza a livello di riga in Power BI

## Aggiungere una tabella di sicurezza al modello

1. In Power BI Desktop aprire la finestra editor di Power Query.

1. Aggiungere una nuova query in base al`D:\Demo\Data\**ManagerCategory**.xlsx` file.

1. Usare la**tabella ManagerCategory** nel file .

1. Rimuovere la colonna**Manager**.

1. Dividere la colonna**Category** con il delimitatore punto e virgola e dividerla in righe (opzioni avanzate).

1. **Nella colonna Posta elettronica** sostituire il valore**<ty-johnston@tailspintoys.com>** con l'account del destinatario (dal file di MySettings.txt).

1. Indicare che questo utente è in grado di visualizzare tre categorie di prodotti:**pitch collettivo, Trainer e Warbird**.

1. Chiudere e applicare le query.

1. Nella visualizzazione Modello creare una relazione tra le**tabelle ManagerCategory** e Product correlate alla**colonna Category** .

1. Impostare la direzione del filtro incrociato su Single (**ManagerCategory** filters Product).

1. Nascondere la tabella**ManagerCategory**.

## Aggiungere un ruolo

1. Nella visualizzazione Report aprire Gestisci ruoli e quindi creare un ruolo denominato**Manager**.

1. Nel ruolo filtrare la colonna Indirizzo di posta elettronica della**tabella ManagerCategory** come indicato di seguito:

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **Salva**.

## Convalidare il ruolo

1. Aprire Visualizza come, quindi configurare le impostazioni seguenti:

    - Altro utente: controlla, quindi immetti l'account del destinatario.

    - Ruolo manager: Verifica

1. Fare notare che l'oggetto visivo filtro mostra solo tre categorie di prodotti.

1. Interrompere la visualizzazione del report usando le opzioni view-as.

1. Salvare il file di Power BI Desktop.

1. Pubblicare il file di Power BI Desktop nell'area di lavoro, sovrascrivendo il modello semantico e il report nel servizio.

1. Chiudere Power BI Desktop.

## Configurare la sicurezza del modello semantico

1. Nel servizio Power BI per l'insegnante, nel riquadro di spostamento aprire la pagina sicurezza per il**modello semantico Sales Analysis**.

1. Nella sezione**Members** immettere l'account del destinatario (corrispondente a Ty Johnston).

1. Aggiungere e salvare.

## Testare la sicurezza a livello di riga nell'app

1. Nel servizio Power BI per il destinatario, aggiornare il dashboard (lasciato aperto dalla demo precedente).

1. **Nel riquadro dashboard Profit Margin** verificare che sia possibile visualizzare solo tre categorie di prodotti.
