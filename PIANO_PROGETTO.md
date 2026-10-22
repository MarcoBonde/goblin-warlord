# Goblin Warlord — Piano di progetto

> Documento di pre-produzione aggiornato con le decisioni attuali, incluse le risposte alla seconda valutazione. I dettagli indicati come da bilanciare restano soggetti a prototipazione e playtest.

## 1. Visione

**Goblin Warlord** è un roguelite dark fantasy 2D per pubblico adulto, costruito attorno a una campagna di conquista. Il giocatore sceglie un warlord goblin e guida una piccola armata in un'unica marcia attraverso il mondo fino alla capitale, conquistando territori e sbloccando specie e job da integrare nell'orda.

La campagna si sviluppa in tre atti su una mappa di nodi in stile *Slay the Spire*: il giocatore vede solo il tipo e la difficoltà del nodo, sceglie il percorso e affronta un boss alla fine di ogni atto; il boss del terzo atto si trova nella capitale ed è l'obiettivo conclusivo. La presentazione degli scontri è laterale, in 2D; il combattimento è un **autobattler senza interventi durante la battaglia**. I personaggi attaccano secondo il proprio ritmo e attivano abilità a intervalli/cooldown. La strategia sta nella composizione del party, nell'equipaggiamento e nel posizionamento, che può influenzare bersagli, accesso alle retrovie, sinergie e abilità.

### Promessa al giocatore

> Scegli uno dei warlord, prepara un party di massimo cinque goblin e marcia fino alla capitale: ogni battaglia, formazione e scelta di percorso determina quali specie, job, talenti ed equipaggiamenti potrai usare.

### Pubblico e tono

- Pubblico adulto, interessato a dark fantasy, strategia leggera e roguelite.
- Tono principalmente tragico, con momenti di stupidità e umorismo goblin soprattutto negli eventi.
- La fantasia centrale è guidare un'armata goblin spietata fino alla conquista del mondo; non esistono percorsi politici o diplomatici alternativi all'obiettivo.
- Violenza senza sangue esplicito: attacchi e magie fanno intuire il danno senza rappresentarlo graficamente.
- Temi maturi e rapporti con persone catturate restano impliciti o fuori campo; la riproduzione non viene mostrata. La componente di eredità è trattata come sistema di gioco e di lore, senza scene esplicite.

## 2. Genere e formato

- **Genere:** roguelite tattico a squadre, con mappa ramificata, progressione dell'armata e autobattaglie.
- **Prospettiva:** 2D laterale.
- **Struttura:** campagna single-player in tre atti; un'unica avanzata ramificata verso la capitale, con un boss alla fine di ogni atto.
- **Combattimento:** autobattler; dopo l'avvio dello scontro non c'è input del giocatore. Il party e le posizioni vengono preparati prima della battaglia; durante lo scontro gli attacchi e le abilità si attivano a ritmo autonomo.
- **Piattaforma iniziale proposta:** PC.
- **Tecnologia:** Godot 4, progetto 2D.
- **Lingue previste:** italiano e inglese.
- **Modalità:** giocatore singolo, offline. Nessun multiplayer nel progetto attuale; non va pianificato né implementato.

## 3. Pilastri di design

1. **La campagna è una marcia verso la capitale.** Ogni atto avvicina al boss e all'obiettivo finale.
2. **L'armata cresce imparando dai nemici.** Le vittorie sbloccano conoscenze di specie e job; la discendenza dei nuovi goblin può ereditare peculiarità della specie materna.
3. **La preparazione è il combattimento.** Il giocatore non interviene durante l'autobattaglia: composizione, oggetti e posizionamento influenzano bersagli, sinergie e abilità.
4. **La squadra è piccola e personale.** Ogni membro è un individuo con specie, job, statistiche ed equipaggiamento.
5. **Le run sbloccano opzioni.** Nuovi warlord, classi iniziali, passivi, talenti e oggetti ampliano le possibilità delle campagne successive.

## 4. Ciclo di gioco

### Ciclo della campagna

1. **Scegli un warlord:** almeno tre archetipi iniziali (guerriero, mago e ladro) danno figli e conoscenze iniziali differenti, senza rendere un'opzione obbligatoriamente superiore.
2. **Scegli il prossimo nodo** conoscendone il tipo e la difficoltà, ma non il contenuto preciso: battaglia, élite, boss, tesoro, evento casuale o razzia; la mappa include anche riposi e mercanti.
3. **Prepara il party** prima di ogni scontro: scegli fino a cinque combattenti da un roster che può includere fino a cinque riserve, quindi definisci formazione e posizioni.
4. **Combatti automaticamente:** non ci sono comandi o abilità attivabili dal giocatore durante la battaglia. I personaggi attaccano al proprio ritmo e usano abilità periodiche; posizione, bersagli e sinergie determinano l'esito.
5. **Ottieni ricompense** pertinenti ai nemici affrontati: specie e job progrediscono con punti/conoscenze; difficoltà ed élite aumentano i guadagni.
6. **Gestisci salute e risorse:** spendi provviste per curare il party fra gli scontri, usa il tesoro da mercanti o in eventi, riposa e potenzia negli accampamenti.
7. **Avanza attraverso i tre atti**, sconfiggi i rispettivi boss e punta alla capitale e al boss finale.
8. **Vinci o perdi la run.** Una sconfitta conclude la campagna; gli sblocchi persistenti ampliano le opzioni per i tentativi successivi.

