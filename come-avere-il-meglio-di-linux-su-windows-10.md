---
description: 'Ovvero, come non avere più bisogno di una macchina virtuale'
---

# Come avere il meglio di Linux su Windows 10

Nelle ultime versioni di Windows viene offerta la possibilità di avere sottomano un sottosistema Linux contenuto all'interno del proprio sistema Windows in modo che sia sempre accessibile tramite linea di comando Windows alla semplice esecuzione del comando `bash`. All'esecuzione di tale comando, il percorso sotto il quale ci si trova da terminale `cmd` o `PowerShell` diverrà automaticamente una linea di comando Linux nella quale il percorso originale risulta come montato al pari di un supporto esterno \(e.g. `C:\Users\utente\Desktop` diventerebbe poi `\mnt\c\Users\utente\Desktop`\). La comodità di questa cosa è semplicemente inenarrabile.

## Installare la WSL

Per avere Ubuntu su WSL si deve, in primo luogo, abilitare il `Sottosistema Windows per Linux`. Per farlo, andare su `Pannello di Controllo -> Programmi -> Attiva o Disattiva Funzionalità di Windows` e, dalla lista di funzionalità, attivare `Sottosistema Windows per Linux`. Dopo aver riavviato il computer, il "recipiente" del sottosistema sarà installato e pronto per ospitare una distribuzione Linux di propria preferenza. A questo punto, per installare l'apposita versione di Ubuntu 18.04 LTS, andate sul `Microsoft Store` \(sì, proprio QUEL Microsoft Store, quello delle app Microsoft, quello che non viene mai usato perché, fino ad ora, è sempre stato totalmente inutile\) e cercate la """app""" Ubuntu 18.04 LTS. Installatela e avviatela.

Una volta avviata, vi si aprirà una linea di comando che vi installerà il sistema operativo all'interno del recipiente e vi chiederà poi di configurare un nome utente UNIX e una password \(importantissima\) di sistema UNIX. Fatelo. Una volta fatto, avrete tutto il sistema operativo pronto per essere usato alla semplice chiamata del comando `bash` su linea di comando Windows.

N.B. È possibile che vi verrà impostato in automatico un layout di tastiera Americano, ciò non è buono per nulla e, per cambiarlo nel layout di tastiera in automatico, eseguite il comando da linea di comando Linux on Windows:

```bash
$ sudo dpkg-reconfigure keyboard-configuration
```

N.B. L'utente più all'avanguardia desidererà essere anche in grado di eseguire programmi provvisti di interfaccia grafica, oltre che solo programmi da linea di comando. Per fare ciò sarà necessario installare su Windows una valida implementazione del server grafico X, tale implementazione si chiama [Xming](http://www.straightrunning.com/XmingNotes/) ed è scaricabile da [qui](https://sourceforge.net/projects/xming/files/Xming/6.9.0.31/Xming-6-9-0-31-setup.exe/download), si consiglia anche l'installazione delle librerie standard di font assortiti per avere il campionario completo di Xming da [qui](https://sourceforge.net/projects/xming/files/Xming-fonts/7.7.0.10/Xming-fonts-7-7-0-10-setup.exe/download) \(Tali font sono necessari per la corretta esecuzione della libreria `passe-par-tout` scritta dal Prof.Graziano Servizi\).

Una volta installato e avviato tale server X \(comparirà in basso a destra come icona risultante server attivo presso l'indirizzo `.0`\), è necessario dire alla linea di comando ATTIVA Linux di FARE USO di tale server attivo sul computer `localhost`. Per fare ciò è sufficiente scrivere:

```bash
$ export DISPLAY=:0
```

È possibile automatizzare questa cosa ad ogni avvio della bash inserendo questo script nel file `\home\<iltuonomeutente>\.profile`, per fare ciò è sufficiente usare l'editor `nano` da terminale tramite i comandi:

```bash
# per andare nella propria cartella home
$ cd
# per aprire e poter modificare il file .profile
$ nano .profile
```

Molto facile e molto piacevole. :\)

### Tutto molto bello! Ma io non ho mai usato la linea di comando bash! Cosa posso fare?

La linea di comando è uno strumento estremamente potente ed estremamente sottovalutato.

Per cominciare a saggiarne la potenza, nonché imparare i comandi fondamentali, si consiglia la lettura dei primi capitoli di [questo meraviglioso libro gratuito](http://linuxcommand.org/tlcl.php).

### Con la WSL posso fare tutto tutto tutto come se fosse davvero Linux?

Purtroppo no, ci sono certe limitazioni strutturali che rendono certi task avanzati impossibili da eseguire \(niente di limitante tuttavia per uno che deve fare solo cose base\).

All'utente avanzato si consiglia quindi di tenersi sempre a portata di mano una macchina virtuale completa su VirtualBox o su Hyper-V.

