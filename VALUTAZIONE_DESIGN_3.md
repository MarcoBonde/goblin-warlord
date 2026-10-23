# Goblin Warlord — Valutazione di game design 3

> Valutazione indipendente del piano aggiornato e del catalogo [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md). Considera le decisioni già prese: campagna single-player a nodi in tre atti, autobattaglie senza input tattico, party schierato fino a cinque con riserve, progressione specie/job e primo atto previsto per l'Accesso Anticipato. È un'analisi di pre-produzione: le conclusioni sono ipotesi da verificare con un prototipo, non risultati di playtest.

## Sintesi esecutiva

Il progetto ha ora un'identità più leggibile: **un warlord goblin guida una squadra ristretta verso la capitale, prepara formazione e composizione prima degli scontri, osserva l'autobattaglia e trasforma le vittorie in nuove possibilità per l'orda**. La mappa a nodi e la progressione legata ai nemici sono una buona struttura per un roguelite compatto; il catalogo di classi offre una direzione concreta per costruire le prime unità.

Il problema da risolvere non è aggiungere altri contenuti: è dimostrare che **preparare una squadra sia una decisione tattica soddisfacente** quando non si può intervenire durante lo scontro. Per farlo, composizione, posizioni, bersagli e abilità automatiche devono cambiare gli esiti in modo comprensibile. Se questa relazione funziona, classi e percorsi possono ampliare il gioco; se non funziona, un catalogo più grande renderà soltanto più costoso il bilanciamento.

### Giudizio rapido

| Area | Valutazione | Rischio o opportunità principale |
|---|---|---|
| Identità | Buona e riconoscibile | L'armata che apprende dai nemici lega fantasia, ricompense e composizione. |
| Giocabilità | Promettente, da validare prima di produrre contenuti | Senza input tattico, una sconfitta deve essere attribuibile a scelte preparatorie comprensibili. |
| Rigiocabilità | Potenziale medio-alto | Tre warlord, percorsi e classi aiutano solo se generano strategie diverse, non solo partenze numericamente diverse. |
| Level design | Adatto a una produzione contenuta, con vincoli da controllare | La mappa authored favorisce il ritmo, ma incontri distinti e nodi garantiti hanno un costo di contenuto. |
| Classi e abilità | Buona base di ideazione, non ancora un sistema validato | I 28 kit sono un bacino di proposte; non sono una promessa né una misura della varietà effettiva. |
| Monetizzazione | Premium coerente con il concept | L'Accesso Anticipato deve offrire un atto rifinito e rigiocabile, non soltanto una quantità di sistemi. |
| Fattibilità | Realistica solo mantenendo il prototipo piccolo | Specie, job, personaggi persistenti, equipaggiamento, eventi e meta-progressione possono moltiplicare il lavoro. |

## 1. Giocabilità: la preparazione deve bastare

### Il ciclo promettente

La sequenza fondamentale è solida sulla carta:

1. scegliere un nodo sapendo tipologia e difficoltà;
2. leggere le informazioni disponibili sulla minaccia;
3. scegliere e posizionare fino a cinque unità;
4. avviare la battaglia automatica e osservare attacchi e abilità;
5. ricevere conoscenza, risorse o oggetti collegati all'incontro;
6. adattare roster, formazione e percorso successivi.

Il punto di forza è che la battaglia automatica rende la preparazione importante e può contenere i costi rispetto a un action game. Il punto debole potenziale è altrettanto netto: il giocatore può sentirsi spettatore se il risultato è deciso da statistiche nascoste, bersagli imprevedibili o abilità che non si combinano.

### Agency senza comandi durante il combattimento

Il divieto di input tattico durante lo scontro è una decisione chiara e va preservato. La profondità dovrebbe venire da poche leve preparatorie che il giocatore possa capire e modificare:

- chi entra in campo e chi resta in panchina;
- disposizione e vicinanza fra unità;
- ruolo e peculiarità di specie/job;
- oggetti assegnati e scelta di percorso;
- capacità di anticipare la gimmick del boss o la minaccia probabile.

Il piano non definisce un sistema di “ordine di attivazione” da scegliere: le unità attaccano al proprio ritmo e le abilità si attivano in base a cooldown. È importante non introdurre per implicazione turni o sequenze di combo se non saranno una regola effettiva. Il prototipo deve invece mostrare con chiarezza **quale evento attiva un'abilità, come viene scelto il bersaglio e perché quell'effetto è utile**.

