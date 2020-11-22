---
title: "Calibrazione Stampante 3D"
excerpt: "Come calibrare la stampante"
author: "Daniel Ruffato"
---
La procedura di calibrazione sia hardware che software della Anycubic i3 mega è un punto cruciale della messa a punto per ottenere ottime stampe.
Per eseguirla è necessario armarsi di moolta pazienza, quindi specialmente se sei alle prime armi preparati una tazza di tè e biscotti (sconsigliata la caffeina durante queste delicate procedure) e prenditi il pomeriggio libero (alla fine converrai che è più il tempo di leggere che non il fare :D ).
	
I seguenti punti ti guideranno nella calibrazione completa della tua Anycubic, ed è suggerito eseguirla di tanto in tanto, quando ti accorgi che la qualità delle stampe sta deteriorando oppure dopo aver smontato parti della struttura per manutenzione od upgrades.

NOTA: A proposito di upgrades, se riscontri eccessive difficoltà nel punto 2 e 3 o ti sembra di star ripetendo le calibrazioni troppo spesso o se magari non hai ancora applicato le mods che ti consentono di diminuire la frequenza delle calibrazioni, ti suggerisco questo articolo, in cui sono visti nel dettaglio tutti quegli upgrade che ti semplificheranno la calibrazione aumentando la qualità delle tue stampe, in special modo consigliata quella degli anti-backlash e degli stepper driver.
	
Passiamo quindi al sodo, ecco riassunti gli 8 punti principali della mia personale procedura:
	
Calibrazione hardware:
1- Pre-livellamento del piatto;
2- Allineamento orizzontale asse Z;
3- Regolazione finecorsa Z;
3.a - Estrusore singolo;
3.b- Doppio estrusore o modifica asse Z unificato;
4- Regolazione di fino del piatto;
	
Calibrazione software:
5- Regolazione E-step (quantità di filo pescata);
6- Regolazione X-Y-Z step (accuratezza dimensionale);
7- Regolazione Oozing e Retraction (evita gocciolamenti);
8- Ottimizzazione di velocità ed accelerazione (parametro jerk incluso);

