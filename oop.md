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
> Concezione dei sistemi software come una rete di agenti autonomi intelligenti che incapsulano il proprio stato e forniscono *servizi* (esibiscono comportamenti) comunicando con gli altri tramite messaggi, seguendo un design frattale.

E' prima di tutto una visione, un [modo di pensare][objectThinking] che produce una *decomposizione* del sistema molto diversa da quella prodotta secondo il paradigma procedurale.

Possiamo vederla come un'applicazione del concetto di *divide et impera*, ma con la caratteristica che *il problema viene decomposto in parti che hanno la stessa potenza del tutto* (in contrasto con la decomposizione procedurale che divide strutture dati dalle funzioni che vi operano, ottenendo parti che sono più limitate del sistema in cui "vivono"). Questa concezione della progettazione e *struttura* dei sistemi rende quindi possibile il **design frattale**.

Una conseguenza è che *tutto è un oggetto*. Questo è il semplice concetto unificante che sta alla base di tutte le tecniche, meccaniche e caratteristiche che vengono impiegate per realizzare sistemi realmente object-oriented.

Una buona metafora per coglierne l'essenza sono i sistemi biologici (cellule) e le reti di calcolatori (come internet), che hanno entrambe la caratteristica di essere *sistemi complessi* estremamente *scalabili*. In questi sistemi, i componenti base possono essere relativamente semplici ma dalla loro interazione scaturisce un *comportamento emergente* anche estremamente complesso (a volte caotico).

> I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages --[Alan Kay][oop]

> “real computers all the way down (RCATWD)” --[Alan Kay][kayInterview]

Di conseguenza è un approccio di *design* che entra in gioco molto prima della scrittura del codice (quindi al di sopra di mere meccaniche e tecniche di programmazione). I vantaggi principali sono non-funzionali e sono di tipo *strutturale*. Nel [GOOS][goos] si parla di due tipi di qualità relativi al software:

- **Esterna**: il concetto di qualità dal punto di vista degli utenti finali, ovvero se l'applicazione fa ciò che desiderano in modo gradevole, veloce e senza errori.
- **Interna**: la *struttura* sottostante del software, riguarda il codice e come è organizzato. Flessibilità, modularità, resilienza, etc.

Un software per essere *sostenibile* oltre che utilizzabile deve avere entrambi questi tipi di qualità e l'approccio OO aiuta molto a mantenere un'alta qualità interna (per svilupparla unitamente alla qualità esterna esistono approcci come il TDD/BDD).

Lo scopo quindi è *gestire la complessità* dei sistemi software permettendo la realizzazione di applicazioni molto complesse mantenendo caratteristiche di:

- Modularità
- Flessibilità
- Estendibilità
- Riusabilità

> \[with OOP you can create\] protected and interchangeable modules to make highly scalable systems --[Alan Kay][kayInterview]

Secondo [Alan Kay][historySmalltalk], le caratteristiche principali dell'approccio OO sono:

- *Messaging*: gli oggetti comunicano esclusivamente tramite messaggi e non hanno alcun accesso allo stato degli altri oggetti con cui collaborano.
- *Local retention and protection and hiding of state-process*: incapsulamento dello stato e appunto unica comunicazione tramite messaggi senza accesso diretto. L'unica cosa che gli oggetti espongono sono **comportamenti**, non il loro stato interno.
- *Extreme late-binding of all things*: in contrasto con l'approccio ADT, [duck-typing][duckTyping].

Riprendendo quindi la definizione iniziale:

> Concezione dei sistemi software come una rete di agenti autonomi intelligenti che incapsulano il proprio stato e forniscono *servizi* (esibiscono comportamenti) comunicando con gli altri tramite messaggi, seguendo un design frattale.

- Agenti autonomi e intelligenti: oggetti
- In rete che forniscono servizi ad altri oggetti: messaging, extreme late-binding, *loose coupling*
- Incapsulano il proprio stato: data-hiding, encapsulation, *high cohesion*

Quindi il *principio organizzatore* del design che emerge da questa visione sono i *comportamenti* degli oggetti ed i rispettivi *ruoli* che espletano per i propri vicini... TODO(GOOS)

### Tipi di oggetto ###
Tutto è un oggetto, ma ne esistono di due tipi differenti:

- *Identità*: agenti intelligenti per i quali la semantica dell'uguaglianza si basa sulla loro identità (due oggetti della stessa classe e nello stesso stato sono comunque due oggetti diversi, nel *tempo* possono assumere stati diversi).
- *Valore*: tipicamente *immutabile* rappresenta una informazione e si manipola tipicamente con uno stile funzionale. Qui la semantica di uguaglianza si basa appunta sull'informazione che rappresenta (il numero 6, anche se rappresentato da oggetti diversi in memoria ha sempre lo stesso valore.

