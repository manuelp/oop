# OOP: You're (probably) doing it wrong #
- **Autore**: Manuel Paccagnella
- **Revisione**: 0.1-SNAPSHOT
- **Data**: dd/MM/yyyy

## Abstract ##
La "programmazione orientata agli oggetti" è il paradigma ad oggi imperante nell'industria e nelle università. Ma c'è un problema: **quello che viene insegnato e che comunemente si intende come OOP, non è OOP**. O almeno, non è coerente con la visione iniziale con la quale è stato concepito l'object-oriented programming. Lo scopo di questo paper/articolo è quello di esaminare la storia dell'OOP e cercare di individuarne la reale essenza e gli eventuali vantaggi che l'uso dell'OOP reale porta nella realizzazione e gestione di sistemi software complessi.

## Struttura ##
Inizialmente cercheremo di dare una definizione della reale OOP, dopodichè esamineremo la storia dell'OOP per capirne il contesto ed il reale significato. 

Nella seconda parte, una volta chiarita la *forma mentis* e l'essenza dell'OOP, esamineremo dei principi (linee guida) che aiutano nella realizzazione di questa visione nel concreto.

Infine, esamineremo alcuni esempi reali di applicazione della programmazione ad oggetti.

## Definizione ##
virtual machines/servers, biological cells only able to communicate through messages

bio/net non-data-procedure

parts with the same power of the whole (fractal design):

> “real computers all the way down (RCATWD)” --[Alan Kay][kayInterview]

- messaging
- local retention and protection and hiding of state-process (encapsulation, no data)
- extreme late-binding of all things (xenoagnosis, only public interfaces, no ADT)

Obiettivo: 

> protected and interchangeable modules to make highly scalable systems --[Alan Kay][kayInterview]

Everything is an object

----

