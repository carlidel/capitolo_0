---
description: Come avere un compilatore di base per poter cominciare a seguire le lezioni
---

# Iniziare ammodo col C++

Si presuppone che il lettore abbia sottomano una bash WSL funzionante. In caso diverso questi comandi sono comunque validi su qualsiasi distribuzione Ubuntu.

## Installare il compilatore gcc/g++

È molto facile, basta aprire una linea di comando WSL scrivendo `bash` su di una linea di comando Windows e poi scrivete:

```bash
$ sudo apt update
$ sudo apt install build-essential
```

La prima riga vuol dire: eseguimi con permesso di amministratore \(`sudo`\) il programma gestore di pacchetti software standard di Ubuntu \(`atp`\) ed aggiornami da internet \(`update`\) tutto il software installabile esistente nei repository ufficiali di Ubuntu.

La seconda riga riga vuol dire: eseguimi con permesso di amministratore \(`sudo`\) il programma gestore di pacchetti software standard di Ubuntu \(`atp`\) ed installami \(`install`\) il pacchetto software `build-essential`.

Questo pacchetto contiene tutti gli strumenti di sviluppo minimi standard, tra cui il compilatore gcc/g++, il compilatore standard OpenSource per il linguaggio C/C++. Nonché il compilatore standard di praticamente tutti i corsi universitari di programmazione in C/C++.

### E come lo uso questo compilatore per il C++?

Guarda [qui](https://courses.cs.washington.edu/courses/cse373/99au/unix/g++.html), oppure comincia direttamente a leggere [La C++ Commedia](http://www.physycom.unibo.it/labinfo/per_cominciare.php).

## E per scrivere il codice?

La scelta di editor di codice è sconfinata. Io personalmente uso [Visual Studio Code](https://code.visualstudio.com/), ma ne parliamo meglio nella pagina dopo.

