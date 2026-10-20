# Goblin Warlord — Valutazione di game design 2

> Seconda valutazione, basata sulle decisioni aggiunte al piano di progetto: campagna in tre atti verso la capitale, autobattaglie senza input durante lo scontro, party massimo di cinque, ricompense di specie/job, discendenza materna, equipaggiamento, sblocchi persistenti e primo atto previsto per l'Accesso Anticipato. È una revisione di pre-produzione, non un esito di playtest.

## Sintesi esecutiva

La versione attuale ha una direzione più concreta e riconoscibile rispetto al concept iniziale. Il suo nucleo è:

> **Scegliere il percorso, preparare un piccolo gruppo di goblin e l'ordine delle loro abilità, osservare la battaglia automatica, imparare dai nemici sconfitti e adattare l'orda per proseguire verso la capitale.**

Questo nucleo può sostenere un roguelite strategico, ma presenta una sfida di design precisa: **tutta l'agency tattica si concentra prima della battaglia**. Se l'ordine delle abilità e la composizione non producono effetti visibili e spiegabili, il giocatore non avrà modo di correggere una decisione durante lo scontro. Il prototipo deve quindi provare presto che preparare l'ordine è soddisfacente, leggibile e abbastanza profondo da sostenere molte battaglie.

Il secondo rischio è lo scope: specie, job, personaggi individuali, discendenza, oggetti, talenti, warlord, risorse, eventi, atti e sblocchi persistenti sono molti sistemi per un progetto autofinanziato e inizialmente basato su placeholder. L'Accesso Anticipato non riduce questo rischio da solo: il primo atto deve costituire un prodotto coerente, non un prototipo pubblicato con la promessa di completarlo in seguito.

### Valutazione rapida

| Area | Giudizio | Rischio principale |
|---|---|---|
| Identità | Buona | L'idea distintiva è l'orda che impara dai nemici e li riproduce come nuove opzioni di squadra. |
| Giocabilità | Da validare presto | Senza input durante lo scontro, l'ordine del party deve essere una decisione tattica forte, non una formalità. |
| Rigiocabilità | Potenziale medio-alto | Dipende da percorsi, ricompense e build realmente diversi, non dal solo sblocco di bonus permanenti. |
| Level design | Adatto a produzione piccola | Mappa a nodi costruita a mano; i tipi di nodo devono cambiare lo stato dell'armata o offrire trade-off. |
| Fattibilità | Sostenibile solo con scope stretto | La moltiplicazione specie × job × oggetti × abilità × animazioni può diventare ingestibile. |
| Monetizzazione | Premium single-player plausibile | In Accesso Anticipato, atto uno e comunicazione dei contenuti devono giustificare l'acquisto già al lancio. |

## 1. Giocabilità: il giocatore prepara, poi osserva

### Il vantaggio della scelta fatta prima dello scontro

Un autobattler senza interventi può funzionare se la battaglia è il risultato leggibile di un piano. Il giocatore:

1. osserva gli indizi sul prossimo nodo e sul tipo di nemico;
2. sceglie quali membri portare;
3. configura job, tre slot oggetto e ordine delle unità;
4. avvia lo scontro e verifica se la sequenza prevista funziona;
5. usa il risultato per adattare il party e il percorso.

È una struttura coerente con una campagna a nodi e può essere più facile da produrre di un combattimento in tempo reale. Offre inoltre spazio per animazioni automatiche spettacolari senza dover costruire controlli d'azione precisi.

### Rischio centrale: ordine delle abilità poco significativo

Il piano dice che l'ordine dei personaggi determina l'ordine di attivazione delle abilità. Questo è un hook promettente, ma non basta che cambiare l'ordine cambi la cronologia: deve cambiare **l'esito strategico**.

Un buon esempio di relazione leggibile:

- un goblin applica vulnerabilità;
- un secondo sfrutta la vulnerabilità;
- un terzo protegge o potenzia il gruppo prima della risposta nemica.

Se invece ogni personaggio attacca una volta in ordine, ma le abilità non interagiscono o i bersagli non sono prevedibili, il giocatore non avrà motivo di riordinare il party. Se l'ordine è imposto per l'intero scontro, le abilità devono essere utili in più stati di battaglia, non solo alla prima attivazione.