Punto 1- Pre-livellamento del piatto
Per prima cosa ti dovrai preoccupare di livellare il piatto di stampa rispetto al telaietto nero a cui è aggianciato. Lo dovrai fare utilizzando un calibro (digitale o analogico vanno entrambi benissimo) e misurando la distanza tra piatto e telaietto. Per farlo basta posizionare i becchi del calibro in modo che poggino uno sulla superficie superiore del piatto e l'altro sulla superficie inferiore del telaietto, a "morsa" diciamo. Mi raccomando! Presta attenzione a non scalfire la superficie trattata "Ultrabase" del piatto.
*foto calibro su piatto*
Agendo quindi sulla manopola dovrai cercare di portare la distanza a circa 23mm ma se hai installato 4 molle afermarket la misura può differire. Regolato il primo angolo si passa al suo opposto (a croce) e si effettua la regolazione sempre portandolo alla stessa distanza, e cosi per i restanti due angoli. Fatto ciò il tuo piatto sarà approssimativamente calibrato, non ancora perfettamente, ma quanto basta per il momento.
n.b. se ti venisse il dubbio che il telaietto nero che sorregge il piatto non sia molto dritto è possibile rimediare effettuando la misurazione con una distanza assoluta, cioè poggiando la testa del calibro sulla base della stampante invece che poggiando uno dei due becchi sulla parte inferiore del telaietto. In questo caso la misura consigliata aumenta e non è più 23mm ma 34mm.
*foto calibro sulla base*
Punto 2- Allineamento orizzontale asse Z
Questo è per certo la fase di calibrazione hardware più critica, ed al tempo stesso che si riflette maggiormente sulle stampe se non eseguita come si deve. Farlo nel modo adeguato ti risparmierà un sacco di grattacapi per cui non aver fretta.
L'aggiustamento deve essere effettuato con i motori accesi* ed il carrello al centro dell'asse X, e consiste nel ruotare i due filetti verticali in modo che le torrette si trovino alla stessa altezza e parallele al piatto. In giro si leggono diverse strategie che utilizzano vari punti di riferimento per l'allineamento ma quella vincente e più accurata è una sola, ovvero quella con il riferimento di misura base della stampante --> barra liscia X inferiore.
*foto indicazione riferimenti*
Per misurare la distanza tra questi due punti ci sono sostanzialmente due modi:
§ il primo utilizza ancora il calibro, lo posizioni a fianco ad una delle due torri Z in modo che la testa del calibro poggi nuovamente sulla base della stampante mentre l'altro becco tocchi il punto più basso della barra liscia inferiore dell'asse X. Successivamente ruoti il filetto finchè non ottieni un'altezza di 100mm. Poi ripeti la misurazione sull'altra torre portandola esattamente alla stessa altezza.
*foto calibro su Z*
§ Altro modo mooolto piu rapido ed in un certo senso anche più preciso è quello di utilizzare due "Z Sync Tool".
*foto Z tools*
Nient'altro sono che due blocchetti rettangolari della stessa identica misura, alti 100mm. Esistono in rete dei progetti 3D (stl) pronti da stampare di questi due blocchetti ma supponendo che la tua stampante non sia ancora così precisa, prendi un qualsiasi pezzo solido di circa quell'altezza. L'ideale sarebbe averne due, ma in caso di dubbia lunghezza (è necessaria una precisione del decimo di mm) si può fare anche con uno solo. Posiziona il tool nello stesso modo in cui posizioneresti il calibro, e poi ruota i filetti finché non avverti una piccola pressione della barra sul tool. È molto importante che la pressione sia la stessa da entrambi i lati, in quanto anche un solo scatto corrisponde ad un layer di sfasamento tra gli estremi dell'asse X
*foto Z tools in posizione 1 e 2*
* Il motivo di eseguire la procedura con i motori ON, o almeno quelli dell'asse Z, è appunto il fatto che così facendo essi saranno sempre costretti a posizionarsi in uno degli "scatti" di movimento che possono fare, e non magari a metà via tra due scatti (quando i motori sono spenti). Così non si rischia che al primo comando finiscano casualmente nello scatto "sopra" o "sotto", sballando la calibrazione. Quindi è bene assicurarti che i motori siano accesi dando un comando di spostamento Z qualsiasi prima di seguire questo punto.
Punto 3- Regolazione finecorsa Z;
Bene, a questo punto avrai l'asse X (dove scorre il carrello) perfettamente parallelo al piano ma prima di procedere con l'ultimo step di regolazione di fino del piatto è necessario impostare i finecorsa sulle due torrette Z così che pigiando il tasto Home non rischi di dare delle brutte "testate" sul piatto, rovinando il rivestimento e rischiando di scalibrare tutto.
La procedura da seguire per questo punto è diversa a seconda che tu abbia la stampante nella configurazione originale con un solo estrusore, o che invece tu abbia aggiunto un estrusore, che poi è la stessa da applicare se hai deciso di unificare il pilotaggio dell'asse Z per semplificarti (e non di poco) la calibrazione e mantenerla più a lungo. Ne parliamo in dettaglio in questo articolo.
Tornando ai finecorsa:
*foto finecorsa sx*
*foto finecorsa dx*
3.a - Estrusore singolo
Nella configurazione standard della Anycubic i3 mega ogni motore viaggia da sè, ed è associato al proprio pulsante finecorsa. In questo modo al comando di Home Z ogni motore smette di ruotare nel momento in cui il proprio pulsante di finecorsa è pigiato. Va da sé quindi che per mantenere l'orizzontalità dell'asse, al comando di Home Z entrambi i pulsanti di finecorsa devono cliccare contemporaneamente come fossero uno solo nel preciso momento in cui l'ugello sfiora il piatto.
Prima di procedere con la regolazione vera e propria devi però posizionare il classico foglio bianco sul piatto, e portare il carrello al centro dell'asse X. 
Successivamente premi il pulsante di Home Z facendo scendere le due torri. A questo punto dovrai far caso a due fattori: 
§ L'ugello tocca il foglio? Se si, il foglio dovrà appena appena opporre un minimo di resistenza, non troppa, ed in questo caso l'ugello è alla giusta distanza dal piatto.
§ I finecorsa hanno cliccato perfettamente insieme? Se si, significa che i finecorsa dell'asse Z sono calibrati.
Nel caso in cui uno dei due fattori non sia verificato devi agire sulle viti di finecorsa posizionate in ogni torre nel modo seguente:
§ Se l'ugello NON tocca il foglio, ma i finecorsa hanno cliccato insieme, devi svitare entrambe le viti di finecorsa della stessa quantità
§ Se l'ugello NON tocca il foglio, e i finecorsa non hanno cliccato insieme, devi svitare entrambe le viti di finecorsa, maggiormente quella che ha cliccato in ritardo.
§ Se l'ugello tocca il foglio e i finecorsa hanno cliccato insieme, la procedura è terminata§ Se l'ugello tocca il foglio ma i finecorsa non hanno cliccato insieme devi avvitare leggermente il finecorsa che ha cliccato per primo e svitato quello che ha toccato in ritardo
§ Se l'ugello tocca troppo il foglio ma i finecorsa hanno cliccato insieme devi avvitare i finecorsa della stessa quantità
§ Se l'ugello tocca troppo il foglio e i finecorsa non hanno cliccato insieme, devi avvitare entrambi, maggiormente quello che ha cliccato per primo.
Dopo ogni variazione, prima di pigiare nuovamente il tasto Home Z devi obbligatoriamente ripetere il punto 2!!  Questo perchè essendo i motori indipendenti, quando uno solo dei due smette di girare l'asse perde orizzontalità.
Una volta che l'ugello tocca il foglio (si deve avvertire una piccola resistenza nel tirare il foglio) ed i finecorsa cliccano insieme, la procedura è completa e puoi procedere con l'ultimo step
3.b- Doppio estrusore o modifica asse Z unificato
In questa configurazione i motori dell'asse Z condividono lo stesso driver e si muovono sempre e continuamente insieme. A differenza della 3.a non è necessario allineare nuovamente le torri dopo ogni Home Z perchè entrambi i motori si fermeranno sempre contemporaneamente e non sarà persa l'orizzontlità (un bel vantaggio vero?).
Nel caso tu non abbia rimosso il finecorsa di sinistra ti ricordo che il vero pulsante finecorsa, quello che dice ai motori quando fermarsi, è solo quello di destra mentre il pulsante di sinistra funge solo da "spia" di controllo, quindi non è necessario che entrambi i finecorsa siano cliccati così precisamente come nel caso precedente (un'altra bella comodità eh?).
La procedura inizia quasi allo stesso modo, dopo aver posizionato il foglio bianco sul piatto ed il carrello al centro dell'asse X, si svita di una manciata di giri la vite finecorsa di sinistra, semplicemente perchè se questa fosse malauguratamente più vicina al pulsante della vite di destra, il pulsante potrebbe essere forzato od addirittura sfondato durante la discesa. Dato che la vite di sx per il momento resta molto alzata, avrai bisogno di cliccare due volte a mano il relativo pulsante finecorsa. Se non lo farai semplicemente la stampante non accetterà altri comandi, incluso l'home successivo per migliorare la regolazione. Ora ti basterà pigiare il tasto Home Z ed osservare l'ugello avvicinarsi al piatto:
§ Se l'ugello non tocca il foglio, devi svitare la vite di dx;
§ Se l'ugello tocca il foglio la procedura è completata;
§ Se l'ugello tocca troppo il foglio devi svitare la vite di dx;
A questo punto devi solo riavvitare la vite finecorsa di sinistra finche non giunge a premere con sicurezza il pulsante e puoi procedere con l'ultimo step.
*foto ugello sul foglio*
Punto 4- Regolazione di fino del piatto;
Finalmente all'ultimo estenuante punto di questa calibrazione e con una buona notizia: si stampa! Ebbene si, l'ultimo punto riguarda l'affinazione dell'accoppiamento ugello/piatto e va effettuato in corso d'opera. A quest'ora hai il piatto perfettamente in piano e le barre lisce su cui scorre il carrello perfettamente orizzontali, rimangono solo le manopole del piatto da regolare finemente allo scopo di compensare quelle differenze micrometriche che difficilmente si rilevano con il calibro. Lo dovrai fare con una semplice stampa molto simile ad uno skirt, una volta scaricato questo file lo dovrai aprire nel tuo slicer di fiducia (consigliatissimo Cura ma se non ti senti confidente questo articolo fa al caso tuo) e controllare che nell'anteprima le linee siano molto vicine al bordo del piatto. Se tutto è in regola puoi caricare un qualsiasi filamento (meglio se PLA di colore chiaro*) e far partire la stampa. Man mano che l'ugello traccerà queste linee dovrai far caso a come il filamento si dispone negli angoli, compensandoli ruotando le manopole per avvicinare od allontarare tra loro le linee di filamento depositato:
○ Se le linee sono troppo distanti e non si toccano tra loro, devi svitare la manopola ed avvicinare quell'angolo del piatto;
○ Se le linee si congiungono mantenendo la giunzione evidente, la procedura è completa;
○ Se le linee non sono distinguibili o addirittura la linea è troppo sottile tanto da essere troppo "trasparente" od estrusa a tratti devi avvitare la manopola ed avvicinare quell'angolo del piatto.
*foto linee distanti*
*foto linee giuste*
Finalmente la calibrazione hardware è terminata! Il consiglio finale è sicuramente quello di non allarmarti se non ottieni soddisfacenti risultati alla prima o seconda calibrazione. Via via acquisirai sempre più confidenza con le procedure ed arriverai ad effettuare gli step appena affrontati in non più di 20-30 minuti.
n.b. se durante la stampa di prova ti accorgi che nel tratto rettilineo tra due angoli le linee non mantengono la distanza che hanno negli angoli, non temere. I piatti sono spesso e volentieri ondulati o comunque non perfettamente piani. Il problema si risolve con l'implementazione di un un sensore come il bl-touch o ad ultrasuoni, che trovi nel dettaglio in questo articolo.