## 5. Sistemi principali

### 5.1 Personaggi, specie, job e discendenza

- Il party schierato ha un massimo di **cinque personaggi**; il roster può contenere fino a **cinque riserve aggiuntive**. Si può modificare il party prima di ogni battaglia. Il limite della panchina va confermato nel prototipo.
- All'inizio il warlord scelto determina i figli di partenza e quali rami di conoscenza sono già al livello 1. I tre archetipi iniziali minimi sono guerriero, mago e ladro; ciascuno deve offrire un vantaggio iniziale moderato e distinto.
- I personaggi sono individui persistenti, non pedine fungibili. Ognuno ha nome/identità, specie (linea materna), job, salute, attacco e difesa.
- Le specie conferiscono peculiarità innate; i job definiscono il ruolo e le abilità. Specie e job sono sistemi distinti e possono combinarsi come in un gruppo fantasy.
- L'assimilazione è un reclutamento forzato astratto: non si mostra come avviene, ma si ottengono nuove **conoscenze** di specie/job, come se l'orda imparasse dai vinti.
- Ogni battaglia fornisce punti di conoscenza di specie e job pertinenti agli avversari. Al raggiungimento di una soglia si sblocca la possibilità di creare una nuova unità di quella linea/job; un punto di riposo può assegnare un bonus mirato a una conoscenza prossima al livello successivo.
- Le ricompense aumentano con la difficoltà e il numero di avversari, oltre che in base al tipo di incontro. La progressione dei punti e i tetti per incontro devono evitare farming eccessivo.
- I goblin possono salire di livello durante la campagna; anche livello e qualità delle ricompense possono crescere con la progressione, mantenendo i valori numerici contenuti e leggibili.
- I goblin creati durante la campagna possono ereditare peculiarità dalla specie materna acquisita. La cattura e la riproduzione restano implicite e fuori campo: non si mostrano rapporti o atti sessuali. Una razzia può occasionalmente sbloccare una nuova linea materna o una specie, come ricompensa narrativa e di progressione.
- I nodi dedicati permettono di creare nuovi goblin usando le conoscenze/specie e i job disponibili. Il loro scopo è offrire membri al roster/party; se la panchina è piena, il giocatore deve sostituire un membro o rinunciare alla nuova unità.
- I rapporti di forza e le caratteristiche specie/job devono essere leggibili e creare scelte; non ogni combinazione richiede una regola o un'animazione esclusiva.

**Job e classi:** il sistema prende ispirazione dalla varietà di ruoli di un gruppo fantasy. Il documento [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) raccoglie i kit proposti per le 28 classi richieste, suddivise in Base, Avanzate, Alternative e Ibride. Ogni kit definisce attacco base, abilità spam, ultimate automatica, passiva e idee di tratti sbloccabili; è il riferimento di design da cui selezionare e prototipare, non una promessa che tutte le classi saranno presenti nel gioco. Il prototipo iniziale include almeno **Guerriero, Barbaro, Chierico e Stregone**; l'Accesso Anticipato aggiunge classi solo in quantità compatibile con il tempo di produzione.

**Specie di partenza e progressione:** il roster iniziale è goblin; nuove specie e peculiarità si scoprono affrontando nemici e attraverso eventi. Limitare il numero di specie/job implementati per l'Accesso Anticipato in base agli asset e al tempo disponibili.

### 5.2 Combattimento autobattler

- Prima di ogni scontro il giocatore sceglie fino a cinque membri dal party attivo e può modificare la formazione; sono previste fino a cinque riserve aggiuntive. Premendo **Start battaglia** avvia lo scontro.
- **Nessun input tattico del giocatore durante lo scontro.** Le unità attaccano automaticamente al proprio ritmo e attivano abilità a intervalli/cooldown; il giocatore non cambia bersagli né attiva skill.
- Le posizioni influiscono su chi viene attaccato per primo, sul percorso che i nemici devono attraversare per raggiungere i personaggi più arretrati e sulle sinergie di vicinanza.
- Alcuni job possono avere posizioni preferite; posizione e/o artefatti globali possono modificare tratti o abilità attive. Queste regole sono candidate da prototipare, non vanno aggiunte tutte contemporaneamente.
- Ogni personaggio segue una struttura di **attacco base + abilità caratteristica a cooldown breve + abilità potente a cooldown lungo**. Gli attacchi base e i cooldown devono risultare leggibili e bilanciabili.
- Per i kit e gli effetti candidati si usa [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md), mantenendo le abilità automatiche e i bersagli coerenti con il combattimento senza input. Per il primo prototipo, i kit di **Guerriero, Barbaro, Chierico e Stregone** forniscono la base da testare: rispettivamente *Colpo d'arma / Provocazione / Muro di scudi*, *Fendente furioso / Rabbia / Turbine selvaggio*, *Fiamma sacra / Cura / Rianimazione* e *Scarica innata / Fiammata erratica / Eruzione del sangue* (attacco base / abilità spam / ultimate).
- Statistiche di base: salute, attacco e difesa; velocità/ritmo di attacco e cooldown sono parametri del sistema di combattimento. Evitare altre statistiche finché non sono necessarie.
- La presentazione deve rendere comprensibili posizioni, bersagli, attacchi, cooldown, abilità e sinergie; la battaglia deve poter essere letta senza microgestione.
- Gli oggetti, le specie, i job, la formazione e gli artefatti globali sono le leve di preparazione. L'abilità del giocatore consiste nel prevedere l'incontro e costruire una configurazione coerente.

