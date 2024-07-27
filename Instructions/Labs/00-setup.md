---
lab:
  title: Configurare l'ambiente personale
  module: Set up your own environment
---

# Configurare l'ambiente lab locale

Idealmente, è consigliabile completare questi lab in un ambiente lab ospitato. Se si intende completarli nel proprio computer, è possibile eseguire questa operazione installando il software seguente.

- Tutti i file di installazione e risorse possono essere [scaricati da GitHub](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip).
  - Estrarre la cartella 'AllFiles' in D:/ e rinominarla in 'D:\Allfiles\'.

***È possibile che vengano visualizzate finestre di dialogo impreviste o si verifichino comportamenti diversi dal previsto quando si usa il proprio ambiente. A causa dell'ampia gamma di configurazioni locali possibili, il team del corso non può offrire supporto per i problemi che potrebbero verificarsi nell'ambiente specifico.***

## Istruzioni riferite a Windows 11

> &#128221; Le istruzioni seguenti sono relative a un computer Windows 11. Se ci si connette da un altro sistema operativo l'esperienza potrebbe essere diversa.

### Power BI Desktop

1. Scaricare e installare da Microsoft Store. Se non si ha accesso a Microsoft Store, eseguire il download dal [Web](https://www.microsoft.com/download/details.aspx?id=58494). Power BI Desktop è l'applicazione principale per questi lab.

    - Usare le opzioni predefinite nel programma di installazione.

### Account per sviluppatore M365

Per alcuni degli esercizi, sarà necessario accedere a Power BI con un account aziendale. È possibile usare il proprio, ma se non si ha accesso, è possibile creare un [account per sviluppatore M365](https://developer.microsoft.com/en-us/microsoft-365/dev-program) gratuito.

### Motore di database di SQL Server

1. Il lab si connette a un'istanza di SQL Server localhost. Le istruzioni seguenti consentiranno di installare SQL Server e configurare le opzioni predefinite. È necessario installare solo la funzionalità Motore di database.

    - Scaricare la [copia gratuita per sviluppatori dei supporti di installazione](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1)
    - [Installare SQL Server dall'Installazione guidata (programma di installazione)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> &#128221; È possibile usare un'istanza di SQL Server esistente se accessibile, anziché installare una versione locale. È tuttavia necessario modificare la stringa di connessione da "localhost" al nome dell'istanza.

### Microsoft Edge

1. Installare la versione più recente di [Microsoft Edge](https://microsoft.com/edge) per accedere al servizio Power BI online.