**Raccomandazione:** nel prototipo creare tre abilità che interagiscono chiaramente e due nemici con priorità o debolezze diverse. Usare lo stesso party in due ordini differenti e verificare che il risultato cambi per una causa che il giocatore sa nominare.

### Decisioni da specificare per la risoluzione del combattimento

Prima di bilanciare decine di unità, il prototipo deve definire:

- Il party agisce tutto prima dei nemici, oppure le unità si alternano?
- L'ordine del party vale una sola volta all'inizio o si ripete a ogni round?
- Un'abilità si attiva automaticamente a ogni turno, una volta per battaglia o quando si verifica una condizione?
- Quando una unità è sconfitta, l'ordine avanza, si ricalcola o l'abilità successiva cambia bersaglio?
- Come vengono selezionati i bersagli: prima linea, nemico con meno salute, bersaglio casuale o priorità specifica del job?
- Il giocatore conosce la composizione nemica prima di premere **Start battaglia**, oppure solo il tipo di nodo?
- Si può ripetere una battaglia persa con la stessa preparazione? Una sconfitta dovrebbe essere spiegabile e non apparire come un esito casuale opaco.

Questi sono dettagli di regola, non nuovi sistemi: sono il contratto fondamentale del combattimento automatico.

### Rendere osservabile una battaglia senza microgestione

Non serve dare comandi al giocatore durante lo scontro, ma occorre renderlo un evento comprensibile:

- mostrare l'ordine delle attivazioni e a chi si rivolge ogni abilità;
- rendere visibili buff, debuff, difesa e salute senza aprire pannelli complessi;
- indicare con brevi feedback perché un'abilità ha avuto effetto o non ha trovato un bersaglio;
- permettere una durata contenuta e opzioni di velocità/skip della risoluzione, se i playtest mostrano che assistere a ogni animazione rallenta il ritmo;
- alla fine, riepilogare i danni, le unità perse e la causa principale del risultato.

Velocità e skip non alterano il divieto di intervento tattico: sono controlli di presentazione e vanno testati con utenti.

## 2. Party, identità dei goblin e progressione

### Cinque personaggi: un limite promettente, ma da rendere coerente

Un massimo di cinque crea un party gestibile e distingue il gioco dalla gestione di un esercito enorme. La partenza con uno o due goblin in base al warlord offre identità iniziali differenti.

Resta da decidere se “roster massimo cinque” significa:

- cinque personaggi totali posseduti durante la run, che combattono tutti; oppure
- una squadra di cinque selezionabili da una riserva più ampia.

Il testo attuale tende alla prima lettura: individui persistenti, creazione di unità per sostituire membri e cap di cinque. Questa scelta rende ogni nuova recluta una decisione di sostituzione, ma può far percepire la creazione come una perdita se gli attuali goblin sono più sviluppati. Se l'intenzione è avere riserva e schieramento, specificare separatamente **dimensione del roster** e **dimensione del party in battaglia**.

### Specie/job: varietà con costi di produzione controllati

La distinzione specie (peculiarità) e job (ruolo/abilità) è una buona base sistemica. Evita che ogni nuova specie debba essere una classe completa e può sostenere combinazioni emergenti.

Il costo cresce però rapidamente: ogni combinazione può richiedere statistiche, icone, animazioni, leggibilità, interazioni e test. Per il primo atto consiglio:

- 3 job con funzioni nettamente diverse;
- 2 specie giocabili, inclusa la specie base;
- 1 peculiarità innata per specie, oltre alle statistiche base;
- abilità principalmente definite dal job;
- poche interazioni specie/job progettate a mano, non una regola esclusiva per ogni coppia.

Questo produce sei combinazioni possibili e consente di verificare il sistema senza promettere decine di unità uniche.

### Ricompense per tipo e difficoltà

Che i nemici insegnino specie e job pertinenti è un forte legame fra contenuto e progressione. Premiare maggiormente gli incontri difficili rende gli élite invitanti. Il pericolo è che la ricompensa basata sul numero di nemici favorisca sistematicamente gli incontri più affollati o strategie di farm.

