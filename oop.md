# OOP: You're (probably) doing it wrong #

## TODO ##
- Rationale OOP (vantaggi)
- design frattale, small virtual machines
- Link a paper sulla storia di smalltalk e dell'OOP
- Mia definizione/summary del reale OOP/object thinking
- Conseguenze dell'object-thinking: object design (esempi)
- Critiche
- Citare [Anti-if campaign](http://www.antiifcampaign.com/)

## historySmalltalk ##
> I just decided to leave inheritance out as a feature in Smalltalk-72, knowing that we could simulate it back using Smalltalk’s LISPlike flexibility. The biggest contributor to these AI ideas was Larry Tesler who used what is now called “slot inheritance” extensively in his various versions of early desktop publishing systems. Nowadays, this would be called a “delegation-style” inheritance scheme.

## oop ##
> I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages

> I wanted to get rid of data.

> At the end of the 60s (I think) Bob Balzer wrote a pretty nifty paper called "Dataless Programming", and shortly thereafter John Reynolds wrote an equally nifty paper "Gedanken" (in 1970 I think) in which he showed that using the lamda expressions the right way would allow data to be abstracted by procedures.

> OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things. It can be done in Smalltalk and in LISP. There are possibly other systems in which this is possible, but I'm not aware of them.

> My math background made me realize that each object could have several algebras associated with it, and there could be families of these, and that these would be very very useful. The term "polymorphism" was imposed much later (I think by Peter Wegner) and it isn't quite valid, since it really comes from the nomenclature of functions, and I wanted quite a bit more than functions. I made up a term "genericity" for dealing with generic behaviors in a quasi-algebraic form.

In realtà ci sono praticamente due concezioni diverse del termine OOP:

> One of the things I should have mentioned is that there were two main paths that were catalysed by Simula. The early one (just by accident) was the bio/net non-data-procedure route that I took. The other one, which came a little later as an object of study was abstract data types, and this got much more play.

> If we look at the whole history, we see that the proto-OOP stuff started with ADT, had a little fork towards what I called "objects" -- that led to Smalltalk, etc.,-- but after the little fork, the CS establishment pretty much did ADT and wanted to stick with the data-procedure paradigm.

Quindi, internet è l'unico esempio reale di object-orientation esistente (e molto di successo anche).

## oopWrongPath ##

> If 'real objects' are RCATWD, then each object could be implemented using the programming language most appropriate for its intrinsic nature, which would give new meaning to the phrase 'polyglot programming.'

>OO as implemented today has gone wrong a lot for the fact that the focus is more on class hierarchies than on messaging among objects. Besides, most of development done with OO languages barely qualify as OO systems. People are using OO languages to create what amount to be badly-written procedural systems.
> 
>So, in a way, OO has gone the wrong way because people to this date still don't know how to proper OOAD. 
- http://www.infoq.com/news/2010/07/objects-smalltalk-erlang#view_58401

## kayInterview ##
> you can simulate data (in what are called "abstract data types"), and this is sometimes useful to do, but it is not the essence in any way of object oriented design

> I did make up this term (and it was a bad choice because it under-emphasized the more important idea of message sending). Part of the idea existed (in several systems). I could see that a more comprehensive basis could be made by going all the way to thinking of efficient whole virtual machines communicating only by messages. This would provide scaling, be a virtual version of what my research community, ARPA-IPTO [The Information Processing Techniques Office at the US Department of Defense's research facility] was starting to do with large scale networking, and also would have some powerful “algebraic” properties (like polymorphism). ... However, I am no big fan of Smalltalk either, even though it compares very favourably with most programming systems today (I don’t like any of them, and I don’t think any of them are suitable for the real programming problems of today, whether for systems or for end-users). 

> I think “real design” in terms of protected and interchangeable modules to make highly scalable systems has not been achieved yet, and is desperately needed.

> To me, one of the nice things about the semantics of real objects is that they are “real computers all the way down (RCATWD)” – this always retains the full ability to represent anything. The old way quickly gets to two things that aren’t computers – data and procedures – and all of a sudden the ability to defer optimizations and particular decisions in favour of behaviours has been lost.
> 
> In other words, always having real objects always retains the ability to simulate anything you want, and to send it around the planet. If you send data 1000 miles you have to send a manual and/or a programmer to make use of it. If you send the needed programs that can deal with the data, then you are sending an object (even if the design is poor).
>
> And RCATWD also provides perfect protection in both directions. We can see this in the hardware model of the Internet (possibly the only real object-oriented system in working order).
>
>You get language extensibility almost for free by simply agreeing on conventions for the message forms.
>
>My thought in the 70s was that the Internet we were all working on alongside personal computing was a really good scalable design, and that we should make a virtual internet of virtual machines that could be cached by the hardware machines. It’s really too bad that this didn’t happen.

Ancora su moduli:

> For most things, I advocate using a dynamic language of very high level and doing a prototype from scratch in order to help clarify and debug the design of a new system – this includes extending the language to provide very expressive forms that fit what is being attempted.
>
>We can think of this as “the meaning” of the system. The development tools should allow any needed optimizations of the meaning to be added separately so that the meaning can be used to test the optimizations (some of which will undoubtedly be adapted from libraries).
>
>In other words, getting the design right – particularly so the actual lifecycle of what is being done can be adapted to future needs – is critical, and pasting something up from an existing library can be treacherous.
>
>The goodness of the module system and how modules are invoked is also critical. For example, can we find the module we need without knowing its name? Do we have something like “semantic typing” so we can find what we “need” – i.e. if the sine function isn’t called “sine” can the system find it for us, etc.?

L'idea di **meta**:

> One of the biggest holes that didn’t get filled in computing is the idea of “meta” and what can be done with it. The ARPA/PARC community was very into this, and a large part of the success of this community had to do with its sensitivity to meta and how it was used in both hardware and software.
>
>“Good meta” means that you can take new paths without feeling huge burdens of legacy code and legacy ideas.
>
>We did a new Smalltalk every two years at PARC, and three quite different designs in eight years – and the meta in the previous systems was used to build the next one. But when Smalltalk-80 came into the regular world of programming, it was treated as a programming language (which it was) rather than a meta-language (which it really was), and very little change happened there after.
>
>Similarly, the hardware we built at PARC was very meta, but what Intel and Motorola etc., were putting into commercial machines could hardly have been less meta. This made it very difficult to do certain important new things efficiently (and this is still the case).

Concetto di "new" e "news":

>It’s largely about the enormous difference between “News” and “New” to human minds. Marketing people really want “News” (= a little difference to perk up attention, but on something completely understandable and incremental). This allows News to be told in a minute or two, yet is interesting to humans. “New” means “invisible” “not immediately comprehensible”, etc.
>
>So “New” is often rejected outright, or is accepted only by denaturing it into “News”. For example, the big deal about computers is their programmability, and the big deal about that is “meta”.


## computerRevolution ##
> I made up the term object-oriented, and I can tell you I did not have C++ in mind.

> In the sixties things were quite mechanical. There's a sense of simple mechanism because computers were as large as this room. The one that Ivan Sutherland did Sketchpad on was the size of this room. It was one of the last computers in the US large enough to have its own roof. It was the building it was in. But the programs were quite small and they had a lot in common with their mathematical antecedents. One way of thinking about the semantics of math that was based on logic, is as interlocking gears. Everything kind of has to fit together, and if it does, and everything is compatible at the end, you get the final turning of the shaft that you want.
>
> An analogy to these programs of the sixties is a dog house. If you take any random boards, nail, and hammer; pound them together and you've got a structure that will stay up. You don't have to know anything, except how to pound a nail to do that. Now, somebody could come along and look at this dog house and say, Wow! If we could just expand that by a factor of a hundred we could make ourselves a cathedral. It's about three feet high. That would give us something thirty stories high, and that would be really impressive. We could get a lot of people in there. The carpenters would set to work blowing this thing up by a factor of a hundred. Now, we all know, being engineers and scientists, that when you blow something up by a factor of a hundred, its mass goes up by a factor of a million, and its strength, which is mostly due to cross sections of things, only goes up by a factor of ten thousand. When you blow something up [by] a factor of a hundred, it gets by a factor of hundred weaker in its ability, and in fact, what will happen to this dog house; it would just collapse into a pile of rubble. Then there are two choices you can have when that happens. The most popular one is to say, Well, that was what we were trying to do all along. [Laughter] Put more garbage on it, plaster it over with limestone, and say, Yes, we were really trying to do pyramids, not gothic cathedrals. That, in fact accounts for much of the structure of modern operating systems today.
>
> Or, you can come up with a new concept, which the people who started getting interested in complex structures many years ago did. They called it architecture. Literally, the designing and building of successful arches. A non-obvious, a non-linear interaction between simple materials to give you non-obvious sinergies, and a fast multiplication of materials. It's quite remarkable to people when I tell them that the amount of material in [unintelligible] cathedral, which is an enormous, physical structure, is less than the amount of material that was put into the Parthenon. The reason is that it's almost all air, and almost all glass. Everything is cunningly organized in a beautiful structure to make the whole [hole/whole] have much more integrity than any of its parts. That's the other way you can go, and part of the message of OOP was, that, as complexity starts becoming more and more important, architecture's always going to dominate material, and in fact, the sad fact, I think, about OOP, is [that] people didn't get interested in architecture because of the beauty of it. They're only starting to get interested in architecture now, when the Internet is forcing everybody to do it. That's pretty pathetic.

> learning, of course, is an act of creation itself, because something happens in you that wasn't there before [...] progress, in a fixed context, is almost always a form of optimization, because if you're actually coming up with something new, it wouldn't have been part of the rules or the context [...] Creative acts, generally, are ones that don't stay in the same context that they're in.

> [...] you have to have something blue to have blue thoughts with. I think this is generally missed in people who specialize to the extent of anything else. When you specialize, you are basically putting yourself into a mental state where optimization is pretty much all you can do. You have to learn lots of different kinds of things in order to have the start of these other contexts.

Di seguito le realizzazioni base

### 1. Data abstraction (cells/servers: data hiding & messaging) ###

> I was in the Air Force in 1961, and I saw it in 1961, and it probably goes back one year before. Back then, they really didn't have operating systems. Air training command had to send tapes of many kinds of records around from Air Force base to Air Force base. There was a question on how can you deal with all of these things that used to be card images, because tape had come in, [there] were starting to be more and more complicated formats, and somebody—almost certainly an enlisted man, because officers didn't program back then—came up with the following idea. This person said, on the third part of the record on this tape we'll put all of the records of this particular type. On the second part—the middle part—we'll put all of the procedures that know how to deal with the formats on this third part of the tape. In the first part we'll put pointers into the procedures, and in fact, let's make the first ten or so pointers standard, like reading and writing fields, and trying to print; let's have a standard vocabulary for the first ten of these, and then we can have idiosyncratic ones later on. All you had to do [to] read a tape back in 1961, was to read the front part of a record—one of these big records—into core storage, and start jumping indirect through the pointers, and the procedures were there.
>
> I really would like you to contrast that with what you have to do with HTML on the Internet. Think about it. HTML on the Internet has gone back to the dark ages because it presupposes that there should be a browser that should understand its formats. This has to be one of the worst ideas since MS-DOS. [...] There's a set of browser wars which are 100 percent irrelevant. They're basically an attempt, either at demonstrating a non-understanding of how to build complex systems, or an even cruder attempt simply to gather territory. I suspect Microsoft is in the latter camp here. You don't need a browser, if you followed what this Staff Sergeant in the Air Force knew how to do in 1961. You just read it in. [...] basically, you want to be able to distribute all of the knowledge of all the things that are there, and in fact, the Internet is starting to move in that direction as people discover ever more complex HTML formats, ever more intractable. This is one of these mistakes that has been recapitulated every generation. It's just simply not the way to do it.

Quindi un modo di attaccare e gestire la complessità. Non è un'idea nuova, l'evoluzione ha già trovato il modo di costruire sistemi immensamente complessi come gli esseri umani: le *cellule che comunicano tra loro in parallelo*. Per esempio, quelle del cervello. 

> The shift in point of view here is from mechanical. This is a problem. If you take things like dog houses, they don't scale by a factor of a hundred very well. If you take things like clocks, they don't scale by a factor of a hundred very well. Take things like cells, they not only scale by factors of a hundred, but by factors of a trillion, and the question is, how do they do it, and how might we adapt this idea for building complex systems.—Okay, this is the simple one. This is the one, by the way, that C++ has still not figured out, though. [Laughter] There is no idea so simple and powerful that you can't get zillions of people to misunderstand it.
>
> You must, must not let the interior of any one of these things to be a factor in the computation of the whole. Okay. This is only part of the story. The cell membrane is there to keep most things out, as much at it is there to keep certain things in.

Non tanto "object-oriented" quanto *process oriented* ([Steve Yegge][kingdomNouns] sarà contento):

> I think our confusion with objects is the problem that in our Western culture, we have a language that has very hard nouns and verbs in it. Our process words stink. It's much easier for us when we think of an object—and I have apologized profusely over the last twenty years for making up the term object-oriented, because as soon as it started to be misapplied, I realized that I should have used a much more process-oriented term for it. The Japanese have an interesting word, which is called ma. Spelled in English, just ma. Ma is the stuff in-between what we call objects. It's the stuff we don't see, because we're focused on the nounness of things rather than the processness of things. Japanese has a more process-feel oriented way of looking at how things relate to each other. You can always tell that by looking at the size of [the] word it takes to express something that is important. Ma is very short.

Quindi eccoci ai *messaggi*, il secondo principio oltre all'*information hiding*.

> once you have encapsulated, in such a way that there is an interface between the inside and the outside, it is possible to make an object act like anything.

Ecco quindi l'errore della concezione mainstream dell'OOP e di linguaggi come Java e C++, ovvero "nascondere" ciò che è veramente nuovo di questa concezione del software, ovvero il *design frattale*:

> The reason is simply this, that what you have encapsulated is a computer. You have done a powerful thing in computer science, which is to take the powerful thing you're working on, and not lose it by partitioning up your design space. This is the bug in data and procedure languages. I think this is the most pernicious thing about languages a lot like C++ and Java, is that they think they're helping the programmer by looking as much like the old thing as possible, but in fact they are hurting the programmer terribly by making it difficult for the programmer to understand what's really powerful about this new metaphor. People who were doing time-sharing systems had already figured this out as well. Butler Lampson's thesis in 1965 was about what you want to give a person on a time-sharing system, is something that is now called a virtual machine, which is not the same as what the Java VM is, but something that is as much like the physical computer as possible, but give one separately to everybody. 

URL per ogni oggetto e ancora su oggetti come *server*:

> Here's one that it is amazing to me that we haven't seen more of. For instance, one of the more amazing things to me, of people who have been trying to put OOP on the Internet, is that I do not—and I am hoping someone will come up afterwards and tell me of an exception to this—but I do not know of anybody yet, who has realized that, at the very least, every object should have a URL, because, what the heck are they if they aren't these things, and I believe that every object on the Internet should have an IP [address], because that represents, much better, what the actual abstractions are of physical hardware to the bits. So this is an early insight that objects basically are like servers. This notion of polymorphism, which used to be called generic procedures is a way of thinking about classes of these servers. Everybody knows about that.

Sulla scalabilità di questo modello (internet):

> The ARPNANET, of course, became the Internet, and from the time it started running—just around 1969 or so—to this day, it has expanded by about a factor of a hundred million. That's pretty good. Eight orders of magnitude. [...] This is a system that has expanded by a hundred million, has changed every atom and every bit, and has never had to stop. That is the metaphor we absolutely must apply to what we think are smaller things.

### 2. Meta-programming ###
> Here's the other big source. Certainly the greatest, single language along with Simula of the sixties, I think. One with as many profound or more profound insights—LISP. On page thirteen of this book that was published in 1962, there's a half page of code which is the reflective model of LISP written in itself. All the important details of LISP semantics and the guidelines for how to make a LISP interpreter are in that half page. It is this aspect—this meta-reflective aspect—that to me, is the saddest thing about what is happening with Java. [...] how do they hope to survive all of the changes, modifications, adaptations, and interoperability requirements without a meta-system. Without even, for instance, being able to load new things in while you're running. The fact that people adopted this as some great hope is probably the most distressing thing to me, personally, as I said, since MS-DOS. I mean, it represents a real failure of people to understand what the larger picture is, and is going to be. 

> This notion of meta-programming. Lots of different ways of looking at it. One of them is that, any particular implementation is making pragmatic choices, and these pragmatic choices are likely not to be able to cover all of the cases, at the level of efficiency, and even at the level of richness required. Of course, this is standard OOP lore. This is why we encapsulate. We need to hide our messes. We need to have different ways of dealing with the same concepts in a way that does not distract the programmer.

> you can also apply it to the building of the language itself. The more the language can see its own structures, the more liberated you can be from the tyranny of a single implementation. I think this is one of the most critical things that very few people are worrying about in a practical form. 

In pratica, il problema che si pone Alan è l'interoperabilità tra tutti i diversi sistemi ad oggetti che sono simili nei principi ma differenti nei dettagli pragmatici. Ed ecco quindi una realizzazione riguardo internet e gli "object systems", un *universal interface language* (che non è un linguaggio di programmazione in sè e per sè.

> If you think about what a URL actually is, and you think of what an HTTP message actually is, and if you think of what an object actually is, and if you think of what an object oriented pointer actually is, I think it should be pretty clear that any object-oriented language can internalize its own local pointers to any object in the world, regardless of where it was made. That's the whole point of not being able to see inside. A semantic interoperability is possible almost immediately by simply taking that stance. This is gonna change, really everything. [...] This is going to lead to a universal interface language, which is not a programming language per se. It's more like a prototyping language that allows an interchange of deep information about what objects think they can do. It allows objects to make experiments with other objects in a safe way to see how they respond to various messages. This is going to be a critical thing to automate in the next ten years.

Sulla storia:

> What happened in most of the world, starting in the seventies, was abstract data types, which is really staying with an assignment centered way of thinking about programming.

Usare il C++ per efficienza? 

> Oh, let's not do it in Smalltalk, that's too slow! Let me tell you, there's nothing more inefficient than spending ten years on an operating system that never works.

Ancora sulla corruzione di idee nuove che non vengono capite, poi corrotte e adottate come "religioni":

> Let's take our pink plane, and we can also use this McLuhan quote—my favourite McLuhan quote—"I don't know who discovered water, but it wasn't a fish." He meant us as the fish, and he meant water as our belief structures—as our context. If you had to pick one cause, of both particular difficulty in our field, and also a general difficulty in the human race, it's taking single points of you and committing to them like they're religions. This happend with Smalltalk. There's a wonderful quote by Schopenhauer, a German philosopher of the nineteenth century, who said, "Every idea goes through three stages. First, it is denounced as the work of madmen."—This is what Swift called "A Confederacy of Dunces"—and then later, it's remarked as being totally obvious the whole time, and then the last stage is when the original denouncers claim to have invented it.

Smalltalk ha smesso di essere buono quando è uscito da Xerox PARC ed è stato "standardizzato":

> To me, the most distressing thing that happened to Smalltalk when it came out of Xerox PARC, was, for many respects and purposes it quit changing. I can tell you, at Xerox PARC there are four major versions—completely different versions of the language—over about a ten year period, and many dozens and dozens of significant releases within those different versions. I think one of the things we liked the most about Smalltalk was not what it could do, but the fact that it was such a good vehicle for bootstrapping the next set of ideas we had about how to do systems building. That, for all intents and purposes—when Smalltalk went commercial—ceased. [...] What they missed was, to me, the deepest thing I would like to communicate with you today, and that is we don't know how to design systems yet. Let's not make what we don't know into a religion, for God's sake. What we need to do is to constantly think and think and think about what's important. We have to have our systems let us get to the next levels of abstraction as we come to them. The thing I am most proud of about Smalltalk, pretty much the only thing, from my standpoint, that I am proud of, is that it has been so good at getting rid of previous versions of itself, until it came out into this world.

Sulla nascita di Squeak:

> One of the reasons we got involved in doing Smalltalk again, after, for me, it was sixteen years of not working on programming languages. A couple of years ago we started this project called Squeak, which is simply not an attempt to give the world a free Smalltalk, but an attempt to give the world a bootstrapping mechanism for something much better than Smalltalk, and when you fool around with Squeak, please, please, think of it from that standpoint. Think of how you can obsolete the damn thing by using its own mechanisms for getting the next version of itself. So look for the blue thoughts!

## Matteo Vaccari ##
Anche in Italia abbiamo qualche persona che pensa e scrive riguardo l'OOP reale.

### A revelation insiede another revelation ###
http://matteo.vaccari.name/blog/archives/675

Sul libro "Object Thinking":

> One of the main things I got out of it is that Object Thinking is a revolutionary break with respect to established software engineering practice. Another thing is that the view of objects as Abstract Data Type is basically the establishment’s way to dilute and incorporate the grand new thing and make it look like a variation of the old thing.

[Objects are good but not for domain modeling](http://c2.com/cgi/wiki?OopNotForDomainModeling)?

> the old OOP books all said things like “take the description of your problem, underline the nouns in the description, and these are your candidate objects”. I used to think that this is a silly exercise! And I’m not alone.

## Sommario ##
- Tre caratteristiche
- enfasi su messaging (virtual machines)
- *comportamento*, non dati e procedure

Me stesso medesimo: 

> The problem here is more a perspective/mindset one I think. As far as I understand object thinking, it's all about fractal design and messages between intelligent objects (that are like little virtual machines). The concept of "dumb object" seems to me in contrast with this vision. I don't say that it's absolutely wrong, but IMHO it's wrong in the context of object thinking and design. 

Modo di pensare che produce una *decomposizione* del sistema molto diversa da quella prodotta secondo il paradigma procedurale (cita Object Thinking).

Da [Alan Kay][historySmalltalk]:

> This is probably a good place to comment on the difference between what we thought of as OOP-style and the superficial encapsulation called “abstract data types” that was just starting to be investigated in academic circles. … To put it mildly, we were quite amazed at this, since to us, what Simula had whispered was something much stronger than simply reimplementing a weak and ad hoc idea. What I got from Simula was that you could now replace bindings and assignment with goals. … the objects should be presented as sites of higher level behaviors more appropriate for use as dynamic components.

> OOP is about modeling the problem with a community of autonomous agents. The way to make OOP shine is to build a simulation of the problem. And I remembered the thrill I once had when I first read about OOP. About imagining these little software robots going about their business inside my programs. An object that can “think” for itself and has a behaviour. Now *that* is what OOP is about!

## kayConversation ##
Chi è Alan Kay?

>Kay was one of the founders of the Xerox Palo Alto Research Center (PARC), where he led one of several groups that together developed modern workstations (and the forerunners of the Macintosh), Smalltalk, the overlapping window interface, desktop publishing, the Ethernet, laser printing, and network client-servers.
>
> Prior to his work at PARC, Kay earned a Ph.D. in 1969 from the University of Utah, where he designed a graphical object-oriented personal computer and was a member of the research team that developed pioneering 3-D graphics work for the Advanced Research Projects Agency (ARPA). Kay was also a “slight participant” in the original design of the ARPANet, which later became the Internet. He holds undergraduate degrees in mathematics and molecular biology from the University of Colorado. After leaving Xerox PARC, Kay went on to become chief scientist of Atari, a Fellow of Apple Computer, and vice president of research and development at The Walt Disney Company.
>
>Today he is Senior Fellow at Hewlett-Packard Labs and president of Viewpoints Research Institute, a nonprofit organization whose goal is to change how children are educated by creating a sample curriculum with supporting media for teaching math and science. This curriculum will use Squeak as its media, and will be highly interactive and constructive. Kay’s deep interests in children and education have been the catalysts for many of his ideas over the years.
>
>In addition to winning the Turing Award, Kay recently received the Draper Prize from the National Academy of Engineering and the Kyoto Prize in Advanced Technology, awarded every four years by the Inamori Foundation.

Come mai Smalltalk e la concezione dell'OOP non hanno preso piede? Probabilmente per colpa della commercializzazione.

> You could think of it as putting a low-pass filter on some of the good ideas from the ’60s and ’70s, as computing spread out much, much faster than educating unsophisticated people can happen. In the last 25 years or so, we actually got something like a pop culture, similar to what happened when television came on the scene and some of its inventors thought it would be a way of getting Shakespeare to the masses. But they forgot that you have to be more sophisticated and have more perspective to understand Shakespeare. What television was able to do was to capture people as they were.

Sull'utilità del late-binding:

> It’s not that people are completely stupid, but if there’s a big idea and you have deadlines and you have expedience and you have competitors, very likely what you’ll do is take a low-pass filter on that idea and implement one part of it and miss what has to be done next. This happens over and over again. If you’re using early-binding languages as most people do, rather than late-binding languages, then you really start getting locked in to stuff that you’ve already done. You can’t reformulate things that easily.

## Storia ##
Perchè allora è diventata mainstream un'idea "corrotta" della programmazione orientata ad oggetti? Una possibile spiegazione la dà [Ralph Johnson][oopWrongPath]:

> One of the things that always happen when you get an idea and it comes out and it's too radical for most people. Most people don't adopt the whole thing, they take a piece of it and then you get this approximation.

## Riferimenti ##
- [Dr. Alan Kay on the Meaning of "Object-Oriented Programming"][oop]
- [Uniform Access Principle][uap], vedere anche la [pagina](https://en.wikipedia.org/wiki/Uniform_access_principle) di Wikipedia corrispondente
- [Object Oriented Programming: The Wrong Path?](http://www.infoq.com/news/2010/07/objects-smalltalk-erlang)
- [A to Z of programming languages: Smalltalk-80][kayInterview]
- [The computer revolution hasn't happened yet][computerRevolution], il [video](http://video.google.com/videoplay?docid=-2950949730059754521) del relativo talk all'OOPSLA del '97.
- [Execution in the kingdom of nouns](http://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html)
- [A conversation with Alan Kay][kayConversation]

### Da riferire ###
- [Storia del termine OOP][historyOOP]
- [A Laboratory For Teaching Object-Oriented Thinking][laboratoryOOP]
- ["On the Criteria To Be Used in Decomposing Systems into Modules" by D.L. Parnas][modulesParnas]
- [Early History Of Smalltalk][historySmalltalk] (c'è anche una [versione](http://propella.sakura.ne.jp/earlyHistoryST/EarlyHistoryST.html) più semplice da leggere ma senza le figure)
- [Design Principles Behind Smalltalk][designPrinciplesSmalltalk]
- [Problems With Existing OOP Evidence][problemsOOP]
- [L'arte perduta di pensare ad oggetti](http://matteo.vaccari.name/blog/archives/723), c'è anche il [video][OOPVaccari].

- http://www.bonkersworld.net/object-world/
- [Name Objects after things, not actions!](http://matteo.vaccari.name/blog/archives/743)
- [Classess without faces](http://matteo.vaccari.name/blog/archives/700) Esempio nomenclatura
- [On the folly of representing a first name with a String](http://matteo.vaccari.name/blog/archives/685) Esempio design form
- [Objects are just objects, aren't they?](http://www.confreaks.com/videos/461-rubyconf2010-objects-are-just-objects-aren-t-they)

[oop]: http://www.purl.org/stefan_ram/pub/doc_kay_oop_en
[uap]: martinfowler.com/bliki/UniformAccessPrinciple.html
[oopWrongPath]: http://www.infoq.com/news/2010/07/objects-smalltalk-erlang
[kayInterview]: http://www.computerworld.com.au/article/print/352182/z_programming_languages_smalltalk-80
[historyOOP]: http://programmers.stackexchange.com/a/142330
[computerRevolution]: http://blog.moryton.net/2007/12/computer-revolution-hasnt-happened-yet.html
[kingdomNouns]: http://steve-yegge.blogspot.it/2006/03/execution-in-kingdom-of-nouns.html
[kayConversation]: http://queue.acm.org/detail.cfm?id=1039523

[laboratoryOOP]: http://c2.com/doc/oopsla89/paper.html
[modulesParnas]: http://sunnyday.mit.edu/16.355/parnas-criteria.html
[historySmalltalk]: http://www.iam.unibe.ch/~ducasse/FreeBooks/SmalltalkHistoryHOPL.pdf
[designPrinciplesSmalltalk]: http://www.cs.virginia.edu/~evans/cs655/readings/smalltalk.html
[problemsOOP]: http://c2.com/cgi/wiki?ProblemsWithExistingOopEvidence
[OOPVaccari]: https://www.youtube.com/watch?v=jO6Z3wOdfWc