### Criticità del kit automatico

Le classi proposte hanno identità interessanti: il Guerriero protegge e attira gli attacchi, il Chierico cura e rianima, il Druido combina controllo e cure condizionali, l'Alchimista reagisce agli effetti di stato. Tuttavia, alcuni kit presuppongono condizioni non ancora definite nel sistema comune: priorità fra bersagli, nemici marcati, effetti cumulabili, distanza e allineamento, evocazioni, interruzioni e stati di pericolo.

Ogni nuova regola aumenta il carico cognitivo e di implementazione. Per il prototipo conviene adottare un contratto uniforme e ridotto:

- ogni abilità indica chiaramente **quando** si attiva;
- ogni bersaglio segue una priorità deterministica o una casualità esplicitamente mostrata;
- ogni stato ha durata, accumulo e interazioni definiti;
- le abilità non hanno bersagli validi? L'interfaccia mostra se il lancio salta, cambia bersaglio o attende;
- attacchi e abilità hanno feedback visivi e un riepilogo che consenta di spiegare l'esito.

La scelta esatta fra tempo reale continuo, intervalli discreti o altra simulazione è ancora da prototipare. Prima di scrivere decine di abilità, si deve decidere la regola del tempo, i cooldown, il reset fra scontri e il trattamento di morte, stordimento e bersaglio non disponibile.

### Chiarezza e controllo di esito

La mappa mostra il tipo e la difficoltà del nodo, non la composizione esatta. Questo preserva sorpresa e pianificazione, ma il giocatore deve ricevere indizi sufficienti per fare scelte sensate. I boss hanno una gimmick anticipata: è un buon esempio del livello di informazione da garantire sulle minacce decisive.

Valutare il combattimento chiedendo ai tester di spiegare **quale scelta preparatoria ha inciso sull'esito**. La sola percentuale di vittorie non basta: una vittoria non compresa e una sconfitta percepita come arbitraria indicano comunque un problema.

## 2. Classi e abilità: un catalogo, non ancora 28 sistemi distinti

Il documento delle classi definisce 28 kit, ciascuno con attacco base, abilità spam, ultimate, passiva e idee di tratti. È una risorsa utile per il team e per la prototipazione, ma non implica che 28 classi vadano implementate nel primo atto.

La varietà percepita non dipenderà dal numero di nomi o abilità. Dipenderà da quanto ciascun kit cambia:

- il bersaglio prioritario;
- il modo di proteggere o curare il party;
- la relazione con posizione e retroguardia;
- la gestione di una risorsa o condizione;
- la sinergia con un'altra unità.

#### Rischi da tenere sotto controllo

- **Regole speciali premature:** evocazioni temporanee, trasferimento di buff, rianimazione, predizione e forme adattive richiedono sistemi comuni che potrebbero superare lo scope del primo prototipo.
- **Differenze solo nominali:** varianti che infliggono danno o applicano un debuff simile possono sembrare classi diverse nel documento, ma giocare allo stesso modo.
- **Troppe eccezioni di targeting:** “nemico più vulnerabile”, “più pericoloso” o “più adatto” richiedono definizioni stabili e leggibili.
- **Ultimate che non si attivano:** con scontri brevi o cooldown lunghi, l'abilità potente può restare inutilizzata e una parte del kit non essere mai percepita.
- **Carico di bilanciamento moltiplicativo:** le interazioni fra specie, job, posizioni, tratti e oggetti vanno limitate; non è sostenibile bilanciare a mano ogni combinazione.
- **Ambiguità di terminologia:** piano e documento alternano “job”, “classe” e “abilità spam”. Stabilire un glossario unico per interfaccia, risorse dati e documentazione.

#### Raccomandazione

Trattare il catalogo come una **banca di design**. Nel prototipo usare i quattro kit già selezionati nel piano — Guerriero, Barbaro, Chierico e Stregone — ma implementare solo le regole necessarie a testarli. Non aggiungere più classi finché i ruoli e il modello automatico non sono leggibili. Per l'Accesso Anticipato, scegliere un roster limitato che copra funzioni distinte, invece di mirare a un numero arbitrario di job.

**Nota editoriale:** il testo introduttivo di [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) dichiara 30 classi, mentre le sezioni di classe presenti sono 28. Conviene correggere il conteggio per mantenere coerenti documento e piano.