La ricompensa dovrebbe dipendere da una formula semplice, controllata e spiegabile: **tipo di incontro + fascia di difficoltà + eventuale boss**, non soltanto il conteggio dei nemici. Il giocatore dovrebbe sapere se sta ottenendo:

- conoscenza di specie;
- conoscenza di job;
- un membro reclutabile/creabile;
- oggetti o risorse.

Evitare di concedere automaticamente l'intero gruppo sconfitto come party. Il piano parla soprattutto di conoscenze e di creare nuovi goblin: questa distinzione va mantenuta nell'interfaccia.

### Discendenza materna e tono

Le peculiarità ereditate dalla specie materna sono una meccanica distintiva, ma possono restare molto astratte: cattura e riproduzione non sono mostrate, e i nuovi goblin sono il risultato della progressione di lignaggio.

Per ridurre ambiguità di tono e scope, l'interfaccia potrebbe parlare di **lignaggio**, **tratto ereditato** o **conoscenza di specie**; la narrazione può lasciare implicito il modo in cui l'orda ha acquisito la linea. Il giocatore deve capire l'effetto sistemico senza che il sistema trasformi persone catturate in una schermata esplicita di allevamento.

## 3. Oggetti, salute e pressione della run

### Tre slot per personaggio

Arma, armatura e oggetto speciale sono una dotazione facile da capire. Con massimo cinque goblin significa fino a quindici slot potenziali: quantità ragionevole, ma già sufficiente a rendere importante il confronto dei drop.

La regola “il goblin è possessivo e cambia solo con qualcosa di migliore” è coerente come caratterizzazione, ma il criterio di “migliore” è pericoloso se è automatico. Un oggetto può aumentare attacco e perdere una sinergia o una difesa utile.

**Raccomandazione:** mantenere la possessività come tono o regola narrativa, ma mostrare confronto e lasciare al giocatore una scelta esplicita quando un drop ha trade-off. Se si desidera davvero impedire il downgrade, definire una misura semplice per slot e comunicare quando un oggetto non viene accettato.

### Salute persistente e provviste

I danni che persistono fra incontri creano pressione sul percorso e danno una funzione chiara alle provviste. Perché la scelta sia interessante:

- le provviste devono essere sufficientemente rare da richiedere pianificazione;
- il giocatore deve stimare il recupero prima di scegliere un nodo;
- i nodi di riposo devono competere con un'altra opzione appetibile;
- la campagna non deve diventare un'attesa di guarigione dopo ogni battaglia.

Per il primo atto userei solo due risorse durante la run: **provviste** per recupero e **tesoro** per mercanti/eventi. Lasciare fuori l'influenza è la scelta giusta finché non esiste un uso che generi una decisione nuova.

## 4. Rigiocabilità e progressione meta

### Fonti effettive di rigiocabilità

- Warlord con partenze e passivi differenti.
- Incontri e ricompense che sbloccano specie/job diversi.
- Percorsi sulla mappa con nodi e opportunità differenti.
- Combinazioni di abilità che cambiano in base all'ordine.
- Oggetti, talenti e opzioni sbloccati fra run.

Queste fonti si rafforzano se una run porta a costruire un party coerente, ma una lista più ampia di contenuti non garantisce di per sé varietà. La domanda da testare è: **un giocatore può indicare almeno due approcci diversi per affrontare il boss, e la mappa gli consente di preparare quello scelto?**

### Sblocchi permanenti: attenzione al “grind per poter giocare”

Il giocatore ha detto che gli sblocchi possono essere opzioni migliori, passivi, classi iniziali, talenti e oggetti. Questo è un possibile motore di progressione, ma può rendere frustranti le prime run se le opzioni iniziali sono deliberatamente peggiori.

Consigli:

- sbloccare prima **alternative** (un altro stile, job o oggetto con trade-off) e poi bonus diretti;
- non rendere i bonus permanenti obbligatori per vincere;
- evitare che le opzioni base siano deliberatamente incomplete;
- premiare una run breve o un obiettivo, non un numero artificiale di ripetizioni;
- verificare che gli sblocchi non rendano dominante un singolo warlord o una sola composizione.

