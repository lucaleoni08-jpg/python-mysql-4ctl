
## Domande
- Qual è la differenza tra una query scritta direttamente nel codice e una query parametrizzata?
```text
In una query parametrizzata i dati vengono inviati separamente al database, che li tratta esclusivamente come valori e non come stringe con la query diretta
```

- Qual è il vantaggio di avere funzioni di supporto come esegui_select() ed esegui_dml()?
```text
Queste funzioni servono a non dover riscrivere ogni volta le stesse operazioni, come aprire il cursore, gestire gli errori o confermare le modifiche. Invece di avere dieci righe di codice ripetute per ogni operazione, ne usiamo solo una richiamando queste funzioni "assistenti". Questo rende il programma più pulito e molto più facile da correggere se qualcosa non va
```

- In che senso i tre file non sono alternative equivalenti, ma evoluzioni progressive dello stesso codice?
```text
I tre file non sono modi diversi di fare la stessa cosa, ma rappresentano il miglioramento del codice nel tempo. Si parte da uno script disordinato dove tutto è mischiato (file 1), si passa a uno più organizzato con le funzioni (file 2), fino ad arrivare a una struttura professionale (file 3). In quest'ultimo stadio, il codice è diviso in scomparti stagni: uno gestisce solo la connessione e l'altro solo i dati, proprio come in una cucina professionale ogni zona ha il suo compito preciso.
```


## Esercizi
Esercizi a partire dal **terzo file Python**.

### 1. Selezionare tutti i modelli di prodotto
Scrivere una funzione:

```python
seleziona_tutti_modelli(connection)
```

La funzione deve restituire tutte le righe della tabella `modelli_prodotto`

---
### 2. Visualizzare gli acquisti di un utente a partire dalla sua email

Scrivere una funzione:

```python

seleziona_acquisti_cliente(connection, email)
```

La query deve restituire almeno i seguenti campi:

* nome
* cognome
* email
* id_ordine
* data_ordine
* cod_seriale
* nome del modello
* categoria
* prezzo_vendita_effettivo
---

### 3. Contare quanti prodotti di un modello sono presenti a magazzino
Scrivere una funzione:

```python
conta_prodotti_modello(connection, cod_modello)
```

La funzione deve restituire il numero di prodotti presenti a magazzino associati a un determinato modello, identificato tramite il campo cod_modello.

---

### 4. Inserire un nuovo modello di prodotto
Scrivere una funzione:

```python
inserisci_modello(connection, cod_modello, nome, descrizione, categoria, prezzo_listino)
```
La funzione deve permettere di inserire un nuovo modello di prodotto

---

### 5. Aggiornare il prezzo di listino di un modello
Scrivere una funzione:

```python
aggiorna_prezzo_modello(connection, cod_modello, nuovo_prezzo)
```
La funzione deve permettere di modificare il prezzo di listino di un modello di prodotto, a partire dal suo codice

## Indicazioni operative

Per scegliere la funzione di supporto corretta:
- usare `esegui_select(...)` per le query `SELECT`;
- usare `esegui_dml(...)` per le query `INSERT`, `UPDATE` e `DELETE`.

Testare la funzione all'interno del main() e stampare a video il risultato