## 3. Rigiocabilità e progressione

### Fonti di varietà già previste

- tre warlord con unità e conoscenze iniziali diverse;
- percorsi ramificati e incontri non ripetuti nella stessa campagna;
- specie e job appresi dagli avversari;
- formazione, equipaggiamento e tratti di classe;
- sblocchi persistenti e Hall of Fame.

Queste fonti sono complementari, ma non tutte hanno lo stesso peso. I warlord, per esempio, sono descritti soprattutto come differenze di unità e conoscenze iniziali, con vantaggi moderati. Se le conseguenze si esauriscono dopo i primi nodi, la scelta può diventare cosmetica. Ogni warlord dovrebbe aprire un piano diverso senza rendere una partenza superiore.

La morte di tutti i goblin alla fine della run dà peso alla campagna e rende la Hall of Fame una buona ricompensa commemorativa. Non sostituisce però la rigiocabilità sistemica: un nome e delle statistiche sono un ricordo, non un motivo sufficiente per ripetere l'atto.

### Meta-progressione

Gli sblocchi di classi, tratti, passivi e oggetti possono incoraggiare nuove strategie. Possono anche creare un problema di equilibrio se gli sblocchi sono bonus diretti e le prime run risultano intenzionalmente inferiori. La direzione più sostenibile è sbloccare principalmente **alternative con trade-off** e mantenere le opzioni iniziali in grado di completare la campagna.

Il catalogo contiene molti possibili tratti. Sbloccarli tramite uso di abilità può incentivare a usare una classe, ma va evitato che il giocatore debba ripetere azioni inutili o prolungare gli scontri per “farmare” progressi. Il progresso dovrebbe derivare dall'uso naturale e rendere esplicito quanto manca.

### Ripetizione degli incontri

Il requisito di non ripetere battaglie nella stessa campagna può rendere ogni percorso più fresco. La varietà deve provenire da differenze di composizione, comportamento o regola d'incontro, non soltanto da sprite o numeri diversi. Chiarire la regola di produzione: riutilizzare un'arena o una famiglia di nemici può essere accettabile se l'incontro presenta una decisione distinta; non serve produrre una scena completamente nuova per ogni nodo.

**Domanda di validazione:** dopo una run, il tester sa indicare quale warlord, percorso o composizione vuole provare la volta successiva e quale scelta concreta cambierà?

## 4. Level design: mappa e battaglia

### Mappa di campagna

La mappa authored con bivi è una scelta prudente: consente di controllare ritmo, difficoltà e introduzione delle regole senza costruire una generazione procedurale complessa. Le informazioni limitate sui nodi sostengono la sorpresa, mentre le quantità minime di mercanti, élite e riposi danno forma alla progressione.

Il rischio è che la lista di nodi garantiti diventi una checklist di contenuti anziché un ritmo giocabile. Ogni nodo dovrebbe avere un ruolo chiaro nella condizione del party:

- un élite giustifica il rischio con ricompensa o conoscenza significativa;
- un riposo risolve un problema reale di salute o progressione;
- un mercante crea una scelta di spesa, non un passaggio obbligato;
- un raid/tesoro cambia risorse o apre una possibilità rara;
- un evento offre un trade-off leggibile;
- il boss verifica una preparazione raggiungibile tramite più di un percorso.

Il raid/tesoro è garantito circa a metà per ogni percorso, mentre altri nodi sono garantiti solo sulla mappa complessiva. Comunicare bene questa differenza nella progettazione della mappa e verificare che tutte le rotte siano percorribili, non solo quelle che includono il percorso più favorevole.

### Incontri e boss

Un atto con più percorsi, almeno cinque élite e cinque riposi sulla mappa, due mercanti, raid, eventi e nessuna battaglia ripetuta è un obiettivo produttivo impegnativo. Prima di costruire tutto, disegnare una mappa minima di un atto e contare quanti incontri distinti devono esistere davvero in una singola run e nel catalogo complessivo.

La gimmick anticipata dei boss è una buona promessa di fairness. Deve indicare una minaccia concreta senza rivelare ogni dettaglio o imporre un solo counter. Un boss ben progettato dovrebbe poter essere affrontato da più composizioni, con differenze di rischio o durata.

### Arene laterali