Un piccolo aumento di potenza può essere accettabile, ma va bilanciato contro il rischio che il giocatore senta di non aver perso per una decisione, bensì perché non aveva ancora sbloccato abbastanza.

### Percorsi “diversi” senza moltiplicare i contenuti

Per l'atto uno non servono mappe casuali completamente nuove. Una mappa authored con nodi alternativi e varianti di incontro può essere sufficiente. Ogni ramo dovrebbe offrire un trade-off concreto, ad esempio:

- battaglia élite: più rischio, conoscenza specie/job maggiore;
- accampamento: recupero affidabile, ma nessun nuovo job;
- evento/razzia: provviste o piccola cura, possibile linea materna rara ma ricompensa inferiore alla battaglia;
- mercante: convertire tesoro in un miglioramento, rinunciando a un'altra opzione;
- nodo di creazione: ampliare o cambiare il party entro il limite di cinque.

Se due rami offrono semplicemente la stessa quantità di potere in ordine diverso, la scelta di percorso è solo presentazionale.

## 5. Level design: campagna e incontri

### Mappa a nodi

Il modello di *Slay the Spire* è adatto a una campagna a marcia: rende la pianificazione leggibile e limita il costo di produzione rispetto a un mondo aperto. Una mappa fissa o semi-fissa è consigliabile all'inizio; si può introdurre casualità nelle composizioni, ricompense e collegamenti mantenendo il ritmo progettato.

Per ogni atto, la mappa dovrebbe:

1. introdurre una minaccia o una regola nuova;
2. consentire una prima scelta fra rischio e recupero;
3. offrire almeno un nodo che modifica il party (creazione, ricompensa di conoscenza o oggetto);
4. dare accesso a un accampamento o a un'altra forma di gestione della salute;
5. preparare con segnali leggibili al boss dell'atto.

Il giocatore ha detto di voler vedere i tipi di nodo disponibili, non ogni dettaglio. È un buon compromesso: tipo e ricompensa probabile sono leggibili, mentre composizione esatta e imprevisti possono restare parzialmente nascosti. Se l'autobattaglia non offre recupero durante lo scontro, gli indizi sul nemico devono essere sufficienti a preparare la formazione senza richiedere una risposta perfetta a informazioni invisibili.

### Ritmo di un atto

Il primo atto dovrebbe insegnare progressivamente il gioco, non contenere subito ogni variante:

1. battaglia semplice per presentare ordine e abilità;
2. bivio fra ricompensa e recupero/evento;
3. primo élite o incontro che richiede una sinergia;
4. primo accesso a mercante, creazione o upgrade;
5. preparazione al boss con una scelta di percorso finale;
6. boss che mette alla prova l'ordine, il party e la gestione delle provviste.

La durata e il numero effettivo di nodi non sono fissati: determinarli con playtest. L'atto deve essere abbastanza completo da giustificare l'Accesso Anticipato, ma non tanto lungo da rimandare il test del loop.

### Battaglie 2D laterali

La visuale laterale è prima di tutto una scelta di presentazione, perché il design corrente non include controlli di movimento o piattaforme. Evitare di aggiungere livelli platform o navigazione ambientale: il valore del campo di battaglia può venire da composizione, bersagli, animazioni e leggibilità della sequenza.

Una variabile di arena (copertura, terreno o ostacolo) può essere testata più avanti, ma solo se incide su una decisione pre-battaglia e non richiede pathfinding complesso. Non è una priorità per il prototipo.

## 6. Monetizzazione e Accesso Anticipato

### Modello consigliato

Per il prodotto descritto, la soluzione più coerente è **premium a prezzo unico**, senza monetizzazione di potenza, loot box, timer o valute a pagamento. La progressione e le ricompense restano parte della campagna, non dell'economia reale.

### Accesso Anticipato al primo atto

Un primo atto venduto in Accesso Anticipato è plausibile, ma deve essere percepito come una porzione completa e rigiocabile:

- loop stabile dall'inizio al primo boss;
- almeno più di una configurazione di party e un motivo per avviare una seconda run;
- salvataggi affidabili, impostazioni e interfaccia leggibile;
- contenuti e limiti dichiarati in modo trasparente;
- prezzo proporzionato al contenuto disponibile, da decidere solo dopo aver provato la build;
- comunicazione onesta che gli atti successivi dipendono da fondi e sviluppo, senza promettere date non sostenibili.

L'Accesso Anticipato non dovrebbe essere usato per finanziare un prototipo ancora privo di loop divertente. È preferibile validare prima una build piccola con tester e poi decidere se il primo atto ha qualità e quantità sufficienti per una release commerciale.

### Uso di asset gratuiti e AI

Asset gratuiti e placeholder sono appropriati per prototipare sistemi e testare ritmo. Prima di una release commerciale, verificare licenze, attribuzioni, diritti di distribuzione e coerenza stilistica di ogni asset. Gli asset AI possono servire per esplorazione e mockup; non sostituiscono una direzione artistica coerente né risolvono la leggibilità delle unità in battaglia. Chiarire l'uso di strumenti AI nella comunicazione di prodotto quando richiesto dalle piattaforme o dalle licenze applicabili.

Possibili ricavi successivi: espansioni sostanziali dopo il gioco base, se il prodotto e il team lo giustificano. Eviterei cosmetici e aggiornamenti continui come priorità per un piccolo single-player.

## 7. Rischi prioritari

| Rischio | Impatto sul giocatore | Risposta di design |
|---|---|---|
| L'ordine abilità non cambia davvero il risultato | Il sistema centrale sembra cosmetico | Costruire interazioni esplicite e confrontare due ordini sullo stesso scontro |
| Risultato automatico non spiegabile | La sconfitta sembra casuale o inevitabile | Mostrare sequenza, bersagli, effetti e riepilogo della battaglia |
| Party di cinque confuso con riserva | Le regole di sostituzione non sono chiare | Definire roster totale e party schierato come quantità separate, oppure dire esplicitamente che sono la stessa cosa |
| Ricompense proporzionali ai nemici favoriscono il farming | Si sceglie il nodo per massimizzare quantità, non per strategia | Premiare la difficoltà e il tipo di sfida con un tetto, non solo il numero di corpi |
| Sblocchi rendono la prima campagna punitiva | Progressione persistente percepita come grind | Dare opzioni e trade-off, non potenza necessaria |
| Oggetti “migliori” sostituiti automaticamente | Il giocatore perde una sinergia scelta | Confronto esplicito e conferma in caso di trade-off |
| Salute persistente esaurisce il party | La run diventa una sequenza di attese o morti | Regolare provviste e accampamenti; testare i danni medi per nodo |
| Scope dell'atto uno troppo ampio | Non si arriva alla release | Limitare specie/job, eventi e varianti; riusare strutture di incontro |
| Accesso Anticipato basato su fondi futuri | Aspettative non soddisfatte | Presentare l'atto uno come un prodotto giocabile e descrivere il resto come piano non garantito |
| Tono tragico interrotto dall'umorismo | L'identità narrativa appare incoerente | Concentrare l'umorismo nei comportamenti/eventi dei goblin senza sminuire sistematicamente le conseguenze |

## 8. Dubbi di design da risolvere, in ordine di priorità

### Bloccanti per un prototipo utile

1. **Il party di cinque è l'intero roster oppure il limite di schieramento?** Questa risposta cambia il valore dei nodi di creazione e delle ricompense.
2. **Come si svolge esattamente un round?** Definire ordine alleati/nemici, ricorrenza delle attivazioni e selezione dei bersagli.
3. **Che cosa può cambiare l'ordine?** È solo la posizione del personaggio oppure esiste un parametro distinto? Può essere riordinato liberamente prima di ogni battaglia? Il piano attuale suggerisce di sì.
4. **Quali sono le tre abilità iniziali e quali sinergie intenzionali hanno?** Se non si possono descrivere due sequenze significative, il core non è ancora validato.
5. **Quanto è visibile il contenuto di un nodo prima di sceglierlo?** Tipo certo, nemici parzialmente rivelati, ricompensa attesa o ignota?
6. **Come una ricompensa di conoscenza diventa una nuova unità?** Quanta conoscenza serve, dove si crea e che succede se il party è già pieno?
7. **Qual è la regola dei goblin possessivi sugli oggetti?** L'oggetto migliore è definito da un punteggio, dal giocatore o da preferenze del personaggio?