### 5.3 Progressione durante e fra le campagne

- Durante una campagna, le battaglie sbloccano conoscenze di specie e job in base agli avversari sconfitti; difficoltà e numero di nemici influenzano la quantità ottenuta.
- Le conoscenze di specie/job avanzano tramite punti e soglie; un riposo può assegnare punti bonus a una conoscenza che non ha ancora raggiunto il livello successivo.
- I goblin possono salire di livello durante la campagna. Livelli e ricompense possono aumentare con la progressione, mantenendo i numeri iniziali contenuti e facilmente leggibili.
- Eventi, razzie e nodi di creazione possono fornire risorse, guarigione leggera, nuovi goblin o nuove linee/specie materne. Le razzie sono eventi senza combattimento, con ricompense inferiori a una battaglia ma con provviste e una piccola cura; occasionalmente possono sbloccare una specie o una madre particolare.
- Le unità mantengono i danni subiti fra battaglie. Le provviste sono la risorsa principale per curare il party fra gli scontri; accampamenti e alcuni eventi possono offrire riposo o potenziamenti.
- La sconfitta conclude la run e richiede di ricominciare.
- Nessun goblin sopravvive alla sconfitta della run. Una **Hall of Fame** può registrare gli eroi migliori con statistiche, job e linea materna/specie di origine; è una funzione commemorativa, non un sistema di persistenza dei personaggi.
- Le vittorie e sconfitte possono sbloccare contenuti persistenti per le run successive: warlord o classi iniziali, passivi, talenti ed equipaggiamenti. Gli sblocchi aggiungono opzioni, alcune potenzialmente più forti; il bilanciamento deve evitare che il progresso permanente renda inutile la preparazione o imponga grind.
- Tratti specifici di classe si sbloccano giocando quella classe e usando le sue abilità; alcune opzioni possono inoltre sbloccarsi vincendo con uno specifico warlord.
- Talenti da assegnare ai goblin e nuove opzioni possono essere sbloccati giocando più campagne. La progressione persistente va comunicata chiaramente e non deve essere confusa con il roster di cinque individui della run corrente.
- I talenti/oggetti possono appartenere a set: possedere/equipaggiare un numero definito di pezzi attiva un bonus aggiuntivo. I set vanno introdotti con cautela, per evitare combinazioni eccessivamente potenti.

### 5.4 Equipaggiamento e risorse

Ogni personaggio ha tre slot: **arma, armatura e oggetto speciale**. Gli oggetti sono personali e i goblin sono possessivi: un personaggio accetta la sostituzione solo se il nuovo oggetto ha rarità superiore a quello equipaggiato; un oggetto di pari rarità o inferiore non viene accettato. Il giocatore sceglie se assegnare o rifiutare il nuovo oggetto. Bonus di set possono essere aggiunti in seguito: raccogliere più pezzi dello stesso set può attivare un effetto aggiuntivo; il numero di set e pezzi iniziali va mantenuto contenuto.

**Risorse della run**

- **Provviste:** usate per curare il party fra le battaglie; senza spesa o un nodo di riposo, i danni restano. Valori iniziali da testare: 5 HP per cura tramite provviste, 10 HP curati a ogni personaggio in accampamento e +5 provviste per una razzia. Stabilire col prototipo se la cura a provviste è per personaggio o per l'intero party e quante provviste consuma.
- **Tesoro:** usato con i mercanti e in eventi che chiedono un sacrificio o pagamento.
- **Influenza:** non inclusa nel prototipo/MVP. In precedenza era stata ipotizzata per eventi e controllo di goblin forti, ma la sua funzione non è ancora abbastanza definita; reinserirla solo se emergerà una decisione distinta che non possono già svolgere le provviste o il tesoro.

Le risorse devono avere utilizzi distinti e poche schermate di gestione: non aggiungere valute solo per simulare la logistica.

### 5.5 Mappa della campagna e tipi di nodo