La prospettiva 2D laterale è principalmente una scelta di presentazione finché non cambia targeting o posizionamento. Per l'MVP è sufficiente una scena leggibile con linee e posizioni chiare. Terreno, copertura o ostacoli sono possibili aggiunte future, solo se producono una scelta pre-battaglia osservabile senza introdurre pathfinding e movimento complessi.

## 5. Monetizzazione e accesso anticipato

Il modello **premium a prezzo unico** è coerente con un gioco single-player offline e con una campagna chiusa. Non servono valute premium, loot box, energia, pass stagionali o vendita di potere; introdurli contraddirebbe l'economia della run e aumenterebbe le aspettative operative.

L'Accesso Anticipato al primo atto può funzionare se il prodotto è già una campagna locale soddisfacente: inizio, progressione, boss, vittoria/sconfitta, salvataggi, impostazioni e almeno un motivo concreto per rigiocare. Il fatto che il gioco completo preveda tre atti non giustifica da solo un prezzo; il prezzo va definito solo quando durata e qualità del contenuto disponibile sono misurabili.

Una demo gratuita può essere utile dopo la validazione interna, se mostra il ciclo completo in miniatura e non soltanto una battaglia isolata. Espansioni o DLC sostanziali sono valutazioni future, da non usare come sostituto di un gioco base coerente. Nessuna previsione di ricavi è possibile senza dati su durata, pubblico, qualità e mercato.

## 6. Dubbi di design ancora aperti

### Bloccanti prima di implementare il combattimento esteso

1. **Modello del tempo:** lo scontro è una simulazione continua o a intervalli? Come si confrontano frequenze di attacco e cooldown?
-> Facciamo un cambio rotta, l'autobattler può sempre rimanere, però mettiamo un sistema di combattimento a turni che può essere automatizzato (solo abilità base o opzione anche ultimate). Simile a un Fate Grand Order o giochi per cellulare simili.
Il giocatore può scegliere l'azione del goblin da fargli fare e contro chi, tipo darkest dungeon.
2. **Attivazione dell'abilità:** le abilità spam partono sempre appena il cooldown termina, solo se una condizione è soddisfatta o in base a una priorità?
-> dato che da tempo diventa a turno, le abilità avranno dei cooldown (brevi - 1/2 turni. Ultimate 3/5 turni o anche più) e l'attacco base sarà sempre disponibile.
3. **Ultimate:** si attiva al cooldown anche se non è utile? Il cooldown si resetta all'inizio di ogni battaglia? La durata media degli incontri permette di vederla?
-> se non c'è un target valido per l'abilità, non viene usata. magari troppo forte il chierico che ressurect -> allora facciamo che da uno scudo di squadra, così si può concentrare sulla cura con l'abilità base. se cura extra -> aggiunta allo scudo
4. **Bersagli e fallback:** come si definiscono “più pericoloso”, “più vulnerabile” e “alleato più esposto”? Cosa succede se il bersaglio muore o non è raggiungibile?
-> bersagli. ora il giocatore può scegliere autononamente, a meno che non ci sia una provocazione tipo tank. o l'attacco non abbia abbastanza range. farei i corpo a corpo che possono attaccare con l'attacco base solo quelli in prima linea, mentre i ranged possono attaccare chiunque, tranne se c'è provocazione o simili effetti. Le abilità avranno un range di scelta disponibile per tutti i personaggi. In autobattle saranno scelti secondo un algoritmo di "personalità" dei goblin. 
5. **Stati e controllo:** quali effetti possono accumularsi, essere rimossi o interrompere un'abilità? Quanti stati può leggere comodamente il giocatore?
-> tutti gli effetti sono accumulati sotto o vicino al nome e la barra vita del nemico. come in slay the spire, farei che si accumulano simboli/icone rappresentative che permettono di leggere cosa significano. volendo da un menu di pausa del gioco puoi guardare nel dettaglio i nemici e cosa hanno addosso. 
6. **Sconfitta e personaggi:** quando un goblin cade, può essere rianimato soltanto durante la battaglia? Come si distingue la rianimazione dal recupero tra gli scontri?
-> i goblin caduti sono persi per la run a meno di un evento di resurrezione (che avrà altri vantaggi se non hai nessun goblin da risorgere.) nessuno può resuscitare in partita o rendo troppo essenziale il chierico.
7. **Morte della run:** la campagna termina quando tutto il party è sconfitto, oppure le riserve possono entrare in combattimento o recuperare i superstiti? Il ruolo della panchina va reso inequivocabile.
-> il resto dei goblin in panchina va nel panico e scappa dalla paura, perdi la run e non puoi più continuare. 

