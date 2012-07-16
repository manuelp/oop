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

- Data abstraction (bio/net: data hiding & messaging)
- Meta-programming

## Storia ##
## Principi ##
## Esempi ##
### Controllers ###
### PE ###
## Riferimenti ##
- [A to Z of programming languages: Smalltalk-80][kayInterview]
- [The computer revolution hasn't happened yet][computerRevolution], il [video](http://video.google.com/videoplay?docid=-2950949730059754521) del relativo talk all'OOPSLA del '97.

[kayInterview]: http://www.computerworld.com.au/article/print/352182/z_programming_languages_smalltalk-80
[computerRevolution]: http://blog.moryton.net/2007/12/computer-revolution-hasnt-happened-yet.html