- Il mondo è una marcia in avanti verso la capitale, suddivisa in tre atti. Ogni atto termina con un boss; il boss del terzo atto si trova nella capitale ed è il boss finale.
- La mappa può avere bivi e percorsi alternativi, ma non deviazioni verso campagne o strategie di conquista indipendenti: tutti i percorsi servono l'obiettivo di conquistare il mondo.
- Prima di scegliere, il giocatore vede il **tipo e la difficoltà del nodo**, ma non il contenuto specifico. Le categorie includono battaglia, élite, boss, tesoro, evento casuale e raid/razzia; sono inoltre presenti riposi, creazione e mercanti.
- Ogni atto prevede almeno **due nodi mercante, cinque incontri élite e cinque riposi** distribuiti sulla mappa; non tutti devono essere raggiungibili in ogni percorso. Ogni percorso deve invece includere un nodo obbligatorio di tesoro o razzia circa a metà dell'atto.
- Il resto dei nodi varia fra battaglie normali ed eventi. Gli incontri di battaglia (composizione nemica e scenario/regole dell'incontro) non si ripetono all'interno della stessa campagna: le combinazioni e i contenuti devono bastare a sostenere i percorsi possibili.
- I raid/razzie sono nodi dedicati senza combattimento: forniscono provviste e una cura leggera; raramente possono sbloccare una linea materna o specie speciale. La ricompensa rara è limitata a una per atto al massimo.
- Villaggi e città possono essere tematizzati negli incontri o negli eventi, senza richiedere un sistema diplomatico autonomo.
- Gli eventi possono offrire sotterfugi e scelte utili alla stessa avanzata militare. Non ci sono vittorie diplomatiche o un percorso di governo pacifico.
- La conquista dei villaggi/città e le razzie devono offrire differenze leggibili di rischio e ricompensa, ma non richiedono un simulatore di fazioni per l'MVP.
- I boss hanno meccaniche riconoscibili e una gimmick comunicata prima dello scontro. Verificano sia che i personaggi abbiano statistiche/livello sufficienti per avanzare sia che il giocatore sappia adattare il party alla meccanica, senza rendere obbligatoria una singola composizione.

## 6. Struttura narrativa

### Premessa

Un warlord goblin avvia una marcia di conquista verso la capitale, attraversando tre atti di territori difesi da eserciti, mostri e insediamenti. L'orda parte con uno o due goblin base; battaglie ed eventi forniscono conoscenze di specie/job e opportunità per creare nuovi membri, fino a cinque nel party e cinque in panchina. La storia segue l'avanzata militare e le conseguenze della conquista.

### Temi e conflitti

- Conquista, sopravvivenza e costo della guerra.
- Assimilazione e identità delle diverse specie dell'orda.
- Successione e peculiarità ereditate dalla linea materna.
- Brutalità implicita e conseguenze della cattura, senza rappresentazione sessuale esplicita.
- Gli eventi possono essere tragici, con momenti comici dovuti alla stupidità goblin.

### Presentazione sostenibile

- Eventi testuali brevi con scelte e sotterfugi diretti alla conquista.
- Nessun albero di dialogo esteso nel prototipo; non si sviluppano sistemi autonomi di diplomazia o politica.
- Niente sangue o rappresentazione grafica del danno; violenza, rapporti con persone catturate e riproduzione restano sottintesi/fuori campo.
- Tono principalmente tragico, alleggerito occasionalmente dall'umorismo involontario dei goblin.

## 7. Ambito: MVP e contenuti esclusi

### Prototipo iniziale

- Una battaglia autobattler ripetibile con un warlord e 1-2 unità iniziali, più job/specie di prova e attacchi automatici a ritmo/cooldown.
- Party di battaglia massimo cinque e panchina di riserva fino a cinque personaggi; il giocatore cambia membri e posizioni prima di ogni scontro.
- Ricompense di specie/job come progressi a soglie, variabili per tipo e difficoltà dell'incontro.
- Posizioni che influenzano target/priorità e almeno una sinergia di vicinanza o posizione preferita.
- Una gimmick di boss leggibile e anticipata.
- Una prima prova di creazione di goblin, discendenza/specie materna, provviste, oggetti e danni persistenti.
- Una mini-mappa che prova generazione/garanzie dei nodi, inclusa una razzia/tesoro.
- Asset gratuiti e placeholder; usare strumenti AI per supportare i test iniziali. Nessuna spesa significativa in produzione artistica prima di validare lo slice.

### Accesso Anticipato — primo atto

- Prima release pubblica in Accesso Anticipato: il **primo atto completo**, dalla partenza al primo boss.
- Almeno **tre warlord** iniziali: guerriero, mago e ladro; variano figli e conoscenze iniziali, con vantaggi limitati e bilanciati.
- Party massimo cinque e panchina fino a cinque; un set contenuto ma significativo di specie e job, con almeno una linea materna alternativa.
- Tipi di nodo principali: battaglie normali/élite, eventi casuali, accampamenti, creazione di unità, mercanti, tesoro/raid e boss dell'atto.
- Per l'atto: almeno due nodi mercante, cinque élite e cinque riposi sulla mappa complessiva; tesoro o raid obbligatorio circa a metà per ciascun percorso. Non tutti i nodi garantiti devono essere raggiungibili da ogni rotta.
- Nessuna battaglia o composizione d'incontro ripetuta durante una campagna; il numero di incontri distinti sostenibili va definito prima del contenuto finale dell'atto.
- Tre slot equipaggiamento per personaggio (arma, armatura, speciale), provviste per la cura e tesoro per acquisti/eventi.
- Sconfitta della run, Hall of Fame e primi sblocchi persistenti: nuove opzioni di partenza, passivi, talenti e oggetti. I tratti di classe si sbloccano usando le abilità della classe o vincendo con specifici warlord.
- Solo placeholder e asset gratuiti finché non sarà possibile collaborare con un artista e finanziare la produzione visiva definitiva.
- Italiano e inglese per testi e interfaccia.
- Pubblicare come Accesso Anticipato solo quando il primo atto offre un ciclo completo e giocabile; comunicare chiaramente che atti successivi dipendono da finanziamenti e sviluppo futuro.

### Gioco completo previsto

- Tre atti in un'unica campagna di conquista; il boss finale presidia la capitale.
- Ulteriori warlord, specie, job, talenti, oggetti, eventi e contenuti per i tre atti, dimensionati in base ai risultati, al tempo e ai fondi.
- L'espansione oltre il primo atto non è una promessa di data o contenuto finché non viene finanziata.

### Fuori ambito per l'MVP

- Combattimento action controllato direttamente, platforming e fisica di precisione.
- Multiplayer, cooperativa, modalità online o servizi server. Il multiplayer resta una possibilità remota da considerare solo dopo il rilascio del single-player; non va progettato o implementato nell'MVP.
- Mondo aperto, deviazioni verso campagne alternative o mappe generate proceduralmente complesse.
- Diplomazia, conquista pacifica o sistemi geopolitici autonomi.
- Interventi e comandi del giocatore durante l'autobattaglia.
- Un party schierato superiore a cinque personaggi; una panchina fino a cinque riserve è il target corrente.
- Influenza come risorsa finché non viene definita una funzione necessaria e distinta.
- Produzione artistica costosa prima della validazione e del finanziamento.
- Dialoghi doppiati e cinematiche.
- Rappresentazione esplicita di rapporti sessuali o riproduzione.
- Gestione esplorabile della base.

## 8. Roadmap di produzione

### Fase 0 — Prototipo economico

- Creare il progetto Godot 4 e una scena di battaglia leggibile usando placeholder e asset gratuiti.
- Definire le risorse dati di personaggio, specie, job, abilità e oggetti.
- Usare i kit di Guerriero, Barbaro, Chierico e Stregone proposti in [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) per il prototipo; verificare che ruolo, bersagli, frequenza delle abilità e cooldown siano distinguibili e leggibili.
- Sperimentare party schierato massimo cinque, panchina fino a cinque, partenze da uno o due goblin e warlord con conoscenze iniziali differenti.
- Implementare attacchi a ritmo autonomo e cooldown per abilità; nessun input del giocatore durante lo scontro.
- Provare le posizioni: priorità dei bersagli, accesso ai personaggi arretrati, posizione preferita e una sinergia di vicinanza.
- Verificare che la battaglia automatica sia comprensibile senza input durante lo scontro.

**Uscita:** un prototipo di combattimento con schermata pre-battaglia, scelta party/posizioni, boss con gimmick anticipata e risoluzione automatica osservabile.

### Fase 1 — Progressione del party

- Implementare salute persistente, provviste e recupero.
- Aggiungere tre slot oggetto e accettazione dei drop solo se hanno rarità superiore all'oggetto equipaggiato, comunicando chiaramente la regola.
- Aggiungere progressi di specie/job a soglie, legati agli avversari, alla difficoltà e al numero di nemici.
- Aggiungere level up dei goblin e ricompense che crescono con la progressione mantenendo valori numerici bassi.
- Provare creazione di nuovi goblin e peculiarità ereditate dalla linea materna.
- Provare sblocco di tratti di classe tramite uso delle abilità e vittorie con warlord specifici.
- Selezionare dal documento [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) pochi tratti sbloccabili per classe e provarli prima di espandere il catalogo.

**Uscita:** sconfiggere un incontro modifica le opzioni del party; il party schierato resta entro cinque unità e la panchina entro cinque riserve.

### Fase 2 — Mappa e primo atto giocabile

- Creare una mappa authored con bivi; mostrare i tipi di nodo raggiungibili.
- Implementare battaglia, élite, evento, accampamento, creazione, mercante e boss.
- Collegare le ricompense, la cura tramite provviste, il tesoro e la preparazione prima dello start.
- Creare una gimmick unica per il boss e comunicarla prima della battaglia.
- Garantire almeno due mercanti, cinque élite e cinque riposi nella mappa dell'atto; assicurare un nodo tesoro/raid a metà su ogni percorso.
- Produrre un numero sufficiente di incontri distinti per evitare ripetizioni nello stesso atto.
- Completare la marcia fino al boss del primo atto.

**Uscita:** un primo atto completo dall'inizio al boss, con vittoria e sconfitta gestite.

### Fase 3 — Sblocchi e run successive

- Salvare gli sblocchi persistenti fra campagne.
- Implementare almeno tre warlord, classi, passivi, talenti e oggetti sbloccabili.
- Aggiungere Hall of Fame per gli eroi migliori, senza far sopravvivere i personaggi fra le run.
- Aggiungere set di oggetti/talenti solo dopo aver validato il bilanciamento degli oggetti individuali.
- Bilanciare la crescita: gli sblocchi ampliano le scelte e possono essere più forti, ma la vittoria non deve richiedere farming ripetitivo.
- Verificare che una nuova run cambi realmente le possibilità del party.

**Uscita:** il ciclo di sconfitta/riavvio offre nuove opzioni e mantiene le scelte di preparazione rilevanti.

### Fase 4 — Accesso Anticipato

- Preparare il primo atto per il rilascio pubblico solo dopo playtest e verifica di stabilità.
- Usare placeholder e asset gratuiti, sostituendoli con asset sviluppati in collaborazione solo se disponibili fondi e partner artistici.
- Pubblicare in italiano e inglese; raccogliere feedback su combattimento, mappa, durata e progressione.
- Comunicare che atti due e tre dipendono dal finanziamento e non hanno una data garantita.

**Uscita:** primo atto rifinito e giocabile in Accesso Anticipato, con salvataggi affidabili e piano di aggiornamento trasparente.

### Fase 5 — Atti successivi e gioco completo

- Sviluppare il secondo e il terzo atto quando risorse, feedback e capacità produttiva lo consentono.
- Aggiungere nuovi nemici, job, specie, oggetti, eventi e boss solo nella misura sostenibile.
- Completare la marcia fino alla capitale e al boss finale; rivedere bilanciamento e accessibilità sull'intera campagna.

**Uscita:** campagna completa in tre atti; date e contenuti vengono pianificati solo quando finanziati.

## 9. Distribuzione e monetizzazione

- **Modello previsto:** gioco single-player premium a prezzo unico, senza acquisti di potenza, valute premium, energia, loot box o pass stagionali.
- **Accesso Anticipato:** la prima release contiene l'atto uno fino al suo boss. Il prezzo non è ancora deciso e va valutato quando durata, rifinitura e contenuti dell'atto saranno misurabili.
- **Atti due e tre:** si sviluppano quando fondi, feedback e capacità produttiva lo permettono; non sono garantiti da una data non finanziata.
- Una demo gratuita può essere valutata per mostrare il loop prima dell'acquisto, ma non è un prerequisito del prototipo.
- Eventuali DLC o espansioni sono decisioni future e non devono frammentare i contenuti del gioco base prima che questo sia completo.
- Il multiplayer non è una fonte di monetizzazione né un requisito di produzione.

## 10. Architettura Godot proposta

Organizzare i dati separatamente dalle scene, usando `Resource` personalizzate per le definizioni statiche e nodi per la presentazione e l'esecuzione.

```text
res://
  scenes/
    main/
    campaign/
    battle/
    ui/
  scripts/
    managers/
    battle/
    campaign/
    roster/
  data/
    characters/
    species/
    jobs/
    skills/
    traits/
    equipment/
    events/
    route_nodes/
    rewards/
  art/
    characters/
    environments/
    ui/
  audio/
```

### Scene principali

```text
Main
├── ScreenRouter
├── CampaignScreen
│   ├── RouteMap
│   ├── RosterScreen
│   ├── FormationScreen
│   ├── PreBattleScreen
│   └── BattleScreen
│       ├── Battlefield
│       └── BattleHUD
└── CampaignState
```

### Responsabilità

- **CampaignManager:** atto, nodo corrente, avanzamento verso la capitale e condizioni di vittoria/sconfitta.
- **RosterManager:** party schierato massimo cinque, panchina fino a cinque, composizione, conoscenze specie/job e assegnazione alle posizioni.
- **BattleController:** simula attacchi a ritmo autonomo, cooldown, bersagli e abilità; non espone input tattici durante la battaglia.
- **CharacterDefinition / SpeciesDefinition / JobDefinition / SkillDefinition / TraitDefinition:** personaggi, specie, job, abilità, tratti e modificatori di posizione.
- **EquipmentDefinition:** dati degli oggetti per arma, armatura e slot speciale.
- **RouteNodeDefinition / EncounterDefinition / EventDefinition:** mappa, composizioni nemiche, eventi e ricompense.
- **KnowledgeProgressionManager:** punti e soglie per sbloccare conoscenze di specie e job e creare nuove unità.
- **MetaProgressionManager:** sblocchi persistenti di warlord, tratti di classe, passivi, talenti, oggetti e set.
- **HallOfFame:** statistiche commemorative dei goblin migliori, inclusa la linea materna/specie d'origine.
- **SaveManager:** serializzazione dello stato della campagna e degli sblocchi, con versione dei salvataggi.
- **ScreenRouter:** cambio fra mappa, preparazione, battaglia automatica e risultati.

Evitare un manager globale che contenga ogni regola. Non introdurre networking o dipendenze multiplayer: il progetto è single-player offline.

## 11. Interfaccia, localizzazione e accessibilità

- Schermata pre-battaglia: roster disponibile, party attuale, formazione/posizioni, statistiche, oggetti e comando **Start battaglia**.
- La mappa mostra chiaramente tipo e difficoltà dei nodi accessibili, ma nasconde l'incontro specifico; mostra inoltre la direzione generale verso il boss/atto successivo.
- La formazione spiega bersagli/priorità, percorso verso le retrovie, bonus di vicinanza e posizioni preferite dei job.
- Durante il combattimento, l'interfaccia comunica attacchi, ritmo, cooldown, bersagli ed effetti delle abilità; il giocatore non interviene.
- Testi e interfaccia in italiano e inglese per la prima release.
- Accessibilità da definire con il prototipo; prevedere almeno testo leggibile e ridimensionabile, contrasto adeguato, simboli affiancati ai colori per distinguere classi, keyword e stati (incluso supporto al daltonismo), sottotitoli per ogni contenuto audio e controlli audio separati.
- Salvare ai passaggi sicuri fra nodi e mantenere recuperabili gli sblocchi persistenti.

## 12. Verifica del design e criteri di successo

Il prototipo è sulla strada giusta se:

- il giocatore capisce che gli attacchi avvengono a ritmo autonomo, mentre cooldown e abilità sono automatici;
- cambiare posizioni modifica in modo osservabile chi viene attaccato, le sinergie o le abilità disponibili;
- il party massimo di cinque e la panchina massima di cinque riserve creano una progressione leggibile;
- una ricompensa specie/job dipende in modo comprensibile dall'avversario affrontato e dalla difficoltà;
- le unità ferite, le provviste e i tre slot oggetto producono scelte senza diventare contabilità eccessiva;
- almeno due percorsi sulla mappa producono composizioni, ricompense o livelli di rischio differenti;
- il giocatore comprende il tipo/difficoltà dei nodi, ma trova comunque significativa la scoperta del contenuto;
- le meccaniche dei boss sono anticipate e leggibili, senza richiedere un solo counter;
- una campagna del primo atto può essere completata o persa senza blocchi, e la sconfitta conduce a sblocchi comprensibili;
- gli sblocchi ampliano la varietà senza rendere necessario ripetere run per grindare potenza;
- il giocatore vuole provare una seconda run per un warlord, job, talento, equipaggiamento o percorso diverso.

### Test manuali minimi

- Iniziare con ciascuno dei tre warlord e verificare figli e conoscenze iniziali, senza vantaggi dominanti.
- Cambiare composizione e posizionamento prima dello start; verificare cambi di target, accesso alle retrovie, sinergie e posizioni preferite.
- Verificare che durante la battaglia non ci siano comandi tattici o cambi di formazione.
- Verificare che attacchi e abilità si attivino a ritmo/cooldown autonomi, con bersagli comprensibili.
- Sconfiggere avversari diversi e controllare i punti specie/job, le soglie, il bonus al riposo e la relazione con difficoltà e numero di nemici.
- Creare un goblin e verificare l'ereditarietà di una peculiarità della linea materna acquisita.
- Controllare limite di cinque in party e fino a cinque riserve, cambio di party fra battaglie e gestione della panchina piena.
- Verificare gli oggetti: stessa rarità o inferiore non sostituisce; rarità superiore può essere assegnata o rifiutata.
- Spendere provviste per curare, acquistare dal mercante con tesoro e scegliere eventi con/senza costo.
- Verificare i nodi garantiti dell'atto, il raid/tesoro obbligatorio a metà e l'assenza di composizioni/scenari di battaglia ripetuti nella stessa campagna.
- Completare e perdere l'atto uno; verificare gli sblocchi e il riavvio della run.
- Verificare Hall of Fame dopo la sconfitta e tratti sbloccati con uso abilità/vittorie di warlord.
- Chiudere e riaprire il gioco per verificare salvataggio di run e progressione persistente.
- Verificare testi in italiano e inglese, leggibilità, simboli non dipendenti solo dal colore e impostazioni audio.

## 13. Rischi e mitigazioni

| Rischio | Effetto | Mitigazione |
|---|---|---|
| Autobattaglia passiva o poco leggibile | Senza input durante lo scontro, il giocatore può sentirsi spettatore | Rendere formazione, targeting e sinergie posizionali determinanti; mostrare chiaramente la simulazione e testare prima di produrre molti contenuti |
| Ricompense che creano palla di neve | Più vittorie producono forza sempre crescente e azzerano la sfida | Limitare il party a cinque, tarare il guadagno su difficoltà/numero nemici e verificare le curve per atto |
| Troppe combinazioni specie/job | Aumenta il costo di arte, implementazione e bilanciamento | Definire ruoli attraverso i job e peculiarità limitate per specie; ampliare solo se una combinazione introduce una scelta |
| Sblocchi permanenti obbligatori | La meta-progressione rende le prime run frustranti o il grind necessario | Sbloccare opzioni e vantaggi bilanciati; provare la campagna anche senza grind ripetitivo |
| Risorse ridondanti | Provviste/tesoro/influenza diventano contabilità senza decisioni | MVP con provviste e tesoro; escludere influenza finché non ha un uso distinto |
| Requisiti minimi dei nodi troppo costosi | Cinque élite e cinque riposi per atto, più mercanti, raid ed eventi, richiedono molti contenuti distinti | Usare mappe ramificate authored, riutilizzare regole e set di animazioni; definire quanti incontri unici richiedono davvero variazione |
| Nessuna battaglia ripetuta | La produzione di incontri può superare budget e capacità | Creare varianti di composizione e gimmick mantenendo gli incontri meccanicamente distinti; prototipare un atto prima di impegnarsi sui tre |
| Party e panchina saturi | Le ricompense e la creazione perdono valore se non c'è spazio | Chiarire il cap di cinque riserve e fornire opzioni di sostituzione/abbandono prima di creare o reclutare |
| Posizionamento troppo complicato | Bersagli, prossimità, job preferiti e artefatti possono rendere la schermata indecifrabile | Introdurre una regola posizionale alla volta e mostrare anteprima dei suoi effetti |
| Oggetto “migliore” definito solo dalla rarità | Un drop superiore in rarità può peggiorare la build o forzare una scelta frustrante | Far sì che la regola impedisca l'assegnazione degli oggetti di pari/inferiore rarità, ma lasciare sempre il rifiuto del drop al giocatore |
| Crescita del team oltre i mezzi | Arte e sviluppo superano il budget disponibile | Prototipare con asset gratuiti/placeholder e usare l'Accesso Anticipato per finanziare eventuale produzione successiva |
| Accesso Anticipato percepito come incompleto senza contesto | Il primo atto può sembrare una demo se roadmap e stato non sono chiari | Completare e rifinire il primo atto, comunicare limiti, obiettivi e dipendenza degli atti successivi dai fondi |
| Temi maturi rappresentati in modo incoerente | Il tono implicito rischia di diventare gratuito o confuso | Niente sangue o rappresentazioni esplicite; mantenere cattura e riproduzione fuori campo e il tono principalmente tragico |

## 14. Dettagli da definire durante il prototipo

Le decisioni di direzione sono state definite. Restano da bilanciare o specificare:

- Se il limite della panchina sia esattamente cinque oltre ai cinque schierabili.
- Cadenza esatta di attacco e cooldown, selezione dei bersagli e interazioni fra le quattro classi iniziali.
- Regole di movimento e targeting: priorità, percorso per raggiungere retroguardia e ruolo preciso delle posizioni.
- Quali posizioni preferite cambiano abilità/tratti; quali effetti di vicinanza sono leggibili e sostenibili.
- Quante specie/job, composizioni nemiche non ripetute e ricompense sono sostenibili nel primo atto.
- Valori numerici di progressione/level up, soglie di conoscenza e punti bonus dei riposi.
- Distribuzione concreta sulla mappa dei due mercanti, cinque élite, cinque riposi e nodo tesoro/raid garantito su ogni percorso.
- Frequenza degli eventi casuali e rapporto fra nodi generati e nodi authored.
- Forma e costo dei talenti persistenti e degli sblocchi fra run.
- Numero di pezzi e soglie dei set, e se i bonus appartengono a oggetti, talenti o entrambi.
- Durata dell'atto uno, prezzo dell'Accesso Anticipato e date, da valutare quando esiste una build giocabile.
- Contenuto della Hall of Fame e quali statistiche dei personaggi sconfitti conservare.
- Funzionalità di accessibilità ulteriori rispetto alla base prevista, incluso il sistema di simboli per keyword/classi e opzioni per daltonismo.
- Budget e forma della collaborazione artistica dopo il prototipo.

Non rientrano nel design attuale: diplomazia come percorso alternativo, interventi durante l'autobattaglia, influenza come risorsa e multiplayer. Gli atti due e tre sono obiettivo del gioco completo, ma il loro sviluppo resta dipendente da finanziamenti e validazione dell'atto uno.

## 15. Prossimo passo operativo

Realizzare un prototipo economico con un warlord, uno o due goblin iniziali, party attivo fino a cinque e un piccolo gruppo di riserva. Implementare attacchi a ritmo autonomo, cooldown di abilità, targeting e una prima regola di posizione; testare il Guerriero, il Chierico e lo Stregone contro due composizioni differenti. Prima di ogni battaglia il giocatore compone e posiziona il party; premendo **Start battaglia** osserva la risoluzione senza poter intervenire. Includere progressi a soglia per una specie/job, un riposo che assegna conoscenza bonus, provviste, un oggetto soggetto alla regola di rarità e un goblin creato con peculiarità materna. Collegare poi i sistemi a una mappa dell'atto uno con i nodi garantiti e un boss dalla gimmick anticipata. Se posizionamento, preparazione e progressione non producono scelte interessanti, correggere le regole prima di aumentare il numero di incontri o investire in arte definitiva.
