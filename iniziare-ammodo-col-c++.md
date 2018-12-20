---
description: Come avere un compilatore di base per poter cominciare a seguire le lezioni
---

# Iniziare ammodo col C++

Si presuppone che il lettore abbia sottomano una bash WSL funzionante. In caso diverso questi comandi sono comunque validi su qualsiasi distribuzione Ubuntu.

## Installare il compilatore gcc/g++

È molto facile, basta aprire una linea di comando WSL scrivendo `bash` su di una linea di comando Windows e poi scrivete:

```bash
sudo apt update
sudo apt install build-essential
```

La prima riga vuol dire: eseguimi con permesso di amministratore \(`sudo`\) il programma gestore di pacchetti software standard di Ubuntu \(`atp`\) ed aggiornami da internet \(`update`\) tutto il software installabile esistente nei repository ufficiali di Ubuntu.

La seconda riga riga vuol dire: eseguimi con permesso di amministratore \(`sudo`\) il programma gestore di pacchetti software standard di Ubuntu \(`atp`\) ed installami \(`install`\) il pacchetto software `build-essential`.

Questo pacchetto contiene tutti gli strumenti di sviluppo minimi standard, tra cui il compilatore gcc/g++, il compilatore standard OpenSource per il linguaggio C/C++. Nonché il compilatore standard di praticamente tutti i corsi universitari di programmazione in C/C++.

### E come lo uso questo compilatore per il C++?

Guarda [qui](https://courses.cs.washington.edu/courses/cse373/99au/unix/g++.html), oppure comincia direttamente a leggere [La C++ Commedia](http://www.physycom.unibo.it/labinfo/per_cominciare.php).

## E per scrivere il codice?

La scelta di editor di codice è sconfinata. Io personalmente uso [Visual Studio Code](https://code.visualstudio.com/), ma ne parliamo meglio nella pagina dopo.

## Qualche fonte in più per cominciare col C++?

Le [Olimpiadi di Informatica](https://www.olimpiadi-informatica.it/) per licei, dal livello di selezione territoriale al livello di gara mondiale, sono una meravigliosa fonte di nozioni su come programmare bene in C++ degli algoritmi di alto livello \(ed includono una splendida letteratura sull'argomento della complessità computazionale di un algoritmo\). 

In particolare, si consiglia di:

1. Prendere visione di questo [splendido manuale](https://www.imparando.net/sito/olimpiadi_di_informatica/guida_quarta_edizione.pdf) per principianti che tratta di come risolvere alcuni problemi semplici di algoritmica in C++ affrontando testi delle selezioni territoriali.
2. Fare un giro sul [correttore online aperto](https://training.olinfo.it/#/overview) di esercizi delle Olimpiadi di Informatica, dove è possibile prendere visione di tutti i problemi di tutte le gare passate e, soprattutto, allenarsi a scrivere codice sottoponendo le proprie proposte di soluzione.
3. Se si vuole approfondire l'argomento, prendere visone di questo [meraviglioso manuale](https://cpbook.net/) di livello internazionale su come fare hard training di algoritmica e strutture dati ad un livello ultra generale e assoluto \(utilissimo per ogni possibile progetto futuro di computazione\).

