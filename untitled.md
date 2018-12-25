---
description: Feticismi tipografici a gogo.
---

# Kinky LaTeX

Imparare a scrivere in LaTeX è vitale nella carriera del fisico e, se usato bene, cambia definitivamente il proprio modo di pensare a come e dove scrivere tutti i documenti di qualsiasi natura e rimuove una enorme quantità di constraint scomodi ed evitabili imposti da editor nella forma WYSIWYG \(What You See Is What You Get\) come Word o LibreOffice Write.

La curva di apprendimento di LaTeX è molto ripida all'inizio, ma dopo averci preso la mano si comincia a scrivere con estrema fluidità qualsiasi tipo di documento contenente equazione matematica complessa, senza avere nessun problema a:

* Gestire enormi quantità di formule matematiche e teoremi, facendovi riferimenti incrociati all'interno del proprio documento con tanto di link interattivi nel .pdf finale prodotto.
* Gestire database bibliografici efficienti e totalmente automatizzati \(vitale nella stesura di una tesi\).
* Impostare tante immagini con label, caption e cross-reference, senza preoccuparsi troppo di dove finiscono in quanto si è consapevoli che il compilatore LaTeX si prenderà cura di collocare l'immagine nella posizione migliore.
* Lasciare che sia il compilatore LaTeX a prendersi cura di impaginare ogni cosa, concentrandosi quindi solo ed esclusivamente sul contenuto del proprio documento.

## Da dove imparare a scrivere in LaTeX?

Scrivere in LaTeX significa scrivere nel linguaggio di programmazione LaTeX che **descrive** quello che è contenuto dentro al documento che si vuole generare e come questo è strutturato. È quindi un editor di documenti nel formato WYSIWYM \(What You See Is What You Mean\)

Questo codice viene poi letto ed interpretato da un **compilatore** di linguaggio LaTeX \(quello usato sempre è PdfLaTeX\), che come risultato, invece di sputare fuori un programma eseguibile come un compilatore C++, sputa fuori il documento descritto dal codice impaginato secondo le migliori norme tipografiche possibili ed esistenti.

