SQL è un lignuaggio di programmazione dichiarativo usato per interrogare, modificare e creare database relazionali (e dunque strutturati). 

Un DBMS molto diffuso che gestisce database relazionali è **MySQL**:

### MySQL
È un DBMS open source, ogni comando termina con **;** i principali per navigare sul DBMS sono:


```MySQL
CREATE DATABASE nome_database;
```


```MySQL
SHOW DATABASES;
```


```MySQL
USE nome_database;
```


```MySQL
DROP database nome_database;
```


```MySQL
    CREATE TABLE book_inventory (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    book_name VARCHAR(255) NOT NULL,
    publication_date DATE
);
```

Il comando permette di creare una tabella (dunque una relazione), specificando gli attributi (colonne) che appartengono ad un dominio. Per ogni attributo bisogna specifciare il tipo ed altri parametri eventuali:
- **INT** indica intero;
- **AUTO_INCREMENT** indica che il valore parte da 1 e ad ogni inserimento aumenta di 1;
- **PRIMARY KEY** indica che quell'attriburto è chiave primaria;
- **VARCHAR(255)** sta ad indicare che il tipo è char e la lunghezza massima è di 255 caratteri;
- **NOT NULL** ovviamente indica che un inserimento nullo di quell'attributo non è permesso;
- **DATE** attributo di tipo data;


```MySQL
SHOW TABLES;
```


```MySQL
DESCRIBE nome_tabella;
```
(permette di ottenre la descrizione di tutti gli attributi di una tabella)


```MySQL
ALTER TABLE nome_tabella
	ADD nuovo_attributo INT;
```
Il comando ALTER permette di modificare la tabella ad esempio aggiugendo o rimuovendo un attributo


```MySQL
DROP TABLE nome_tabella;
```


```MySQL
INSERT INTO books (id, name, published_date, description) 
	VALUES (1, "Android Security Internals", "2014-10-14", "An In-Depth Guide to Android's Security Architecture");
```
Il comando INSERT INTO permette di aggiungere delle righe ad una tabella, per farlo bisogna specificare la tabella, le colonne corrispettive ai valori che dobbiamo in inserire (solo se non inseriamo valori per ogni attributo) ed i valori da inserire, i quali devono rispettare l'ordine della tabella.


```MySQL
SELECT * FROM books;
```
Con SELECT otteniamo i dati presenti nella tabella books, con la wild card facciamo ovviamente riferimento a tutte le colonne, possiamo però specificare ad esempio:


```MySQL
SELECT name, description FROM books;
```


```MySQL
UPDATE books
	SET description = "Descrizione di una riga in particolare"
	WHERE id = 1;
```
Il comando UPDATE permette di modificare dei record esistenti, con SET specifichiamo il nome della colonna (attributo) che andremo ad aggiornare mentre con WHERE identifichiamo la riga


```MySQL
DELETE FROM books WHERE id = 1;
```


All'interno dei comandi si possono usare delle **clausole** che permettono di manipolare i dati su cui si stanno facendo delle interrogazioni, alcune sono **FROM, WHERE** mentre altre sono:

- **DISTINCT**, permette di ottenre i risultati senza alcun valore di qualsiasi attributo duplicato;
	
```MySQL
SELECT DISTINCT name FROM books;
```

- **ORDER BY**, permette di ordinare i risultati rispetto al valore di un attributo, ad esempio in ordine ascendente o discendente, rispettivamente mediante le funzioni ASC e DESC;

```MySQL
SELECT *
FROM books
ORDER BY published_date ASC;
```





#Database #MySQL