### Da risolvere durante il bilanciamento

8. Quanti warlord sono necessari per far sentire significative le partenze da uno o due goblin?
9. Quali differenze fra warlord sono asimmetriche ma bilanciate, invece di rendere uno chiaramente migliore?
10. Quale livello di ferite persiste, e quanto curano provviste, accampamenti e razzie?
11. Le razzie sono eventi casuali o nodi dedicati? Quanto spesso possono offrire una specie/linea materna rara?
12. Quanti oggetti, talenti e passivi servono per una seconda run interessante?
13. Quali sblocchi sono condizionati a obiettivi specifici, e quali si ottengono semplicemente giocando?
14. Quanto casuale sarà la mappa? Quali nodi dell'atto uno sono garantiti e quali variabili?
15. Quanto deve durare un atto e quante battaglie può sostenere prima che il loop diventi ripetitivo?
16. Il boss verifica un counter, una composizione bilanciata o l'uso di una precisa sequenza? Evitare che serva una singola build obbligatoria.
17. I goblin persistono solo durante la run o ci sono personaggi che sopravvivono alla sconfitta? Il piano corrente implica sbloccabilità meta ma non eredi permanenti.
18. Quali opzioni di accessibilità entrano nella prima release oltre a contrasto, testo e sottotitoli?

### Da rimandare

- Numero e contenuto degli atti due e tre, finché atto uno e finanziamento non sono validati.
- Direzione artistica definitiva e collaborazione con artisti.
- Prezzo, solo dopo aver stimato durata, qualità e volume del primo atto.
- Qualsiasi modalità multiplayer, networking o servizio online: non fa parte della roadmap corrente.

## 9. Piano di validazione con prototipi

### Test A — Il combattimento ha profondità?

**Contenuto:** una schermata pre-battaglia, 3 job, 2 specie, 2 composizioni nemiche e un'arena placeholder. Due ordini di party disponibili, nessuna interazione durante lo scontro.

**Esercizio:** chiedere al tester di prevedere quale ordine funzionerà meglio, avviare la battaglia e spiegare il risultato.

**Segnale positivo:** i tester cambiano ordine per una ragione specifica e la differenza è comprensibile guardando la sequenza.

### Test B — Il loop di crescita regge?

**Contenuto:** 3-4 nodi, una ricompensa di specie/job, un nodo di creazione, salute persistente, provviste e un oggetto.

**Esercizio:** far decidere se mantenere i goblin attuali o crearne/sostituirne uno, poi chiedere perché.

**Segnale positivo:** le opzioni aggiunte cambiano il party e la scelta non è sempre “prendi il numero più alto”.

### Test C — Una mini-campagna motiva una seconda run?

**Contenuto:** mappa authored con 6-8 nodi, un bivio, almeno una élite, un evento, un accampamento/mercante e un boss.

**Esercizio:** completare o perdere l'atto, sbloccare una nuova opzione e riavviare scegliendo un'altra rotta o warlord.

**Segnale positivo:** il tester sa indicare quale strategia vuole provare nella seconda run e perché.

### Metriche qualitative e quantitative

- Percentuale di tester che sa prevedere e spiegare l'ordine delle abilità.
- Quante volte l'ordine o la composizione vengono modificati prima dello start.
- Differenza di esito fra due ordini sulla stessa composizione e incontro.
- Danni residui per nodo, provviste spese e frequenza di scelte di riposo.
- Scelte di nodi e ricompense, con motivazione dichiarata.
- Percentuale di tester che ricomincia una run e quale nuova opzione intende provare.
- Durata della campagna e degli scontri, annotando dove si accelera o si salta.

Non fissare soglie arbitrarie prima di avere una prima build: raccogliere una baseline e usare i risultati per decidere quali regole cambiare.

## 10. Raccomandazioni finali

