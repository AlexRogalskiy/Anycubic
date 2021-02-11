---

title: "Calibrazione Stampante 3D"
excerpt: "Come calibrare la stampante"
author: "Daniel Ruffato"

toc: true
toc_label: "Riepilogo contenuti"
toc_icon: "cog"
toc_sticky: true

galleria_Foto calibro su Z:
  - url: /assets/docs/calibrazione/Foto calibro su Z 1.jpg
    image_path: /assets/docs/calibrazione/Foto calibro su Z 1.jpg
    alt: "Foto calibro su Z (1)"
    title: "Foto calibro su Z (1)"
  - url: /assets/docs/calibrazione/Foto calibro su Z 2.jpg
    image_path: /assets/docs/calibrazione/Foto calibro su Z 2.jpg
    alt: "Foto calibro su Z (2)"
    title: "Foto calibro su Z (2)"
    
galleria_Z sync tools:
  - url: /assets/docs/calibrazione/Foto Z tools in posizione 1.jpg
    image_path: /assets/docs/calibrazione/Foto Z tools in posizione 1.jpg
    alt: "Foto Z tools in posizione (1)"
    title: "Foto Z tools in posizione (1)"
  - url: /assets/docs/calibrazione/Foto Z tools in posizione 2.jpg
    image_path: /assets/docs/calibrazione/Foto Z tools in posizione 2.jpg
    alt: "Foto Z tools in posizione (2)"
    title: "Foto Z tools in posizione (2)"
    
galleria_Finecorsa:
  - url: /assets/docs/calibrazione/Foto finecorsa sx.jpg
    image_path: /assets/docs/calibrazione/Foto finecorsa sx.jpg
    alt: "Foto finecorsa sx"
    title: "Foto finecorsa sx"
  - url: /assets/docs/calibrazione/Foto finecorsa dx.jpg
    image_path: /assets/docs/calibrazione/Foto finecorsa dx.jpg
    alt: "Foto finecorsa dx"
    title: "Foto finecorsa dx"
 
---

La procedura di calibrazione sia hardware che software della Anycubic i3 mega è un punto cruciale della messa a punto per ottenere ottime stampe.
Per eseguirla è necessario armarsi di moolta pazienza; quindi specialmente se sei alle prime armi preparati una tazza di tè e biscotti (sconsigliata la caffeina durante queste delicate procedure) e prenditi il pomeriggio libero, alla fine converrai che è più il tempo di leggere che non il fare **:D**

I seguenti punti ti guideranno nella calibrazione completa della tua Anycubic, ed è suggerito eseguirla di tanto in tanto, quando ti accorgi che la qualità delle stampe sta peggiorando oppure dopo aver smontato parti della struttura per manutenzione od upgrades.