Purtroppo, a Java manca questa distinzione e (a meno di accrocchi come l'auto-boxing/unboxing), la semantica di uguaglianza si basa sull'identità per ogni tipo di oggetto:

    String a = "hello";
    String b = "hello";
    a == b // -> false

## Appunti ##
Un approccio non-funzionale, *strutturale*.

- **Data abstraction** (bio/net: data hiding/encapsulation/objects & messaging/late-binding), late-binding che permette l'estensibiltà e l'indipendenza dai dettagli implementativi (ovvero un modo per *partizionare* il sistema stile divide-et-impera e rendere NON necessario il comprenderlo tutto). *Ma*, ovvero non tanto orientata agli oggetti quanto alle interazioni tra di essi (*process oriented*). Design frattale. Ogni oggetto come server con un proprio URL ed eventualmente interfaccia/controllo grafico/presentazione ([concezione di Smalltalk][designPrinciplesSmalltalk]). Replicazione della scalabilità di internet e degli organismi viventi. Cenno al modello degli *actors*.
- **Meta-programming**: riflessione, estendibilità del linguaggio e dei suoi costrutti che non sempre risultano adeguati.

Poche realizzazioni per costruire cose complesse con poco materiale (cattedrale vs Partenone).

----

- *comportamento*, non dati e procedure

----

Da [Objects are just objects, aren't they?][justObjects]:

Smalltalk objects: modularity by encapsulation. Modulare nel senso che sia possibile cambiare alcuni componenti/moduli per cambiare il funzionamento del programma senza che il resto del programma stesso ne sia affetto. *Localizzazione delle modifiche* (protezione dalle stesse: OCP).

Separando logica e dati si finisce per ottenere parti meno potenti del tutto. Se invece si decompone un programma (progetta) utilizzando come blocchi costituitivi *oggetti intelligenti che comunicano tramite messaggi che incapsulano i dati ed espongono comportamenti*, si ottiene un sistema modulare e si riesce a gestire meglio la complessità (quindi si possono costruire sistemi più complessità). **Design frattale**.

Esempi: internet, circuiti elettrici, *noi*.

Oggetti scritti in linguaggi diversi (virtual machines).

TDD: ottenere oggetti che hanno il giusto *comportamento*, che poi possono essere fatti comunicare tra loro.

----

Da [GOOS][goos]:

- Coupling: late-binding, *messaging*
- Coesion: encapsulation

Well designed: *behaviour* (organizing principle) is easy to change.

OOP: web of collaborating objects loosely couples and highly cohesive, organized by *responsibilities* (goals, services, roles) NON nouns.

Modularized around *functions* [more likely to change][parnasModules].

System construction/wiring: declarative. Can be *self-healing* (fault-tolerance, flexibility, etc. See "Let it crash philosophy (Erlang) & the actor model).

Message from A object to B object: A has a *goal* that B can carry on. Interfaccia, NON tipo (duck-typing, messaging).

Perchè?

- Interazioni esplicite
- Demeter's Law, encapsulation (of data/state)
- Flessibilità

## Storia ##
## Differenze con l'approccio ADT ##
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

## Linee guida ##
## Esempi ##
### Controllers ###
### PE ###
## Riferimenti ##
- [Dr. Alan Kay on the Meaning of "Object-Oriented Programming"][oop]
- [A to Z of programming languages: Smalltalk-80][kayInterview]: intervista ad Alan Kay
- [The computer revolution hasn't happened yet][computerRevolution] ed il [video](http://video.google.com/videoplay?docid=-2950949730059754521) del relativo talk all'OOPSLA del '97.
- [Design Principles Behind Smalltalk][designPrinciplesSmalltalk]
- [Early History Of Smalltalk][historySmalltalk] (c'è anche una versione [HTML](http://propella.sakura.ne.jp/earlyHistoryST/EarlyHistoryST.html)
- [Objects are just objects, aren't they?][justObjects], Rick DeNatale
- [On Understanding Data Abstraction, Revisited][cook], William R. Cook
- [Growing Object-Oriented Software Guided By Tests][goos], Nat Pryce e Steve Freeman
- [On the Criteria To Be Used in Decomposing Systems into Modules][parnasModules], D.L. Parnas, Carnegie-Mellon University, disponibile anche in formato [html](http://sunnyday.mit.edu/16.355/parnas-criteria.html)
- [Object Thinking][objectThinking], David West
- [Definizione di Duck-Typing][duckTyping], Wikipedia

[kayInterview]: http://www.computerworld.com.au/article/print/352182/z_programming_languages_smalltalk-80
[computerRevolution]: http://blog.moryton.net/2007/12/computer-revolution-hasnt-happened-yet.html
[designPrinciplesSmalltalk]: http://www.cs.virginia.edu/~evans/cs655/readings/smalltalk.html
[historyOOP]: http://programmers.stackexchange.com/a/142330
[justObjects]: http://www.confreaks.com/videos/461-rubyconf2010-objects-are-just-objects-aren-t-they
[cook]: http://www.cs.utexas.edu/~wcook/Drafts/2009/essay.pdf
[historySmalltalk]: http://www.iam.unibe.ch/~ducasse/FreeBooks/SmalltalkHistoryHOPL.pdf
[goos]: http://www.growing-object-oriented-software.com/
[parnasModules]: http://www.cs.umd.edu/class/spring2003/cmsc838p/Design/criteria.pdf
[objectThinking]: http://shop.oreilly.com/product/9780735619654.do
[oop]: http://www.purl.org/stefan_ram/pub/doc_kay_oop_en
[duckTyping]: https://en.wikipedia.org/wiki/Duck_typing
