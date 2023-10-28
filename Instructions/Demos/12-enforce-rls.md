---
lab:
  "\_\_ title": Enforce Row-level security in Power BI
  "\_\_ module": Deploy and manage Power BI service items
---
# Applicare la sicurezza a livello di riga in Power BI

## Aggiungere una tabella di sicurezza al modello

1. In Power BI Desktop aprire la finestra di editor di Power Query.

1. Aggiungere una nuova query in base al `D:\Demo\Data\**ManagerCategory**.xlsx` file.

1. Usare la tabella **ManagerCategory** nel file.

1. Rimuovere la colonna **Manager**.

1. Dividere la colonna **Category** con il delimitatore punto e virgola e dividerla in righe (opzioni avanzate).

1. Nella colonna **Email** sostituire il valore **<ty-johnston@tailspintoys.com>** con l'account destinatario (dal file MySettings.txt).

1. Tenere presente che questo utente è in grado di visualizzare tre categorie di prodotti: **pitch collettivo, Trainer e Warbird**.

1. Chiudere e applicare le query.

1. In Visualizzazione Modello creare una relazione tra le tabelle **ManagerCategory** e Product relative alla colonna **Category** .

1. Impostare la direzione del filtro incrociato su Single (**ManagerCategory** filter Product).

1. Nascondere la tabella **ManagerCategory**.

## Aggiungere un ruolo

1. In Visualizzazione report aprire Gestisci ruoli e quindi creare un ruolo denominato **Manager**.

1. Nel ruolo filtrare la tabella **ManagerCategory**, colonna indirizzo Email nel modo seguente:

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **Salvare**.

## Convalidare il ruolo

1. Aprire Visualizza come, quindi configurare le impostazioni seguenti:

    - Altro utente: Selezionare, quindi immettere l'account del destinatario.

    - Ruolo manager: Verifica

1. Fare notare che l'oggetto visivo filtro mostra solo tre categorie di prodotti.

1. Interrompere la visualizzazione del report usando le opzioni view-as.

1. Salvare il file di Power BI Desktop.

1. Pubblicare il file di Power BI Desktop nell'area di lavoro, sovrascrivendo il set di dati e il report nel servizio.

1. Chiudere Power BI Desktop.

## Configurare la sicurezza del set di dati

1. Nel servizio Power BI per il docente, dal riquadro di spostamento aprire la pagina di sicurezza per il set di dati **Sales Analysis**.

1. Nella sezione Membri immettere l'account destinatario (che rappresenta **Ty Johnston**).

1. Aggiungere e salvare.

## Testare la sicurezza a livello di riga nell'app

1. Nel servizio Power BI per il destinatario, aggiornare il dashboard (lasciato aperto dalla demo precedente).

1. Nel riquadro dashboard **Profit Margin** verificare che siano visualizzate solo tre categorie di prodotti.
