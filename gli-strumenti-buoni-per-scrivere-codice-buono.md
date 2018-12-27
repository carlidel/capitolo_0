---
description: (in C++)
---

# Gli strumenti buoni per scrivere codice buono

Per riuscire a scrivere codice funzionante con sufficiente agilità e senza cadere in violente crisi depressive, è di vitale importanza poter contare su di un set di strumenti familiari e funzionali per poter gestire un buon flusso di lavoro, tenere sotto controllo gli errori e i progressi e, soprattutto, visualizzare in maniera rapida e comoda i valori numerici ottenuti dalle proprie simulazioni.

In questa pagina si indicheranno e consiglieranno alcuni strumenti per la programmazione in C/C++ facendo uso del compilatore gcc/g++ su ambiente Windows 10 con tanto di WSL per gradire.

## I fondamentali

Per fondamentali si indicano quegli strumenti senza i quali diventa molto difficile, se non impossibile, avere un buon flusso di lavoro nella stesura ed esecuzione del codice.

### Un buon editor di codice

Scrivere codice funzionante è difficile, molto difficile. Le cose di cui tenere traccia durante la costruzione del flusso logico di istruzioni sono molte ed è inevitabile commettere errori umani durante tale processo. Per venire incontro a queste limitazioni umane, tuttavia, esistono editor di codice informatico pieni di utilità di supporto pensate proprio per ridurre al minimo l'occorrenza di tali errori.

Avere un buon editor di codice significa avere un editor:

* Capace di identificare e colorare qualsiasi tipo di linguaggio di programmazione esistente.
* Che permette di esplorare comodamente a lato cartelle e file per gestire molteplici file con facilità.
* Che offre tutti sistemi intelligenti per modificare in fretta grandi porzioni di testo con strumenti più raffinati di un semplice "Trova e Sostituisci".
* Che è in grado di interpretare in tempo reale il codice scritto e fornire suggerimenti di autocompletamento ed identificare errori ovvi, tipo l'utilizzo di una variabile mai dichiarata in nessuna parte del progetto in utilizzo.
* Che è in grado di leggere tutti i metodi standard di una libreria importata e fornire in tempo reale suggerimenti e documentazione mano a mano che ne si utilizzano le componenti.
* Che è in grado di supportare comandi interni di compilazione e di debugging \(in questi casi si comincia a trascendere il concetto di editor di testo e si comincia a parlare di Integrated Development Environment o IDE\)

A seguito si consiglia di provare i seguenti editor, in generale non limitatevi ad usarne solo uno, soprattutto se non vi trovate a vostro agio nel farlo funzionare bene. _È la bacchetta che sceglie il mago, signor Potter!_