Da [The computer revolution hasn't happened yet][computerRevolution]:

Un modo di pensare, progettare e realizzare sistemi software complessi. Gestione della complessità. Caratteristiche:

- Modularità
- Estensibilità
- Riusabilità

Reale significato e conseguenze, non buzz-words.

Un approccio non-funzionale, *strutturale*.

- **Data abstraction** (bio/net: data hiding/encapsulation/objects & messaging/late-binding), late-binding che permette l'estensibiltà e l'indipendenza dai dettagli implementativi (ovvero un modo per *partizionare* il sistema stile divide-et-impera e rendere NON necessario il comprenderlo tutto). *Ma*, ovvero non tanto orientata agli oggetti quanto alle interazioni tra di essi (*process oriented*). Design frattale. Ogni oggetto come server con un proprio URL ed eventualmente interfaccia/controllo grafico/presentazione ([concezione di Smalltalk][designPrinciplesSmalltalk]). Replicazione della scalabilità di internet e degli organismi viventi. Cenno al modello degli *actors*.
- **Meta-programming**: riflessione, estendibilità del linguaggio e dei suoi costrutti che non sempre risultano adeguati.

Poche realizzazioni per costruire cose complesse con poco materiale (cattedrale vs Partenone).

----

- *comportamento*, non dati e procedure

----

> The problem here is more a perspective/mindset one I think. As far as I understand object thinking, it's all about fractal design and messages between intelligent objects (that are like little virtual machines). The concept of "dumb object" seems to me in contrast with this vision. I don't say that it's absolutely wrong, but IMHO it's wrong in the context of object thinking and design. 

Modo di pensare che produce una *decomposizione* del sistema molto diversa da quella prodotta secondo il paradigma procedurale (cita Object Thinking).

----

Da [Alan Kay][historySmalltalk]: sistemi progettati come **comunità di agenti autonomi che forniscono *comportamenti* (servizi)**, e costituiscono quindi una *simulazione del problema* (e della relativa soluzione).

----

Da [Objects are just objects, aren't they?][justObjects]:

Smalltalk objects: modularity by encapsulation. Modulare nel senso che sia possibile cambiare alcuni componenti/moduli per cambiare il funzionamento del programma senza che il resto del programma stesso ne sia affetto. *Localizzazione delle modifiche* (protezione dalle stesse: OCP).

Separando logica e dati si finisce per ottenere parti meno potenti del tutto. Se invece si decompone un programma (progetta) utilizzando come blocchi costituitivi *oggetti intelligenti che comunicano tramite messaggi che incapsulano i dati ed espongono comportamenti*, si ottiene un sistema modulare e si riesce a gestire meglio la complessità (quindi si possono costruire sistemi più complessità). **Design frattale**.

Esempi: internet, circuiti elettrici, *noi*.

Oggetti scritti in linguaggi diversi (virtual machines).

Definizione di *oggetti* OO secondo [Cook][cook]:

- Objects have a hidden representation, and a reference.
- Interfaces expressed as a dispatch procedure, the compiler doesn't know or need to know representational details.
- This allows free mixture of objects with different representations filling a given 'role'.

La differenza con gli ADT è che di un oggetto si ha il *riferimento* ma non si sa e non si ha bisogno di sapere *nulla* del suo "tipo" nè tantomento della sua rappresentazione interna.

(Java interfaces? Non proprio, c'è ancora il "tipo" di mezzo, che poi in questo senso divernta un *ruolo*).

Metafora:

- ADT. Monarchi che devono condividere una caratteristica (implementazione) comune
- Oggetti. Presidenti, chiunque può esserlo (almeno in teoria) senza dover condividere alcun dettaglio implementativo o ereditare alcunchè (duck-typing). Roles.

In altre parole: *xenoagnosis*.

> To me, the prohibition of inspecting the representation of other objects is one of the defining characteristics of object oriented programming. I term this autognostic principle:
>
>    An object can only access other objects through their public interfaces.
>
> Autognosis means 'self knowledge'. An autognostic object can only have detailed knowledge of itself. All other pbjects are abstract.
>
> The converse is quite useful: any programming model that allows inspection of the representation of more that one abstraction at a time is not object-oriented.

Da notare che il paper in questione non fa menzione di classi o ereditarietà. E' questa nozione di xenoagnosi a tempo di compilazione.

Everything is an object (Java: più o meno). Le interfacce di Java sono ancora tipizzate, si collocano in una gerarchia di tipi.

TDD: ottenere oggetti che hanno il giusto *comportamento*, che poi possono essere fatti comunicare tra loro.

## Storia ##
## Principi ##
## Esempi ##
### Controllers ###
### PE ###
## Riferimenti ##
- [A to Z of programming languages: Smalltalk-80][kayInterview]
- [The computer revolution hasn't happened yet][computerRevolution], il [video](http://video.google.com/videoplay?docid=-2950949730059754521) del relativo talk all'OOPSLA del '97.
- [Design Principles Behind Smalltalk][designPrinciplesSmalltalk]
- [Early History Of Smalltalk][historySmalltalk] (c'è anche una [versione](http://propella.sakura.ne.jp/earlyHistoryST/EarlyHistoryST.html) più semplice da leggere ma senza le figure)
- [Objects are just objects, aren't they?][justObjects]
- [On Understanding Data Abstraction, Revisited][cook] by William R. Cook

[kayInterview]: http://www.computerworld.com.au/article/print/352182/z_programming_languages_smalltalk-80
[computerRevolution]: http://blog.moryton.net/2007/12/computer-revolution-hasnt-happened-yet.html
[designPrinciplesSmalltalk]: http://www.cs.virginia.edu/~evans/cs655/readings/smalltalk.html
[historyOOP]: http://programmers.stackexchange.com/a/142330
[justObjects]: http://www.confreaks.com/videos/461-rubyconf2010-objects-are-just-objects-aren-t-they
[cook]: http://www.cs.utexas.edu/~wcook/Drafts/2009/essay.pdf
