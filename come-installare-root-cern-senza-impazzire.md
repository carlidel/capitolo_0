---
description: >-
  Perché installare ROOT CERN è ciò che battezza come fisici adulti e
  indipendenti.
---

# Come installare ROOT CERN senza impazzire

Si assume nella presente trattazione che si è installato sul proprio sistema Windows 10 il Windows Subsystem for Linux \(WSL\) con su almeno Ubuntu 18.07 con tanto di supporto server grafico "X" basato sul programma Xming. Tali comandi però sono ovviamente validi \(mutatis mutandis\) su qualsiasi installazione analoga di Ubuntu.

## Affrontare la Bestia

Forza e coraggio. ROOT va affrontato a pieno petto.

In questa guida verrà indicato come avere funzionante la versione **PRECOMPILATA** di ROOT CERN, per il semplice fatto che compilare da zero il codice sorgente di ROOT CERN è un procedimento lungo, complicatissimo, estremamente prono al fallimento disastroso e, soprattutto, **totalmente inutile visto che esiste la versione già compilata pronta per essere piazzata ed installata!**

### **Preparare le Armi**

ROOT CERN è un framework gigantesco in C++ che necessita di tante, tante, TANTE, TANTISSIME librerie esterne per funzionare totalmente. Tutte queste librerie devono essere opportunamente installate dal proprio fedele gestore di pacchetti `apt`.

Ora, la [fonte ufficiale](https://root.cern.ch/build-prerequisites#ubuntu) di ROOT CERN elenca tutta una serie di comandi di installazioni fondamentali per avere il framework funzionante, tuttavia esiste la possibilità che, durante l'utilizzo del framework, compaiano terribili warning ed errori di linking causati da librerie esterne mancanti. Qualora questo succeda, sarà necessario agire sul momento eseguendo al volo ulteriori comandi di installazione con `apt`. Ma andiamo con ordine e cominciamo con l'installare le librerie indicate.

In primo luogo, eseguire i seguenti comandi nel terminale bash WSL:

```bash
sudo apt update
sudo apt upgrade
```

che fa sempre bene al proprio sistema operativo Linux.

Successivamente, installare in blocco questi pacchetti:

```bash
sudo apt install git dpkg-dev cmake g++ gcc binutils \
libx11-dev libxpm-dev libxft-dev libxext-dev
```

e poi, installare in blocco questi pacchetti indicati come "facoltativi":

```bash
sudo apt install gfortran libssl-dev libpcre3-dev \
xlibmesa-glu-dev libglew1.5-dev libftgl-dev \
libmysqlclient-dev libfftw3-dev libcfitsio-dev \
graphviz-dev libavahi-compat-libdnssd-dev \
libldap2-dev python-dev libxml2-dev libkrb5-dev \
libgsl0-dev libqt4-dev
```

e, già che ci siamo, installare anche `libtbb` \(non fate domande, fidatevi\):

```bash
sudo apt install libtbb2 libtbb-dev
```

Un bel po' di roba vero? Tuttavia nonostante tutte queste installazioni assortite può ancora succedere che a ROOT finisca per mancare un qualche file di libreria condivisa al momento della compilazione/esecuzione di un qualche programma avanzato. Ciò inevitabilmente è dovuto al fatto che ROOT è un enorme progetto di analisi fisica e statistica in costante divenire.

Quando questo succede, si ha \(quasi\) sempre un errore nella forma:

```text
hey dude! I was like trying to compile your code named
culoculo.cpp but then I was, like, unable to find a definition
of some random symbols all around the actual ROOT code...
So yes, it was a linking error and in the end it's all because
I was not unable to locate the file <nomedelfile>.so
So... in the end what I'm trying to say is...
<nomedelfile>.so, not such file or directory.
```

Magari non lo dice esattamente così, ma alla fine quello che conta è che nelle righe finali di errore viene indicato il fatto che l'errore è causato da un mancato file con estensione `.so`, che indica proprio un file di libreria condivisa.

Quindi quello che è necessario fare è "semplicemente" chiedere al fido `apt` di installare il pacchetto che contiene quel file, giusto? Giustissimo!!! Come fare quindi? Con uno di questi 2 comandi a scelta!

Si può provare a chiedere di installare direttamente il file `.so` con

```bash
sudo apt-get install <nomedelfile>.so
```

Se non funziona, si può prima cercare quali pacchetti contengono il file `.so` con

```bash
sudo apt-file search <nomedelfile>.so
```

e poi richiedere l'installazione di tali pacchetti con

```bash
sudo apt-get install <Pacchetto1> <Pacchetto2> <...>
```

### Scaricare e Configurare ROOT

Ora che armi e librerie sono affilate e pronte, si può scaricare l'ultima versione precompilata di ROOT e configurare il proprio sistema operativo in modo che sia conscio della sua esistenza.

1. [Scaricare](https://root.cern.ch/downloading-root) l'ultima versione disponibile di ROOT6 precompilata per il proprio sistema operativo \(Ubuntu 18  gcc7.3\).
2. Decomprimere il file appena scaricato dall'archivio `.tar.gz` facendo uso di un gestore di archivi serio come 7Zip. Si otterrà una cartella di nome `root`.
3. Decidere dove collocare la cartella tutta all'interno del proprio sistema Windows10 \(fate come me e collocatela direttamente in `C:\`, che corrisponde a `/mnt/c` nella WSL\)
4. Aprire una bash WSL ed eseguire direttamente i seguenti comandi:

```bash
# Andare nella cartella home del sistema Linux
cd
# Aprire il file .profile con l'editor di testo da terminale 'nano'
nano .profile


# Una volta dentro l'editor, scrivere alla fine del file le righe
source /mnt/c/root/bin/thisroot.csh
export DISPLAY=:0 # se non lo avete già fatto prima...
# Dopodiché, fate CTRL+X per uscire e dite che sì, volete salvare
```

A questo punto, se aprite oltre alla linea di comando WSL anche una istanza di Xming in background, avrete la possibilità di fare partire ROOT CERN scrivendo direttamente `root`. Oltre a questo sarete in grado di compilare il vostro codice con le varie librerie offerte dal framework.