La migliore dispensa esistente su come imparare a scrivere in LaTeX è la dispensa gratuita ["L'arte di scrivere con LaTeX"](http://www.lorenzopantieri.net/LaTeX_files/ArteLaTeX.pdf). Aggiungere parole a questo lavoro è una perdita di tempo in quanto è semplicemente perfetta e completa per cominciare e approfondire senza limiti l'argomento.

Tuttavia qualche nota di riassunto rapido orientativo per chi comincia dallo zero assoluto può comunque fare bene.

## Da dove partire a livello Software?

Come detto prima, quando si scrive in LaTeX si sta scrivendo un **codice** informatico che verrà poi successivamente **compilato** da un apposito programma compilatore LaTeX. Questo significa che servono necessariamente 2 strumenti software distinti e separati per lavorare in LaTeX:

1. Un compilatore LaTeX, il quale dovrà poi avere il suo preciso ambiente di sviluppo con librerie, dipendenze e quant'altro.
2. Un editor di codice buono che supporti adeguatamente il linguaggio LaTeX.

Come avere queste 2 cose ben allineate, funzionanti e, soprattutto, comunicanti tra di loro?

### Easy way: un account su Overleaf

Siamo ormai al 2020 praticamente, la tecnologia è arrivata ad un certo punto, esiste quindi un equivalente online/cloud estremamente valido di Google Documents per documenti in formato LaTeX. Questa cosa è offerta da [Overleaf](https://www.overleaf.com/). Un sito che offre la possibilità di produrre, gestire e compilare documenti LaTeX in qualsivoglia formato ed in gruppo direttamente sui loro server, server che ospitano una utopistica installazione di LaTeX che riesce a supportare qualsiasi libreria mai inventata nella storia del LaTeX.

Questo sito è la salvezza quando si hanno da produrre relazioni di laboratorio in gruppo.

### Better way: una installazione locale di LaTeX

Per quanto sia bello il cloud, è di vitale importanza avere sottomano sul proprio computer una installazione locale di LaTeX ed un ambiente di sviluppo adeguatamente funzionante in caso di internet non funzionante o, più in generale, in caso di progetti solitari.

Anche perché lavorare in locale significa poter utilizzare il proprio editor di codice preferito per scrivere in LaTeX \(personalmente, utilizzo sempre Visual Studio Code con su installata l'estensione apposita per supportare il linguaggio LaTeX\).

In ambiente Windows, il compilatore e gestore di pacchetti LaTeX più utilizzato e \(quantomeno\) funzionante è [MiKTeX](https://miktex.org/). Un software bello pesante che, oltre a configurare un ambiente di sviluppo LaTeX di base collocandone i compilatori all'interno delle variabili di ambiente del sistema operativo, offre utilità di installazione automatica \(on-the-fly\) di pacchetti e librerie LaTeX quando queste vengono richieste all'atto di compilazione di un qualche documento LaTeX nuovo. \(Mi raccomando, durante l'installazione specificate che MiKTeX può prendersi la libertà di installare pacchetti nuovi quando questi vengono richiesti!\)

MiKTeX, all'atto dell'installazione, installa anche un editor di codice LaTeX estremamente basic chiamato TeXworks. Questo editor di codice non è malvagio, ma è estremamente basic e di poco aiuto a chi comincia a scrivere in LaTeX per la prima volta, specialmente quando si commettono i primi errori nella stesura del codice.

Si consiglia quindi di cominciare ad usare come primo editor di codice LaTeX il programma [TeXMaker](http://www.xm1math.net/texmaker/), che è molto più di supporto all'utente alle prime armi.

## Sì, ok, ma se volessi un inizio rapido ed estremamente riassunto?

Allegherò qua il mio personale template per scrivere un documento LaTeX nel formato standard _article_, con alcuni trucchetti di esempio ed alcune indicazioni di sorta commentate per quanto riguarda l'implementazione di figure e tabelle, che è sempre la parte più critica. Per quel che riguarda invece la scrittura di equazioni e matematica, la dispensa consigliata è l'unica via sensata da percorrere.

```text
% Dichiarazione di intenti in formato del documento, dell'input e della lingua
\documentclass[10pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}

% Tante belle librerie per scrivere tanta bella matematica
\usepackage{amsmath}
\usepackage{mathtools}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{amsmath}
\usepackage{siunitx}
% Sono un fisico, voglio strumenti utili per scrivere della fisica
\usepackage{physics}

% Metti una etichetta alle mie equazioni se e solo se le cito altrove nel documento
\mathtoolsset{showonlyrefs,showmanualtags}

% Tante belle librerie per metterre tante belle immagini
\usepackage{graphicx}
\usepackage{subfig}
\usepackage{wrapfig}
\usepackage{sidecap}

% Voglio un pdf figo con referenze interattive cliccabili
\usepackage{hyperref}

%%% BackEnd Bibliografico (da attivare solo se lo si usa)
%\usepackage{textcomp}
%\usepackage[autostyle]{csquotes}
%\usepackage[
%        backend=biber,
%        %bibstyle=numeric,
%        %sorting=ynt
%    ]{biblatex}
%\addbibresource{bibliografia.bib}
%\nocite{*}
%%%

%%%%%% TESTO EFFETTIVO

\title{Titolo a caso}
\author{Nome dell'autore \and Nome dell'altro autore}
\date{data che voglio se non voglio che sia messa in automatico quella di oggi}

\begin{document}

% fammi il titolo
\maketitle

% fammi l'indice
\tableofcontents

\begin{abstract}
    Questo è il mio abstract.
\end{abstract}

% Inizia una sezione e caratterizza la sezione con un label apposito per future cross-reference
\section{Introduzione}\label{sec:intro}
Lorem Ipsum.

\subsection{subIntroduzione}\label{subsec:subintro}
Lorem Ipsum.

\section{Cose a caso}\label{sec:coseacaso}
Ora siamo nella sezione~\ref{sec:coseacaso},
perché non dare comunque una occhiata alla sottosezione~\ref{subsec:subintro}?

Guarda ora l'immagine in Figura~\ref{fig:culo} e la Tabella~\ref{tab:culo}.
Siccome sto facendo cross-reference con tanto di link cliccabile col comando `ref'
non mi devo preoccupare di dove LaTeX mi andrà effettivamente a collocare immagini e
tabelle, in quanto sono consapevole che le collocherà nella migliore posizione possibile
secondo gli standard tipografici.

% Implementazione basic di una figura:
% [!htp] significa: mettimi la figura qui dove dico io (!h), se fallisci
% mettila invece in cima alla pagina (t), se fallisci ancora invece mettila
% in una pagina dedicata di oggetti float quali immagini e tablee (p)
\begin{figure}[!htp]
    % voglio l'immagine al centro della pagina
    \centering
    % voglio l'immagine larga quanto i margini del testo, se la volessi invece
    % grande quanto la metà dei margini dovrei scrivere [width=0.5\textwidth]
    \includegraphics[width=\textwidth]{immagineculo.jpg}
    % introduco poi un caption descrittivo dell'immagine e poi vi collego il label
    % da usare per cross-reference.
    \caption{Questa è una immagine culo.}\label{fig:culo}
\end{figure}

% Implementazione basic di una tabella
\begin{table}[!htp]
    \centering
    % con {lcc} indico che voglio 3 colonne,
    % una con il testo allineato a sinistra (l)
    % due con il testo centrato (c)
    \begin{tabular}{lc}
        \toprule
        Parametro & Valore $[\si{km}]$ & Secondo Valore $[\si{s}]$ \\
        \midrule
        Valore $\alpha$ & $10.1$ & $10.5$ \\
        Valore $\beta$ & $10.1$ & $10.5$ \\
        Valore $\gamma$ & $10.1$ & $10.5$ \\
        \bottomrule
    \end{tabular}
    \caption{Parametri a caso.}\label{tab:culo}
\end{table}

\end{document}
```

## Altre cose utili per LaTeX che possono sfuggire di vista?

* [Il pacchetto physics](http://mirrors.ibiblio.org/CTAN/macros/latex/contrib/physics/physics.pdf), è una libreria secondaria da installare per LaTeX che contiene una tonnellata di utilissimi strumenti e comandi per scrivere matematica da fisici, quali il comando rapido `\vb{}` per fare il grassetto da notazione vettoriale o il comando generico `\pdv` per scrivere in fretta equazioni a derivate parziali. Include inoltre tutta la notazione di Dirac per scrivere di meccanica quantistica.
* [Detexify](http://detexify.kirelabs.org/classify.html), non ricordi il comando per scrivere un simbolo matematico qualsiasi su LaTeX? Disegnalo a mano libera \(o mouse libero\) su questo sito e lascia che l'algoritmo ad apprendimento macchina \(più o meno, usa un sistema a nearest-neighbour\) riconosca che simbolo hai disegnato indicandoti il comando LaTeX corrispondente!
* **BiBLaTeX è una cosa bella!** Se impari a far uso di un database bibliografico automatizzato, costruire le referenze bibliografiche diventa un semplice copia-incolla dall'utilità di citazione automatizzata di Google Scholar \(le virgolette blu sotto al link del paper\) o di qualsiasi altro tasto di citazione automatica di una rivista online! Copiando-incollando la voce di database scritta in formato **Bibtex** in un file di database bibliografico usato all'interno del codice LaTeX, avrai la possibilità di costruire in automatico tutte le voci secondo le proprie preferenze di standard bibliografico. È molto più facile a farsi che a dirsi, si consiglia caldamente la lettura del capitolo su come fare la bibliografia su LaTeX nella dispensa consigliata. È una lettura di mezz'ora che fa risparmiare ore e ore e ore di lavoro inutile.

