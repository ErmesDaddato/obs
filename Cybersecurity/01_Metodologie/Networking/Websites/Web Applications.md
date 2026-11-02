Per connettersi ad una web app si utilizza ovviamente un link per accedere ai vari contenuti, i link hanno la seguente struttura:
[[Web_Applications_Link.png]]

Le parti su cui porre più attenzione sono:
- **Host/Domain**, in quanto possono essere soggetti a **Typosquatting**, una tecnica che consiste nell'utilizzare nomi molto famosi cambiati solo di qualche lettera per trarre in inganno i visitatori;
- **Query String**, in quanto se non correttamente gestita lato server espone la web application ad attacchi di **injection**;

### Richieste HTTP
Le richieste http e le risposte dai server permettono di analizzare le comunicazioni.
Ogni messaggio è caratterizzato dalla seguente struttura:

- **Header** in cui vengono specificati parametri come l'host e il protocollo HTML, la prima linea è detta **Request Line** e specifica che tipo di richiesta è , tramite parametri come il **Method** (GET, POST, PUT, ...) e il path della risorsa a cui si vuole accedere;
  
- **Empty Space**, lasciato per dividere l'header dal body. Se non presente causa errori nella comunicazione;
  
- **Body** è il contenuto del messaggio inviato, es. pagina html o i parametri ad esempio per il login (username e password) per accedere alla risorsa specificata nella Request Line, la richiesta presente nel body può avere diversi formati, json, Form Data, in base al tipo di richiesta specificata nel **content-type** presente nell'header;

Ulteriori informazioni, come lo **user-agent** o i **cookie** possono essere inviati al server mediante dei parametri aggiuntivi nell'header, detti **request header**. 

Nelle **Risposte HTTP**, nell'header sono presenti:
- **Status Line**, contenente versione HTTP utilizzata, e lo **Status Code** che ci fornisce informazioni su come è andata la richiesta;
- **Response Header**, che contiene informazioni riguardanti il tipo di contenuto, i **cookie** da settare e altri parametri come il server (può essere rimosso per motivi di sicurezza), il cache-control, ... ;


> [!Danger] **Gestione dei Cookie**
> I cookie possono essere un vettore di attacco in quanto se manipolati possono essere usati per **injection** come ad esempio **Cross-Site-Scripting (XSS)**, per questo motivo bisogna impostare sul server i flag **HttOnly** che permette di inviare e ricevere cookie solo mediante http dunque non possono essere manipolati con javascript e **Secure** così da implementare HTTPS

### Security Headers
Permettono di implementare una maggiore sicurezza della Web-Application, i più importanti sono:

- **Content-Security-Policy (CSP)**, previene attacchi come il Cross-Site Scripting (XSS) specificando quali fonti sono considerate sicure in base al tipo di attività, ad esempio la fonte da cui caricare gli script. Ripempiendo il campo con "**self**" si fa riferimento al dominio stesso:
```
Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.tryhackme.com; style-src 'self'
```

- **Strict-Transport-Security (HSTS)**,  obbliga il client a mantenere sempre una connessione tramite HTTPS

- **X-Content-Type-Options**, se usato indica al browser di non provare ad indovinare le estensioni dei risorse ma solo di usare il formato indicato nel **Content-Type-Header**

- **Referrer-Policy**, controlla le informazioni inviate al server di destinazione quando si usa un link sulla pagina web;


### JavaScript
È un linguaggio interpretato dal browser che permette di aggiungere interattività alle pagine web e alle web app. 

> [!Attention] **Gestire il JS**
> Come è facile intuire gestire correttamente questo linguaggio è essenziale per evitare attacchi del tipo XSS. Uno dei modi per rendere il JS difficile alla lettura umana e rendere anche la sua interpretazione più veloce dal lato del browser è quello di **offuscare** il codice e aggiungere pezzi di codice inutili. Per fare ciò ci sono una serie di tool online, anche se il processo inverso è altrettanto semplice. 

> [!Danger] **Validazione lato client**
> Validare i dati inseriti in un form o in un generico campo mediante codice JS che gira sul client, prima che questi vengano inviati al server è una pessima operazione in quato il codice potrebbe essere manipolato dall'utente sul suo stesso client


#Websites #Richieste_HTTP