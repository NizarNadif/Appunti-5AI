# Firewall
Il Firewall indica un processo attivo su un sistema in grado di controllare, a vari livelli, il contenuto dei pacchetti in entrata e in uscita su una o più interfacce di rete al fine di impedire il transito di pacchetti non autorizzati.

---

## **tipologie**

### _personal firewall_
I sistemi firewall possono essere dei programmi software da installare su un host di una rete sicura. Il programma ha lo scopo di proteggere l'host e controlla il traffico che circola sulla sua scheda di rete.

### _firewall perimetrale_
Con firewall perimetrale ci si riferisce a quei tipi di firewall che vengono più comunemente riconosciuti come firewall: quelli installati su  almeno due interfacce di un apparato router, una di queste è connessa ad una rete sicura (_ex. rete privata, anche detta **trust**_) e l'altra ad una rete insicura (_ex. Internet, rete pubblica_).

Queste tipologie di firewall si diramano a loro volta in:

- **firewall hardware**: 
un processo che effettua il controllo nelle interfacce di un apparato hardware con almeno due interfacce di rete.
Anche in questo apparato un'interfaccia deve essere collegata ad una rete trust e l'altra ad una rete sicura; facendo ciò questo apparato hardware svolge anche la funzione di router e può sostituirlo come apparato di (inter)connessione fra una rete privata ed una rete pubblica.

- **application layer firewall**: 
un'applicazione di livello 7 (Application layer: 7o ed ultimo livello ISO/OSI) che opera su più interfacce di rete di una macchina server che agisce da router; questo tipo di firewall può essere integrato con applicazioni di rete che effettuano il controllo della connessione e l'ottimizzazione del traffico.

## **classificazione per livello di controllo**
I firewall si possono classificare, oltre che per tipo di apparato e livello nel quale agiscono, anche in base al tipo di ispezione che effettuano:

### _packet filter_
Funzionalità minima che controlla il traffico a livello IP e ispezione il flag SYN di TCP per intercettare tentativi di connessione.
> qui si agisce sul terzo livello della pila ISO/OSI, quello di rete; effettuare un controllo su questo livello è indispensabile per poter bloccare o permettere il traffico tra sottoreti e/o reti pubbliche.

### _stateful inspection_
Verifica la qualità delle connessioni di tipo TCP controllandone i pacchetti, più nello specifico le loro intestazioni (header)

> qui si agisce sul quarto livello della pila ISO/OSI, quello di trasporto; effettuare un controllo su questo livello è necessario per intercettare il traffico TCP che, apparentemente, appartiene ad una connessione alla quale, nei fatti, non appartiene (tentativo di intrusione).

### _deep inside_
Analizza il traffico dei pacchetti fino al 7o ed ultimo livello della pila ISO/OSI (_Application layer_); nello specifico analizza il corretto uso dei protocolli a livello applicativo e ne ispeziona il contenuto.
In base ad un glossario su un database nel quale sono raccolte le firme dei virus o applicativi d'intrusione più diffusi, questo tipo di processo riesce ad intercettarli.
Dato che questo tipo di funzionalità richiede una notevole capacità prestazionale, questo tipo di processo firewall è solitamente presente su apparati dedicati o firewall a livello applicativo su host dedicati (_ex. proxy server_).