* [Visual Studio Code](https://code.visualstudio.com/), ottimo e leggero editor della Microsoft che offre funzionalità ed estensioni per gestire praticamente ogni possibile scenario e linguaggio di programmazione. In particolare brilla la possibilità di configurare singolarmente i propri progetti con specifiche opzioni di compilazione e debugging tramite file di configurazione in formato .JSon.
* [Sublime Text 3](https://www.sublimetext.com/), altro ottimo editor estremamente elegante basato sul linguaggio Python. È in teoria a pagamento, ma la versione di prova è tuttavia a durata illimitata. Anche questo editor permette di gestire ogni linguaggio esistente tramite installazione di pacchetti ed estensioni. Tuttavia ha una interfaccia in tal senso molto meno intuitiva e necessita di molti smanettamenti collaterali per risultare perfetto.
* [Atom](https://atom.io/), editor scritto dal team di Github, anche lui ha il suo sistema ad estensioni universale e permette anche di fare cose fighe come condividere in stile google documents i propri codici per modifiche in parallelo. Tuttavia è un bel bestione da tenere in piedi in termini di memoria e non sempre è molto reattivo ad accendersi.
* [Vim](https://www.vim.org/), è un editor bello tosto e potente da linea di comando, che potete installare direttamente nella vostra bash WSL con apt. Se vi sentite coraggiosi e hackerosi, fate un tentativo. Personalmente... per me è un po' troppo complicato per avventurarmici dentro.

### Un buon \(modo di accedere al\) compilatore

### Un buon sistema di backup e di version control

Per quel che riguarda il **Backup,** l'ideale è conservare sempre le proprie cartelle di lavoro all'interno di cartelle in sincronizzazione con un qualche servizio cloud come Dropbox od i 1000GB gratuiti che OneDrive offre agli studenti Unibo. Ciò permette di non subire gravi ritardi e crolli nervosi in caso di guasti informatici, cataclismi o furti.

Che cosa si intende invece con **version control**? Si intende fare uso di uno strumento che tenga traccia mano a mano di quali modifiche sono state fatte progressivamente alle varie parti del codice. Quando si fanno 10 copie diverse di uno stesso file o documento \(chiamandole finale.cpp, finaleDavvero.cpp, finaleFinaleDavvero\_v2.cpp e così via\) si sta facendo manualmente e in malo modo una sorta di version control. Fortunatamente, esistono svariati strumenti che permettono di tenere traccia di tutte le modifiche ad un file di codice senza mai perdere lo storico di tutto quanto è stato scritto, riscritto o cancellato.  
Lo strumento più famoso usato in programmazione per fare ciò è [Git](https://www.youtube.com/watch?v=Y9XZQO1n_7c). E verrà analizzato più nel dettaglio nella pagina "Git è una cosa bella", in quanto strumento di vitale importanza per tenere traccia dei progressi di un progetto grosso o di gruppo.

### Un buon framework per fare grafici

Siamo fisici. I fisici devono essere in grado sempre di presentare a modo ogni tipo di dato sperimentale esistente in forma chiara, ordinata, corretta e, soprattutto, elegante. Qualsiasi sarà il programma di simulazione numerica che verrà scritto, è vitale che sia studiato a parte un buon sistema agile di stampa e di visualizzazione dei dati prodotti. Altrimenti non vale la pena di prendersi il disturbo di scrivere il codice in prima istanza.  
A seguito sono elencati alcuni strumenti che possono essere più o meno facilmente integrati con il proprio codice. Non vengono presi in considerazione strumenti come Excel o LibreOffice Calc.

1. [ROOT CERN](https://root.cern.ch/), framework di analisi statistica e plotting basato in C/C++ utilizzato nei principali progetti del CERN. È uno strumento molto potente e vasto la cui padronanza permette di maneggiare qualsiasi tipo di dato o grafico possibile. Tuttavia, la sua sintassi di utilizzo risulta molto ostica e tutt'altro che intuitiva, a meno di investire tempo a leggere i vari manuali di utilizzo. Si consiglia di seguire pedissequamente i corsi di Laboratorio 1 e 2 per apprendere il più possibile riguardo l'utilizzo di questo strumento.
2. [GnuPlot](http://www.gnuplot.info/), programma di plotting per antonomasia su Linux, ha una sintassi molto più agile e leggera e facile da usare di ROOT CERN e, tramite l'inclusione di una singola libreria o tramite l'utilizzo di chiamate a sistema all'interno del proprio codice, è possibile fare il plot di qualsiasi cosa senza troppe difficoltà.
3. [Matplotlib](https://matplotlib.org/), la libreria standard di plotting e grafica su linguaggio Python. Se uno si prende il tempo di imparare un po' di linguaggio Python, si ha la possibilità di fare in 5 righe di codice l'equivalente di 30 righe in ROOT CERN. La documentazione estremamente completa su internet rende questa libreria capace di affrontare ogni situazione o scenario esistente di analisi dati, potendo anche contare sulla sintassi estremamente agile e flessibile del linguaggio Python \(maggiori dettagli in "Il Python è una cosa bella!"\).

## Gli avanzati \(ma molto utili\)

### Un buon debugger

### Un buon profiler