1. Prototipare prima la sequenza delle abilità, non la quantità di specie o la lore.
2. Scrivere una pagina di regole che definisca round, target, ordine, morte e vittoria prima di implementare il sistema esteso.
3. Decidere se roster e party sono la stessa cosa; mantenere il limite di cinque come vincolo forte finché i test non dicono il contrario.
4. Fare in modo che specie/job e ricompense dipendano dai nemici affrontati, ma evitare ricompense lineari che premiano semplicemente la battaglia più affollata.
5. Limitare l'atto uno a contenuti costruiti per mostrare varietà sistemica, non a un grande numero di contenuti.
6. Usare asset gratuiti e placeholder per convalidare gioco e ritmo; verificare licenze e coerenza prima di ogni rilascio commerciale.
7. Lanciare l'Accesso Anticipato solo quando il primo atto è già divertente e completo nella sua promessa locale, comunicando con precisione l'incertezza degli atti successivi.

### Conclusione

**La nuova direzione è più producibile e ha un gancio distintivo**, ma il successo dipende quasi interamente da una domanda: l'ordine preimpostato delle abilità crea abbastanza agency da rendere interessanti decine di scontri automatici? Il prototipo deve rispondere a questo prima di investire in meta-progressione, grandi roster o produzione artistica. Se funziona, la mappa a nodi, il party piccolo e l'apprendimento delle specie/job possono sostenere una campagna compatta e rigiocabile. Se non funziona, aggiungere contenuti non risolverà il problema.

Risposte:

## 8. Dubbi di design da risolvere, in ordine di priorità

### Bloccanti per un prototipo utile

1. **Il party di cinque è l'intero roster oppure il limite di schieramento?** 
Limite di schieramento, volendo è possibile cambiare il party da battaglia a battaglia, ma il limite sarà di 5, con un limite in panchina di altri 5? 

2. **Come si svolge esattamente un round?** Definire ordine alleati/nemici, ricorrenza delle attivazioni e selezione dei bersagli.
Direi che è un autobattler dove ogni personaggio attacca a suo ritmo e poi ha delle abilità che si attivano ogni x secondi. tipo tank fa taunt, healer cura e così via. 
Numeri che rimangono bassi all'inizio e volendo i goblin salgono di livello (come le ricompense salgono di livello) con il tempo.

3. **Che cosa può cambiare l'ordine?** 
L'ordine indica magari chi viene attaccato per primo e chi deve passare da più avversari per arrivare al fondo del party. ci potrebbero essere bonus di vicinanza tra i goblin, o posizioni predilette delle classi (job) per funzionare meglio. Addirittura potrebbe cambiare l'abilità attiva o il tratto in base alla posizione in battaglia. O artefatti globali (come in slay the spire) influenzare certe posizioni della battaglia. 

4. **Quali sono le tre abilità iniziali e quali sinergie intenzionali hanno?** 
Le abilità dei goblin sono tipo: 
Guerriero: Strike (attacco normale), taunt (provocazione, attaccano lui), shield bash (stunna un nemico).
Barbaro: Strike (attacco normale), Rage (più danni fatti, meno subiti, meno armatura), doppio colpo (attacca 2 volte, secondo attacco 50% del danno).
Chierico: Holy Flame (attacco normale a distanza), heal (cura un alleato), resurrection (30% salute, lungo cooldown)
Stregone: static shock (attacco normale), fireball (attacco ad area), meditation (il prossimo attacco magico fa più danni, un alleato come target anche se stessi)
E la struttura segue questo schema: attacco normale, abilità relazione alla classe che spamma, abilità più forte che però ha un cooldown più alto.
altre classi possono essere Ranger, Monaco, Paladino, Pistolero, Cavaliere, Mago, Ladro, Ninja, Samurai, Necromante, Psionico, Morfico, Druido, Evocatore, Elementalista, ecc ecc. 

5. **Quanto è visibile il contenuto di un nodo prima di sceglierlo?** Il contenuto del nodo non è visibile, vedi solo la tipologia di nodo e la difficoltà è spiegata dal nodo stesso (battaglia, battaglia elite, boss, tesoro, evento casuale, raid)