**NOTA VELOCE**: A proposito di upgrades, se dovessi riscontrare eccessive difficoltà nel punto 2 e 3 o ti sembra di star ripetendo le calibrazioni troppo spesso, o se magari non hai ancora applicato le "mod" che ti consentono di diminuire la frequenza delle calibrazioni, ti suggerisco [**questi articoli**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega") in cui sono visti nel dettaglio tutti quegli upgrade che ti semplificheranno la calibrazione aumentando la qualità delle tue stampe, in special modo consigliata quella degli anti-backlash e degli stepper driver.


Andiamo quindi al sodo, ecco riassunti i 9 punti della mia personale procedura di calibrazione:

**Calibrazione hardware:**

1. Pre-livellamento del piatto;
2. Allineamento orizzontale torri Z;
3. Regolazione viti finecorsa:
 - Singolo estrusore;
 - Doppio estrusore/modifica asse Z unificato:
4. Regolazione di fino del piatto;
 - Il foglio bianco
 - Il file stl

**Calibrazione software:**

5. Regolazione E-step;
6. Aggiustamento flusso di estrusione;
7. Regolazione X-Y-Z step;
8. Regolazione Oozing e Retraction;
9. Ottimizzazione di velocità ed accelerazione (parametro jerk incluso);

**Avviso di servizio: momentaneamente la guida termina alla fine delle procedure di calibrazione hardware*

# **Punto 1** Pre-livellamento del piatto:

Per prima cosa ti dovrai preoccupare di livellare il piatto di stampa rispetto al telaietto nero a cui è agganciato. Lo dovrai fare utilizzando un calibro (digitale o analogico vanno entrambi benissimo) e misurando la distanza tra piatto e telaietto. Per farlo basta posizionare i becchi del calibro in modo che poggino uno sulla superficie superiore del piatto e l'altro sulla superficie inferiore del telaietto, a "morsa" diciamo. Mi raccomando! Presta attenzione a non scalfire la superficie trattata "Ultrabase" del piatto.

{% include figure image_path="/assets/docs/calibrazione/Foto calibro su piatto.jpg" alt="Foto calibro su piatto" caption="Foto calibro su piatto" %}

Agendo quindi sulla manopola dovrai cercare di portare la distanza a circa 23mm (se hai installato delle molle afermarket la misura può differire). Regolato il primo angolo si passa al suo opposto (a croce) e si effettua la regolazione sempre portandolo alla stessa distanza, e cosi per i restanti due angoli. Fatto ciò il tuo piatto sarà approssimativamente calibrato, non ancora perfettamente, ma quanto basta per il momento.

**n.b.** se ti venisse il dubbio che il telaietto nero che sorregge il piatto non sia molto dritto è possibile rimediare effettuando la misurazione con una distanza assoluta, cioè poggiando la testa del calibro sulla base della stampante invece che poggiando uno dei due becchi sulla parte inferiore del telaietto. In questo caso la misura consigliata aumenta e non è più 23mm ma 34mm.

{% include figure image_path="/assets/docs/calibrazione/Foto calibro sulla base.jpg" alt="Foto calibro sulla base" caption="Foto calibro sulla base" %}


# **Punto 2** Allineamento orizzontale torri Z:

Questo è per certo la fase di calibrazione hardware più critica, ed al tempo stesso che si riflette maggiormente sulle stampe se non eseguita come si deve. Farlo nel modo adeguato ti risparmierà un sacco di grattacapi per cui non aver fretta!

L'aggiustamento deve essere effettuato con i **motori accesi** ed il carrello al **centro del piatto**, e consiste nel ruotare manualmente le due barre filettate verticali dell'asse Z in modo che le torrette si trovino alla stessa altezza e parallele al piatto.
Il motivo di eseguire la procedura con i motori accesi, o almeno quelli dell'asse Z, è il fatto che così facendo essi saranno sempre costretti a posizionarsi in uno degli "scatti" di movimento che possono fare, e non magari a metà via tra due scatti. Così non si rischia che al primo comando di spostamento i motori si posizionino casualmente nello scatto "sopra" o "sotto", falsando la calibrazione. E' quindi bene assicurarti che i motori siano accesi dando un comando di spostamento qualsiasi all'asse Z prima di seguire questo punto.

Come se non fosse una procedura già abbastanza delicata, giro si leggono diverse strategie che utilizzano i più disparati punti di riferimento per l'allineamento delle torri ma quella vincente e più accurata è una sola, ed è ciò che ti propongo: quella con il riferimento di misura base della stampante --> barra liscia X inferiore, come indicato dalla foto sottostante.

{% include figure image_path="/assets/docs/calibrazione/Foto indicazione riferimento.jpg" alt="Foto indicazione riferimento" caption="Foto indicazione riferimento" %}

Per misurare la distanza tra questi due punti ci sono sostanzialmente due modi:

- Il primo utilizza ancora il calibro. Lo posizioni a fianco ad una delle due torri Z in modo che la testa del calibro poggi nuovamente sulla base della stampante mentre l'altro becco tocchi il punto più basso della barra liscia inferiore dell'asse X.
Successivamente ruoti il filetto finchè non ottieni un'altezza di *100 mm* precisi precisi. Poi ripeti la misurazione sull'altra torre portandola esattamente alla stessa altezza. Se hai due calibri puoi utilizzarli contemporaneamente per una maggiore precisione.

{% include gallery id="galleria_Foto calibro su Z" caption="Foto calibro su Z" %}

- Altro modo mooolto piu rapido ed in un certo senso anche più preciso è quello di utilizzare due **Z Sync Tool**.

{% include figure image_path="/assets/docs/calibrazione/Foto Z tools.jpg" alt="Foto Z tools" caption="Foto Z tools" %}

Nient'altro sono che due blocchetti rettangolari della stessa identica misura, alti *80-100 mm*. Esistono in rete dei progetti 3D (stl) pronti da stampare di questi due blocchetti, simili a [**questi**](https://www.thingiverse.com/thing:2768165 "Link thingiverse"), ma supponendo che la tua stampante non sia ancora così precisa, prendi un qualsiasi pezzo solido e non deformabile di circa quell'altezza. L'ideale sarebbe averne due, ma in caso di dubbia lunghezza si può fare anche con uno solo.
Posiziona il tool nello stesso modo in cui posizioneresti il calibro, e poi ruota i filetti finché non avverti una piccola pressione della barra liscia sul tool. È molto importante che **la pressione sia la stessa** da entrambi i lati, in quanto anche un solo scatto corrisponde ad un layer di sfasamento tra gli estremi dell'asse X.

{% include gallery id="galleria_Z sync tools" caption="Z sync tools" %}


# **Punto 3** Regolazione viti finecorsa;

Bene, a questo punto avrai l'asse X dove scorre il carrello perfettamente parallelo al piano. Prima di procedere con l'ultimo step è necessario impostare i finecorsa sulle due torrette Z così da fissare la calibrazione appena fatta, ed anche per evitare che l'ugello rischi di dare delle brutte "testate" sul piatto, rovinando l'Ultrabase e di scalibrando tutto.

La procedura da seguire per questo punto è diversa a seconda che tu abbia la stampante nella configurazione originale con un solo estrusore, o che invece tu abbia aggiunto un estrusore, che poi è la stessa da applicare se hai deciso di unificare il pilotaggio dell'asse Z per semplificarti (e non di poco) questi step di calibrazione, oltre che a mantenerla più a lungo. Ne parliamo in dettaglio in [**quest'altro articolo**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega")

Tornando ai finecorsa:

{% include gallery id="galleria_Finecorsa" caption="Foto viti dei finecorsa" %}


## - **Opzione 1** Estrusore singolo:

Nella configurazione standard della Anycubic i3 mega ogni motore viaggia da sè, ed è associato al proprio pulsante finecorsa.
In questo modo al comando di Home ogni motore smette di ruotare nel momento in cui il proprio pulsante di finecorsa è pigiato. 
Va da sé quindi che per mantenere l'orizzontalità dell'asse, dopo il comando di Home entrambi i pulsanti di finecorsa **devono cliccare contemporaneamente** come fossero uno solo e nel preciso momento in cui l'ugello sfiora il piatto. 

Per far coincidere questi due fattori devi però prima posizionare il classico foglio bianco sul piatto, e portare il carrello al centro del piatto. 
Successivamente premi il pulsante di **Home Z** presente nel menù Tools/Home. A questo punto il carrello scenderà verso il foglio e dovrai far caso a due fattori: 

- L'ugello **tocca** il foglio? Se si, il foglio dovrà opporre appena un minimo di resistenza se lo tiri/spingi, non troppa. In questo caso l'ugello è alla giusta distanza dal piatto.
- I finecorsa hanno cliccato perfettamente insieme? Se si, significa che i finecorsa dell'asse Z sono correttamente calibrati.

Nel caso in cui uno dei due fattori non sia verificato devi agire sulle viti di finecorsa posizionate in ogni torre nel modo seguente:

- Se l'ugello **non tocca** il foglio, ma i finecorsa **hanno cliccato insieme**, devi svitare entrambe le viti di finecorsa della stessa esatta quantità
- Se l'ugello **non tocca** il foglio, e i finecorsa **non hanno cliccato insieme**, devi svitare entrambe le viti di finecorsa, maggiormente quella che ha cliccato in ritardo.
- Se l'ugello **tocca** il foglio e i finecorsa **hanno cliccato insieme**, la procedura è terminata
- Se l'ugello **tocca** il foglio ma i finecorsa **non hanno cliccato insieme** devi avvitare leggermente il finecorsa che ha cliccato per primo e svitato quello che ha toccato in ritardo
- Se l'ugello **tocca troppo** il foglio ma i finecorsa **hanno cliccato insieme** devi avvitare i finecorsa della stessa quantità
- Se l'ugello **tocca troppo** il foglio e i finecorsa **non hanno cliccato insieme**, devi avvitare entrambi, maggiormente quello che ha cliccato per primo.

**MOLTO IMPORTANTE:** Una volta apportata una variazione sui finecorsa, prima di pigiare nuovamente il tasto Home Z devi OBBLIGATORIAMENTE ripetere il punto 2 !! 
Questo perchè i motori essendo indipendenti, nel momento in cui non si fermano contemporaneamente fanno perdere l'orizzontalità alle torri Z.

Si, lo so cosa stai pensando, è una gran scocciatura dover ripetere tutto ogni volta.. La questione può essere ovviata seguendo [**questa guida**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega") che ti spiegherà come unificare e consolidare il movimento delle barre filettate dell'asse Z in soli 60 secondi, cosi che si muovano sempre ESATTAMENTE insieme e della stessa altezza, facendoti evitare un sacco di lavoro!
In alternativa, non ti resta che tornare al punto 2, ripetere l'allineamento, e poi nuovamente fare il punto 3, e cosi a ciclo finchè le viti finecorsa non saranno calibrate.

Una volta che l'ugello tocca il foglio a sufficienza da avvertire una piccola resistenza nel tirarlo ed i finecorsa cliccano insieme, la procedura è completa e puoi procedere con l'ultimo step.


## - **Opzione 2** Doppio estrusore/modifica asse Z unificato:

Questa opzione è riservata a coloro che hanno aggiunto un secondo estrusore alla Anycubic i3 mega, oppure a chi ha seguito [**la nostra guida**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega") su come unificare il movimento dei due filetti dell'asse Z facendo in modo che i motori fossero pilotati dallo stesso driver e si muovano sempre e  insieme allineati (ricordo che questa opzione è prevista dalla scheda madre Trigorilla ma non messa in pratica dalla Anycubic quando ne ha dotato le stampanti). 
A differenza dell'opzione con singolo estrusore non è necessario ripetere il punto 2 dopo ogni comando di Z Home, per allineare nuovamente le torri, dato che entrambi i motori si fermeranno sempre contemporaneamente e non sarà persa l'orizzontlità. Un bel vantaggio vero?

Mi sento di ricordarti che in questa configurazione il **vero** pulsante finecorsa, quello che dice ai motori quando fermarsi, è ora solo quello di destra mentre il pulsante di sinistra funge solo da "*spia*" di controllo. Non è quindi necessario che entrambi i finecorsa siano cliccati così precisamente come nel caso precedente. Un'altra bella comodità eh?

La procedura inizia quasi allo stesso modo, dopo aver posizionato il foglio bianco sul piatto ed il carrello al centro del piatto, la prima cosa da fare è svitare di mezzo centimetro la vite finecorsa di sinistra, quella di controllo. Questo semplicemente perchè se fosse malauguratamente più vicina al pulsante rispetto alla vite di destra, colei che ferma i motori, il pulsante potrebbe essere forzato od addirittura sfondato durante la discesa dell'asse. Per il momento dato che la vite di sinistra per precauzione resta alzata, dovrai tener premuto a mano il relativo pulsante per far capire alla scheda madre che è tutto ok. Se non lo farai semplicemente la stampante non accetterà altri comandi, incluso l'Home Z successivo per migliorare la regolazione. 

Ora ti basterà pigiare il tasto Home Z ed osservare l'ugello avvicinarsi al piatto:
- Se l'ugello **non tocca** il foglio, devi svitare la vite di destra;
- Se l'ugello **tocca** il foglio la procedura è completata;
- Se l'ugello **tocca troppo** il foglio devi avvitare la vite di destra;

A questo punto devi solo riavvitare la vite finecorsa di sinistra finche non giunge a premere con sicurezza il pulsante di sx e puoi procedere con l'ultimo step.

{% include figure image_path="/assets/docs/calibrazione/Foto ugello sul foglio.jpg" alt="Foto ugello sul foglio" caption="Foto ugello sul foglio" %}


# **Punto 4** Regolazione di fino del piatto;

A quest'ora hai il piatto perfettamente in piano e le barre lisce su cui scorre il carrello perfettamente orizzontali, rimangono solo le manopole del piatto da regolare finemente allo scopo di compensare quelle differenze micrometriche che difficilmente si rilevano con il calibro.

Finalmente all'ultimo estenuante punto di questa calibrazione e con una buona notizia: **SI STAMPAA!!** 
Ebbene si, l'ultimo punto riguarda l'affinazione della distanza ugello/piatto e può essere ancora una volta effettuato in due modi, una di queste prevede la stampa di un file particolare, ma andiamo con ordine:

## - **Modo 1** Il foglio bianco:

Il primo modo è molto semplice e rudimentale. Prendi un foglio di carta bianco, lo stesso usato in precedenza per i finecorsa, e dopo aver portato l'ugello in un estremo angolo, lo poni tra ugello e piatto. Non sto neanche qui a spiegarti come agire sulle manopole perchè lo avrai capito da te! (nel dubbio, devi ruotare la manopola corrispondente finchè non avverti una leggera pressione dell'ugello sul foglio e farai appena appena fatica a spostarlo)

## - **Modo 2** Il file stl:

Questo è un modo che prevede che gli aggiustamenti siano fatti durante la stampa. Una volta scaricato [**questo file**](https://www.thingiverse.com/thing:4757875 "Download Bed Leveling STL") lo dovrai aprire nel tuo slicer di fiducia, e dopo aver selezionato il profilo con altezza layer 0.2mm, impostare 7-8 linee di skirt ad una distanza di circa 7-10mm (caldamente consigliato Cura, se non ti senti confidente perchè pensi sia troppo complesso [**questa guida di approccio**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega") fa per te). 
Dopo aver controllato nell'anteprima che le linee siano molto vicine al bordo del piatto, ed aver fatto eventuali ridimensionamenti (in media è necessario ridurre il modello all'85-90% a seconda delle impostazioni), se tutto è in regola puoi caricare un qualsiasi filamento chiaro (meglio se PLA di colore bianco/giallo) e far partire la stampa.

**NOTA BENE:** Non è necessario stampare i quadratini presenti nel file, l'importante sono le linee di skirt! Per cui giunti al termine della stampa dello skirt la stampa fa fermata e se necessario fatta ripartire per ulteriori aggiustamenti (di norma sono necessarie 3-4 stampate).
Man mano che l'ugello traccerà le linee di skirt ondulate dovrai far caso a come il filamento si dispone sugli angoli, compensando di conseguenza andando a ruotare le manopole per avvicinare o allontanare dal piatto la punta dell'ugello, e quindi tra loro le linee di filamento depositato:

- Se le linee sono **troppo distanti** e non si toccano tra loro, devi svitare la manopola ed avvicinare quell'angolo del piatto;
- Se le linee **si congiungono** mantenendo però comunque la giunzione evidente, la procedura è completa;
- Se le linee **non sono distinguibili** o addirittura la linea è troppo sottile tanto da essere troppo trasparente o da venir estrusa a tratti, devi avvitare la manopola ed avvicinare quell'angolo del piatto. Te ne accorgerai anche perchè se interrompi la stampa ed alzi l'ugello vedrai subito una lunga colata di tutto quel materiale che ha tentato di uscire ma che non ha trovato spazio per colpa del piatto troppo vicino che tappava l'ugello.

{% include figure image_path="/assets/docs/calibrazione/Foto linee distanti.jpg" alt="Foto ugello distante dal piatto" caption="Foto ugello distante dal piatto" %}

{% include figure image_path="/assets/docs/calibrazione/Foto linee giuste.jpg" alt="Foto ugello alla giusta distanza" caption="Foto ugello alla giusta distanza" %}

Al termine della calibrazione puoi anche misurare con il calibro lo spessore delle linee tracciate, che dovrebbe corrispondere a 0.2mm

**n.b.** se durante la stampa ti accorgi che nel tratto tra due angoli le linee non mantengono la distanza che hanno, non temere. I piatti sono spesso e volentieri deformati o comunque non perfettamente piani. Il problema si risolve con l'implementazione di un un sensore come il bl-touch o ad ultrasuoni, che trovi affrontati più in dettaglio nell'[**ennesimo articolo**](https://rbonghi.github.io/Anycubic/octoprint/ "Anycubic i3 mega").

Finalmente la calibrazione hardware è terminata!
Un consiglio finale è sicuramente quello di non allarmarti se non ottieni soddisfacenti risultati alla prima o alla seconda calibrazione. Via via acquisirai sempre più confidenza con le procedure ed arriverai ad effettuare gli step appena affrontati in non più di 20-30 minuti.




**Che la stampa sia con voi!**
