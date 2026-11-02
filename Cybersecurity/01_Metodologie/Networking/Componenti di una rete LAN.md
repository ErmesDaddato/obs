I componenti di una rete LAN sono:

- **Router**, instrada il traffico della rete locale verso il mondo esterno (internet) oppure verso la rete interna, i router di casa sono formati da 3 componenti:
		- un router
		- uno switch piccolo (spesso 4 porte)
		- un AP per creare la rete Wi-Fi

- **Switch**, si occupa di creare una rete LAN fisica, è una "scatola" con numerose porte ethernet che servono per mettere in collegamento tra loro i diversi dispositivi della rete. Se collegato ad un router lo switch permette anche di instradare le connessioni verso l'esterno, altrimenti permetterebbe la sola comunicazione tra i dispositivi presenti nella LAN.

- **AP (Access Point)**, la sua funzione è quella di creare una rete wireless per permettere la comunicazione tra i dispositivi. Se unito ad uno switch (che è a sua volta collegato ad un router) permette l'estensione della rete Wi-Fi del router. È molto comodo perchè gli Switch moderni permettono di alimentare gli AP tramite lo stesso cavo di rete e dunque può essere applicato in posti dove il cablaggio elettrico non arriva.
  **La sua funzione principale sta nel convertire i frame inviati sulla rete Wifi tramite IEEE 802.11 in IEEE 802.3 per inviarli allo switch a cui è connesso.** 
  Un AP lavora allo stesso modo di uno switch ma con le onde radio del Wi-fi, ovvero se due dispositivi vogliono comunicare e sono connessi allo stesso AP allora il segnale viene trasmesso con l'idirizzo MAC del destinatario, arriva all'AP che controlla la sua tabelle delle corrispondenze degli indirizzi e se lo trova lo inoltra al destinatario senza conversioni, altrimenti lo converte nel formato Ethernet e lo inoltra allo switch che lo inoltrerà ad un altro AP o al router.
  Un AP lavora ovviamente al secondo livello.

> [!Attention]
> Siccome anche gli AP come visto possono mettere in comuncazione più dispositivi tra di loro connessi alla stessa rete/AP, questa funzione può essere disattivata mediante **AP Isolation** ovvero una funzione che permette solo di inoltrare le richieste dall'AP al router (passando per lo switch) per l'accesso ad internet. Questa funzione è ovviamente molto utile in reti pubbliche come al bar 


> [!Info]
> Nelle sottoreti sono presenti dei dispositivi chiamati **Default Gateway** che si occupano di mettere in comunicazione sottoreti diverse tra loro, così da permettere una eventuale comunicazione tra due dispositivi presenti in due sottoreti distinte.


> [!TIP] VLAN (Virtual Local Area Network)
>Quando una rete fisica (LAN) viene separata ad esempio in due sottoreti, si dice che si creano due VLAN, in quanto la separazione non è fisica, bensì è virtuale
 

#Networking 