6. **Come una ricompensa di conoscenza diventa una nuova unità?** 
La ricompensa diventa una nuova unità una volta superata una certa soglia di punti o arrivati ad un punto di riposo che conta come bonus per una spefica conoscenza nel caso non sia ancora arrivata a livello.

7. **Qual è la regola dei goblin possessivi sugli oggetti?** Oggetto migliore significa rarità superiore all'oggetto precedente, non accettano stessa rarità, quindi dare l'oggetto o meno è una scelta tattica importante. 

### Da risolvere durante il bilanciamento

8. Quanti warlord sono necessari per far sentire significative le partenze da uno o due goblin?
Almeno 3 warlord differenti. Tipo guerriro, mago, ladro.

9. Quali differenze fra warlord sono asimmetriche ma bilanciate, invece di rendere uno chiaramente migliore?
principalmente sono i goblin figli di partenza, magari dare le conoscenze di alcuni rami già sviluppate al livello 1 per la creazione di goblin, cioè quelle dei goblin di partenza. 
Quindi cambia principalmente il vantaggio iniziale della run, ma non di troppo. 
10. Quale livello di ferite persiste, e quanto curano provviste, accampamenti e razzie?
I goblin hanno HP, rimangono gli hp mancanti, ma non hanno livello le ferite. 
Le provviste curano X hp, tipo 5, tra battaglia e battaglia finchè ci sono.
Gli accampamenti curano 10 a tutti e non consumano provviste. 
Razzie guadagni provviste, guadagni 5. 
11. Le razzie sono eventi casuali o nodi dedicati? Quanto spesso possono offrire una specie/linea materna rara?
Nodi dedicati. Specie / linea materna rara 1 ogni atto al massimo. 
12. Quanti oggetti, talenti e passivi servono per una seconda run interessante?
chi più ne ha, più ne metta, ogni volta che ci viene in mente qualcosa possiamo aggiungere. se diventa troppo forte per le run possiamo separarlo in più pezzi e fare tipo un set, se hai il set intero, sblocchi il potere extra. 
13. Quali sblocchi sono condizionati a obiettivi specifici, e quali si ottengono semplicemente giocando?
I tratti dei goblin specifici (classi) vegono sbloccati man mano che giochi con quella classe. usando le abilità spefiche della classe. O vincendo con un certo warlord.
14. Quanto casuale sarà la mappa? Quali nodi dell'atto uno sono garantiti e quali variabili?
Direi almeno garantiti (ma non per forza sempre raggiungibili da qualunque strada passi) 2 negozianti, 5 battaglie elite. 5 riposi. Poi un tesoro / razzia obbligatoria per atto, più o meno a metà in qualiasi percorso possibile.  il resto causale tra battaglie e eventi. 
15. Quanto deve durare un atto e quante battaglie può sostenere prima che il loop diventi ripetitivo?
nessuna battaglia ripetuta nello stessa campagna. quindi pianificare molte possibilità di scontri e combinazioni di nemici. 
16. Il boss verifica un counter, una composizione bilanciata o l'uso di una precisa sequenza? Evitare che serva una singola build obbligatoria.
i boss degli atti avranno delle meccaniche loro per vedere se hai sia i numeri adatti per passare al round successivo. e diamo anche magari una gimmick riconoscibile prima dello scontro 
17. I goblin persistono solo durante la run o ci sono personaggi che sopravvivono alla sconfitta? Il piano corrente implica sbloccabilità meta ma non eredi permanenti.
nessun goblin sopravvive alla partita. volendo ci più essere una hall of fame con le statistiche dei tuoi goblin migliori diventati "eroi" e mostrare le loro madri. 
18. Quali opzioni di accessibilità entrano nella prima release oltre a contrasto, testo e sottotitoli?
tutte le altre necessarie, magari daltonia, quindi aggiungere simboli vicino a certe keyword di gioco o classi pg. 

### Da rimandare

- Numero e contenuto degli atti due e tre, finché atto uno e finanziamento non sono validati.
- Direzione artistica definitiva e collaborazione con artisti.
- Prezzo, solo dopo aver stimato durata, qualità e volume del primo atto.
- Qualsiasi modalità multiplayer, networking o servizio online: non fa parte della roadmap corrente.