### Da definire mentre si costruisce l'atto uno

8. **Visibilità dei nodi:** oltre a tipologia e difficoltà, quali indizi comunica la mappa per preparare senza svelare la composizione?
-> icone, come in slay the spire. magari differenziate per evidenziare le unità principali all'interno del nodo. piccole modifiche come un villaggio con la croce per uno pieno di chierici o una chiesa direttamente. Gli eventi devono essere casuali, quindi quelli solo punti di domanda. 
9. **Conoscenza e creazione:** quali soglie sbloccano unità, quanto tempo intercorre fra soglia e creazione e quale scelta si presenta a roster/panchina pieni?
-> farei soglie di 5-10-15-20 nemici di una certa tipologia per sbloccare o aumentare di livello / tratto una unità. quelle che lasci in panchina "mandi a caccia" e perdi il goblin ma ottieni soldi. 
10. **Warlord:** quali differenze iniziali restano significative dopo i primi incontri senza creare un'opzione dominante?
-> tipologie iniziali di goblin sceglibili. volendo ognuno ha un roaster diverso. Artefatti / oggetti unici per warlord, per dare passive al gameplay in modo da rendere differente ogni run. magari alcuni danno danni bonus ai melee. un altro ai ranged e l'ultimo alla magia e rimaniamo in quel tema. Magari influiscono sulle possiblità di trovare goblin o diminuisocno i requisiti delle soglie per sbloccare o potenziare. 
11. **Specie e job:** quali sono le poche peculiarità specie del primo atto, e come si combinano con i ruoli di classe senza eccezioni per ogni coppia?
-> le specie madri hanno una passiva che semplicemente va a potenziare un tratto del goblin, come gli oggetti. essi avranno delle statistiche tipo forza, destrezza, costituzione, intelligenza, saggezza, carisma e in base a quello che si mettono addosso e alla specie hanno dei bonus. magari alcune specie hanno bonus a una statistica, mentre altre danno bonus tipo rigenerazione passiva di vita ogni turno. altre danno slot equipaggiamento speciale bonus, altre 2 armi, altre danno 1 turno in meno all'uso della ultimate, altre danno la possiblità di equipaggiare 2 armi. quindi sono indipendenti dalla classe e uguali e un vantaggio (non sempre dallo stesso peso) per tutti. tanto non è un gioco multiplayer, ci deve essere bilanciamento con il playtesting, ma va bene che le opzioni siano tutte buone.
12. **Posizioni:** la posizione cambia solo targeting e vicinanza o modifica anche abilità/tratti? Introdurre una regola alla volta.
-> le regole per il targeting per noi, valgono anche per i nemici e puoi vederle in anticipo chi targetteranno loro e una previsione del danno in quel momento (attivo solo in modalità a turni, non automatico per risparmiare calcoli e risorse).  
13. **Danni e cura:** in una run tipo, quanti HP vengono persi per nodo e quanto spesso il giocatore deve scegliere un riposo? I valori indicativi di provviste e accampamento vanno testati contro la durata reale dell'atto.
-> deve essere testato, ma hp persi rimangono persi fino a cure ricevute. da provviste riprendi nel viaggio tra nodo e nodo automaticamente, nei luoghi di riposo ottieni extra.
14. **Incontri unici:** quale variazione rende due battaglie abbastanza diverse da rispettare il requisito senza moltiplicare eccessivamente asset e animazioni?
-> il numero, tipologia e combinazioni di esse differenti. in più i goblin son costretti a certe classi, mentre i nemici posso farli che hanno abilità e comportamenti differenti in ogni incontro particolamente bilanciato apposta, non generato casualemente ogni volta per evitare di essere invincibile. 
15. **Meta-progressione:** quali sblocchi danno alternative e quali potenza? Nessun bonus deve trasformarsi in prerequisito per vincere.
-> le alternative sono appunto oggetti aggiuntivi, di classe o razza. madri differenti sbloccate, classi nuove rispetto a quelle tutorial, armi, armature, speciali, artefatti del warlord, tratti aggiuntivi o alternativi per le classi. 
16. **Scope di classi:** quante classi entrano nel primo atto e quali coprono ruoli necessari? Il resto del catalogo rimane riferimento futuro.
-> Guerriero (armatura, difesa, taunt). Ranger arciere(attacco ranged), Stregone(attacco magico), Chierico(cure).

### Decisioni da rimandare

- prezzi, durata commerciale e previsioni di vendita prima di una build rappresentativa;
- contenuti e date per gli atti due e tre finché non sono finanziati;
- espansioni, DLC o sistemi online;
- terreno e meccaniche d'arena complesse prima che il posizionamento base sia validato.

## 7. Piano di verifica consigliato

### Prova A — Il combattimento automatico comunica le cause?

Preparare una scena con Guerriero, Barbaro, Chierico e Stregone e due composizioni nemiche che richiedano priorità diverse. Non aggiungere ancora meta-progressione, set o effetti ambientali.

**Osservare:** i tester sanno prevedere almeno una conseguenza della formazione? Sanno spiegare perché un'abilità si è attivata e perché ha scelto quel bersaglio? Modificare una sola variabile di preparazione cambia il risultato in modo riconoscibile?

### Prova B — Le classi producono decisioni, non solo animazioni?

Testare ogni kit iniziale in due contesti e una combinazione con un'altra classe. Se una classe non cambia la scelta di formazione, l'ordine naturale degli eventi o la gestione del rischio, semplificare o riprogettare il suo ruolo prima di aggiungere altre classi.

Registrare inoltre: quante ultimate si attivano; abilità senza bersaglio utile; tempi morti; effetti di stato che i tester non notano; durata e velocità desiderata dello scontro.

### Prova C — La mini-campagna genera scelte di percorso?

Costruire una piccola mappa authored che includa recupero, ricompensa di conoscenza, un élite, mercante/evento e boss. Lasciare nascosta la composizione dei nodi normali, ma comunicare tipo e difficoltà secondo il piano.

**Osservare:** i tester scelgono una rotta per un motivo esplicito? La cura persistente produce decisioni senza bloccare l'avanzata? Il boss è leggibile e affrontabile con più di una composizione?

### Segnali di via libera

- i tester attribuiscono vittorie e sconfitte a scelte o regole osservabili;
- cambiare formazione o composizione è una decisione, non una formalità;
- ogni classe del prototipo ha una funzione distinta comprensibile senza consultare una guida;
- i nodi di recupero, rischio e ricompensa hanno valore differente;
- la prima run è completa anche senza sblocchi permanenti;
- dopo aver concluso, il giocatore sa cosa intende provare diversamente nella run successiva.

Non fissare soglie numeriche prima di una baseline: raccogliere osservazioni iniziali e usare i risultati per intervenire sulle regole, non per giustificare l'aggiunta di contenuti.

## 8. Raccomandazioni finali

1. **Validare prima il tempo e le regole dell'autobattaglia.** Sono il sistema portante di tutte le classi.
2. **Mantenere i quattro kit del prototipo come ambito massimo iniziale.** Il catalogo completo è una riserva di idee, non una roadmap di implementazione.
3. **Definire bersagli, cooldown, stati e morte con regole comuni.** Ridurre le eccezioni specifiche di classe finché il nucleo non è stabile.
4. **Misurare l'agency con spiegazioni dei tester.** Una battaglia veloce ma incomprensibile non valida il sistema.
5. **Progettare prima una piccola mappa completa.** Verificare il ritmo dei nodi e il costo reale degli incontri unici prima di rispettare ogni quantità di contenuto prevista.
6. **Usare sblocchi come alternative.** Evitare che classi, tratti o oggetti persistenti diventino grind obbligatorio.
7. **Rendere la prima run vincibile senza progressione meta.** Gli sblocchi devono ampliare la rigiocabilità, non correggere un bilanciamento iniziale punitivo.
8. **Correggere il conteggio del catalogo classi** e uniformare “job/classe” prima di trasferire i contenuti in dati Godot.

### Conclusione

Il progetto aggiornato ha una struttura adatta a una produzione indipendente e un buon gancio tematico. La sua promessa si manterrà solo se il giocatore percepisce che la squadra preparata prima dello scontro è davvero sua: **le decisioni devono essere leggibili, le abilità automatiche coerenti e le conseguenze spiegabili**. Il prossimo investimento dovrebbe quindi essere un prototipo ristretto di combattimento e una mini-campagna, non l'implementazione estesa delle 28 classi o dei tre atti.
