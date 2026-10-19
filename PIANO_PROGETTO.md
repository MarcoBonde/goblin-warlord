# Goblin Warlord — Piano di progetto

> Documento di pre-produzione. Le decisioni indicate come **proposta** sono una base concreta per il prototipo e potranno essere riviste dopo i primi test.

## 1. Visione

**Goblin Warlord** è un roguelite dark fantasy 2D per pubblico adulto, costruito attorno a una campagna di conquista. Il giocatore guida un warlord goblin attraverso una mappa ramificata di battaglie, insediamenti e città, scegliendo quali avversari affrontare e quali specie e classi assimilare nella propria armata.

La campagna si sviluppa come una run a nodi in stile *Slay the Spire*: il giocatore sceglie il percorso, valuta i rischi e decide come far crescere l'orda fino a un boss o a un obiettivo di conquista. La presentazione degli scontri è laterale, in 2D; il combattimento è un **autobattler tattico**, non un action platform da controllare col pad. La strategia sta nella composizione dell'armata, nelle sinergie e nella scelta del prossimo bersaglio.

### Promessa al giocatore

> Parti con un'orda goblin, conquista una nazione attraverso percorsi diversi e assimila i nemici che sapranno rendere più forte il tuo esercito.

### Pubblico e tono

- Pubblico adulto, interessato a dark fantasy, strategia leggera, roguelite e gestione di una fazione.
- Tono cupo, brutale e talvolta ironico; niente estetica infantile nonostante i protagonisti goblin.
- Temi possibili: guerra, potere, sopravvivenza, successione, vendetta, prigionia, tradimento e conseguenze della violenza.
- La maturità deriva da scrittura, atmosfera e dilemmi, non dalla necessità di rappresentare esplicitamente ogni atto violento.
- Le razzie possono essere una scelta del giocatore, ma devono avere costi e conseguenze nel mondo: non essere una fonte di ricompense priva di contraccolpi.

## 2. Genere e formato

- **Genere:** roguelite tattico a squadre, con mappa ramificata, progressione dell'armata e autobattaglie.
- **Prospettiva:** 2D laterale.
- **Struttura:** campagna per giocatore singolo presentata come una run su mappa a nodi; ogni nodo porta a uno scontro, un evento, una scelta o un obiettivo.
- **Combattimento:** autobattler; le unità combattono autonomamente e il giocatore costruisce la composizione e la formazione prima dello scontro.
- **Piattaforma iniziale proposta:** PC.
- **Tecnologia:** Godot 4, progetto 2D.
- **Modalità iniziale:** giocatore singolo, offline. Il multiplayer non fa parte del progetto attuale; l'architettura non dovrà precludere una futura modalità cooperativa, ma non si implementeranno ora networking, lobby o sistemi online.

## 3. Pilastri di design

1. **La campagna è una conquista.** Ogni percorso porta a territori, nemici e opportunità diversi; il giocatore sceglie come scalare la nazione.
2. **L'armata cresce assimilando i vinti.** Specie e classi nemiche possono diventare parte della forza goblin, aprendo nuove combinazioni.
3. **La preparazione conta più dei riflessi.** Composizione, formazione, classi e sinergie determinano l'esito dell'autobattaglia.
4. **Il potere ha un prezzo.** Conquistare, terrorizzare, allearsi o risparmiare cambia le risorse e la risposta del mondo.
5. **Una campagna deve essere rigiocabile.** Itinerari, bersagli e strategie di conquista diversi producono run differenti senza richiedere contenuti infiniti.

## 4. Ciclo di gioco

### Ciclo della campagna

1. **Scegli un itinerario** sulla mappa ramificata: pattuglie, mostri, villaggi, città, eventi e punti di rifornimento presentano rischi e ricompense diversi.
2. **Prepara l'armata** con le unità disponibili, disponendole in formazione e sfruttando le sinergie fra specie e classi.
3. **Affronta l'incontro** nell'arena laterale: le unità combattono automaticamente secondo le loro abilità e i loro ruoli.
4. **Conquista e assimila:** dopo una vittoria scegli cosa ottenere, per esempio reclute di una specie sconfitta, accesso a un job, risorse, equipaggiamento o un vantaggio temporaneo.
5. **Gestisci le conseguenze:** ferite, risorse, allarme e reazione delle fazioni influenzano le opzioni successive.
6. **Scegli il prossimo bersaglio** e continua verso il boss regionale e l'obiettivo finale della campagna.
7. **Concludi la campagna** con una vittoria o una sconfitta; le run successive possono offrire percorsi e combinazioni differenti.

La crescita dell'armata avviene soprattutto durante la campagna, tramite conquiste e assimilazione, non tornando a una base fra spedizioni separate. Un eventuale livello strategico persistente fra campagne potrà essere valutato dopo il prototipo, ma non è necessario per il ciclo principale.

## 5. Sistemi principali

### 5.1 Specie, classi e assimilazione

- L'armata parte prevalentemente goblin. Le unità sono descritte da **specie** (identità e caratteristiche innate) e **classe/job** (ruolo e abilità tattica).
- Le vittorie contro eserciti, mostri e insediamenti possono sbloccare o aggiungere al roster nuove specie e classi. L'assimilazione può rappresentare reclutamento, diserzione, resa, imposizione del nuovo ordine o appropriazione di tecniche: il contesto dipende dalla fazione e dalle scelte del giocatore.
- Una vittoria non deve trasformare automaticamente ogni nemico in un'unità reclutabile. Ricompense e accesso al roster sono espliciti, limitati e bilanciati.
- Specie e classi possono combinarsi quando ha senso nel mondo; una specie non coincide con un job. Un troll può essere bruto, guardia o lanciatore; una specie minuta può specializzarsi in supporto o sabotaggio.
- Tratti, statistiche e abilità devono creare sinergie e compromessi, non una progressione di potenza sempre crescente.
- Eventuali legami dinastici o eredi possono rimanere contenuto narrativo o una meccanica futura secondaria; non sono il ciclo centrale della campagna né prerequisito per il prototipo.

**Classi/job MVP proposti**

- **Bruto:** combattente resistente in prima linea.
- **Predone:** danno rapido e pressione sui bersagli vulnerabili.
- **Sciamano:** supporto, cura limitata o potenziamenti.

**Specie e classi successive possibili**

- Specie: goblin, umano, orco, troll, bestia corrotta.
- Job: tiratore, sabotatore, domatore, campione, stregone del sangue.

Le classi descrivono il ruolo tattico, mentre la specie, i tratti e l'equipaggiamento aggiungono variazione. Ogni unità deve restare leggibile senza obbligare il giocatore a studiare decine di statistiche.

### 5.3 Combattimento autobattler

- Formazione iniziale su due file: **prima linea** e **retroguardia**.
- Le unità scelgono bersaglio e azione in base a regole semplici e visibili.
- Statistiche iniziali: salute, attacco, velocità, armatura e portata.
- Ogni classe ha un'abilità distintiva; il capitano può avere un ordine speciale con usi limitati.
- Effetti di stato iniziali: sanguinamento, stordimento breve, protezione e ispirazione.
- Il giocatore può decidere se attivare manualmente il potere del capitano o impostare una condizione semplice.
- Nessun RNG opaco: mostrare sempre salute, bersagli, portate e motivi principali delle abilità.

### 5.4 Progressione durante la campagna

- Nuove specie e classi/job assimilati agli avversari sconfitti, aggiunti al roster o sbloccati come opzioni.
- Esperienza e miglioramenti temporanei per le unità superstiti.
- Equipaggiamento trovato o sottratto ai nemici.
- Ricompense alternative, così ogni nodo è una decisione e non solo un combattimento.
- Ferite o debuff temporanei rendono importante la gestione della squadra.
- La perdita di unità o risorse deve rendere importante la gestione dell'armata, senza rendere impossibile il proseguimento dopo un singolo scontro sfortunato.
- La sconfitta termina la campagna corrente; il prototipo può conservare sblocchi fra campagne solo se necessari a testare varietà e rigiocabilità.

### 5.5 Razzie, risorse e fazioni

**Risorse iniziali proposte**

- **Rottami e metallo:** equipaggiamento e fortificazioni.
- **Provviste:** mantenimento dell'armata e recupero dei feriti.
- **Influenza:** accordi, reclutamento e politica.
- **Tesoro:** equipaggiamento, servizi e vantaggi acquistabili durante la campagna.

Le razzie possono fornire risorse, unità e accesso a nuove classi, ma aumentano allarme, ostilità o rischio di rappresaglia. Le alternative includono caccia ai mostri, scambio, tributi, accordi temporanei e sottomissione politica. Queste strategie possono tradursi in rami, nodi e ricompense differenti sulla mappa.

Le fazioni possono ricordare eventi importanti in forma semplice: una comunità saccheggiata può alzare le difese o allearsi con un rivale; una comunità risparmiata può commerciare o chiedere aiuto. Per l'MVP bastano due variabili per regione, come **paura** e **fiducia**.

### 5.6 Mappa della campagna e metodi di conquista

- La mappa è organizzata in livelli di nodi ramificati: ogni livello rappresenta una zona o una fase dell'avanzata.
- Tipi di nodo: pattuglia/esercito, mostro, villaggio, città o fortezza, boss, evento, rifornimento e opportunità politica.
- I nodi mostrano informazioni sufficienti per una scelta informata, come tipologia di nemico, minaccia e ricompensa probabile; non rivelano necessariamente ogni dettaglio.
- Le città e i boss sono obiettivi importanti che possono chiudere un ramo, cambiare lo stato della regione o sbloccare l'accesso alla zona successiva.
- Il giocatore può orientare la conquista verso strategie diverse. Proposte: **forza militare** (vittorie dirette e bottino), **terrore e razzie** (guadagni rapidi con più allarme e resistenza), **accordi e sottomissione** (meno combattimenti ma richieste e vincoli). La caccia ai mostri può inoltre fornire potere e unità speciali.
- Nel MVP queste strategie si esprimono con scelte ed effetti sui nodi, non con un complesso simulatore geopolitico.

## 6. Struttura narrativa

### Premessa

Un warlord goblin avvia la conquista di una nazione frammentata fra signori umanoidi, mostri e città rivali. L'orda parte piccola: ogni vittoria può portare nuovi combattenti e tecniche, mentre ogni scelta determina quali nemici affrontare e quale prezzo pagare per avanzare. La campagna racconta l'ascesa del warlord attraverso le regioni fino al confronto che deciderà il destino del territorio.

### Temi e conflitti

- Conquista contro alleanza e sottomissione.
- Sopravvivenza contro conquista.
- Paura come strumento di governo e fonte di ribellione.
- Assimilazione, identità e conflitti fra le specie dell'orda.
- Le conseguenze delle razzie per chi le compie e per chi le subisce.

### Presentazione sostenibile

- Eventi testuali brevi con due o tre scelte.
- Ritratti e battute distintive per capitani, rivali e personaggi ricorrenti.
- Nessun albero di dialogo esteso nel prototipo.
- Tono maturo senza affidarsi a shock gratuito: le conseguenze si vedono nelle scelte, nelle fazioni e nello stato dell'orda.

## 7. Ambito: MVP e contenuti esclusi

### MVP: fetta verticale giocabile

- Una campagna breve a nodi ramificati con partenza, almeno due percorsi possibili, un boss regionale e una conclusione.
- Una nazione/area, con nodi di pattuglia o esercito, villaggio, città/fortezza, evento e rifornimento.
- Un'orda iniziale goblin e una squadra fino a tre unità.
- Tre job iniziali (bruto, predone e sciamano) e almeno una specie nemica assimilabile, per dimostrare la separazione fra specie e classe.
- Un roster che consente di selezionare e comporre la squadra fra gli incontri; l'assimilazione aggiunge unità o opzioni di reclutamento dopo specifiche vittorie.
- Tre tipi di nemici comuni, un incontro di villaggio, uno di città/fortezza e un boss.
- Almeno due approcci di conquista, come forza militare e razzia/terrore, con differenze comprensibili in rischi o ricompense.
- Un evento con una scelta non militare e conseguenze sulla campagna.
- Poche ricompense: nuove unità/job, provviste e un equipaggiamento con varianti essenziali.
- Vittoria e sconfitta della campagna; ricominciare una campagna per provare un altro itinerario.
- Salvataggio locale dei dati essenziali della campagna.
- Asset provvisori coerenti e leggibili; non serve animazione definitiva.

### Fuori ambito per l'MVP

- Combattimento action controllato direttamente, platforming e fisica di precisione.
- Multiplayer, cooperativa, modalità online o servizi server. Il multiplayer resta una possibilità remota da considerare solo dopo il rilascio del single-player; non va progettato o implementato nell'MVP.
- Mondo aperto, campagne molto lunghe o mappe generate proceduralmente complesse.
- Decine di classi, razze, biomi, boss o risorse.
- Dialoghi doppiati e cinematiche.
- Sistemi genealogici complessi.
- Gestione esplorabile della base.

## 8. Roadmap di produzione

### Fase 0 — Fondamenta

- Creare il progetto Godot 4 e fissare risoluzione, input e convenzioni.
- Scegliere stile visivo provvisorio, palette e formato dei dati.
- Definire il foglio di una unità e una bozza delle regole di combattimento.

**Uscita:** progetto avviabile, schermata iniziale e scena arena vuota.

### Fase 1 — Prototipo di combattimento

- Implementare unità, bersagli, attacchi automatici, salute e vittoria/sconfitta.
- Separare definizioni di specie e job e verificare combinazioni di unità.
- Aggiungere tre job e una formazione a due file.
- Rendere visibili bersagli, portate, danni e abilità.

**Uscita:** una battaglia ripetibile che permette di confrontare almeno due composizioni e mostra come un'unità assimilata cambia la squadra.

### Fase 2 — Spedizione e ricompense

- Aggiungere la mappa della campagna con nodi ramificati, bivio, evento e premio.
- Salvare lo stato della campagna mentre si procede.
- Aggiungere incontri di pattuglia/esercito, villaggio, città/fortezza e boss con ricompense distinte.
- Implementare la prima scelta di assimilazione e almeno due approcci di conquista.

**Uscita:** una campagna completa, dalla scelta del percorso alla conquista o alla sconfitta.

### Fase 3 — Roster e progressione della campagna

- Consolidare il roster fra gli incontri e l'accesso a specie/job assimilati.
- Collegare risorse, recupero, equipaggiamento e scelta della squadra fra nodi.
- Aggiungere recupero, equipaggiamento e scelta della squadra fra i nodi, senza interrompere l'avanzata con un ritorno obbligatorio alla base.

**Uscita:** ciclo completo di campagna, crescita dell'armata e riavvio con un nuovo percorso.

### Fase 4 — Vertical slice e tono

- Sostituire i placeholder essenziali con arte, animazioni, effetti e audio coerenti.
- Aggiungere eventi narrativi e conseguenze delle scelte di conquista e assimilazione.
- Verificare leggibilità, durata, difficoltà e chiarezza dell'interfaccia.

**Uscita:** una versione breve che comunica la promessa del gioco e può essere testata esternamente.

### Fase 5 — Espansione controllata

- Aggiungere regioni, nemici, eventi, equipaggiamento e tratti solo se i test indicano bisogno di maggiore varietà.
- Aggiungere nuove regioni, modi di conquista e ulteriori opzioni di gestione solo quando i sistemi base sono verificati.
- Preparare accessibilità, localizzazione, opzioni e distribuzione.

**Uscita:** contenuti aggiuntivi basati su sistemi già verificati, non nuovi sistemi in parallelo.

## 9. Architettura Godot proposta

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
    units/
    traits/
    enemies/
    equipment/
    events/
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
│   └── BattleScreen
│       ├── Battlefield
│       └── BattleHUD
└── CampaignState
```

### Responsabilità

- **CampaignManager:** stato della campagna, nodo corrente, percorso, fazioni e condizioni di vittoria/sconfitta.
- **RosterManager:** unità disponibili, specie/job assimilati e composizione selezionata.
- **BattleController:** avvio, avanzamento e conclusione di uno scontro.
- **UnitDefinition / SpeciesDefinition / JobDefinition:** dati statici di unità, specie e classi.
- **TraitDefinition / EquipmentDefinition:** modificatori e regole dichiarative.
- **RouteNodeDefinition / EncounterDefinition / FactionDefinition:** nodi della mappa, incontri e fazioni.
- **SaveManager:** serializzazione dei dati persistenti e versione del salvataggio.
- **ScreenRouter:** cambio fra mappa, incontro, battaglia e risultati.

Evitare un manager globale che contenga ogni regola. Non introdurre astrazioni di rete o dipendenze multiplayer: mantenere dati e logica separati quanto basta perché la modalità single-player sia chiara e semplice da estendere in futuro.

## 10. Interfaccia e accessibilità

- Rendere evidente chi è in prima linea, chi sta attaccando e quanto è vicina la sconfitta.
- Mostrare statistiche dettagliate su richiesta, senza sovraccaricare la schermata di battaglia.
- Distinguere le squadre anche con forme e icone, non solo con il colore.
- Consentire di mettere in pausa gli scontri e rallentarli.
- Includere volume separato per musica ed effetti, riduzione di flash/scuotimenti e testo leggibile.
- Salvare dopo eventi importanti e ai passaggi sicuri fra nodi della campagna.

## 11. Verifica del design e criteri di successo

Il prototipo funziona se:

- una campagna si può iniziare, completare o fallire senza blocchi;
- almeno due percorsi conducono a incontri e ricompense diversi;
- una battaglia è comprensibile guardandola e leggendo le informazioni dell'interfaccia;
- cambiare composizione o formazione produce differenze tattiche osservabili;
- assimilare una nuova specie o un nuovo job cambia concretamente le opzioni di composizione;
- almeno una scelta di conquista offre un beneficio immediato e una conseguenza successiva riconoscibile;
- il giocatore può scegliere il prossimo bersaglio e capire i principali rischi e premi;
- il giocatore capisce cosa può fare prima di impegnarsi in un sistema più ampio.

### Test manuali minimi

- Avviare una campagna, scegliere ognuno dei percorsi disponibili e arrivare al boss.
- Vincere uno scontro per assimilare una nuova unità/job e verificare che compaia nel roster.
- Completare una campagna e ripeterla scegliendo un differente approccio di conquista.
- Perdere uno scontro e verificare che la campagna termini o applichi la penalità prevista.
- Chiudere e riaprire il gioco per verificare caricamento e salvataggio.
- Provare una squadra composta da unità della stessa specie e una squadra con specie/job diversi.
- Verificare che un tratto non applicabile o una risorsa insufficiente non causi errori o ricompense inconsistenti.

## 12. Rischi e mitigazioni

| Rischio | Effetto | Mitigazione |
|---|---|---|
| Troppi generi insieme | Progetto eccessivo prima di avere una campagna divertente | Mantenere l'autobattler come unica modalità di combattimento e una sola nazione nell'MVP |
| Combattimento automatico passivo | Il giocatore non sente di influire sull'esito | Formazione, scelta di bersagli/ordini limitati, abilità del capitano e informazioni chiare |
| Assimilazione sbilanciata | Una specie o un job diventa sempre la scelta corretta | Ricompense situazionali, limiti di squadra e sinergie con compromessi |
| Percorsi di conquista cosmetici | Le scelte sulla mappa non cambiano la campagna | Differenziare incontri, rischi, ricompense e reazioni delle fazioni |
| Razzie senza conseguenze | Il tema morale diventa cosmetico e la scelta è ovvia | Collegare la violenza a paura, rappresaglie, reclutamento e diplomazia |
| Contenuti narrativi troppo ampi | Scrittura e localizzazione rallentano il prototipo | Eventi brevi e riutilizzabili; ampliare dopo i test |
| Produzione artistica costosa | Mancanza di contenuti visivi sufficienti | Usare sagome leggibili e palette coerente; limitare le animazioni iniziali |

## 13. Decisioni da prendere dopo il prototipo

Non sono prerequisiti per iniziare:

- Quanto spazio dare a ordini tattici o abilità attivabili durante l'autobattaglia.
- Quante regioni e nazioni compongono la campagna completa.
- Quanto è punitiva la sconfitta e quali eventuali sblocchi persistono fra campagne.
- Quanto profondamente le fazioni persistono e reagiscono alle conquiste.
- Se inserire una progressione persistente fra campagne.
- Stile artistico definitivo e grado di rappresentazione esplicita della violenza.
- Prezzo, piattaforme aggiuntive e strategia di rilascio.
- Se, dopo il rilascio single-player e solo se ha senso per il design, esplorare una modalità multiplayer/cooperativa. Non rientra nella roadmap attuale.

## 14. Prossimo passo operativo

Il primo prototipo deve dimostrare soltanto questo: **scegliere un percorso sulla mappa, preparare tre goblin con job distinti, osservare un'autobattaglia laterale, sconfiggere un gruppo nemico, assimilare una nuova specie o classe e scegliere il nodo successivo**. La fetta verticale completa poi una piccola campagna con villaggio, città/fortezza e boss. Solo dopo aver verificato questo ciclo si amplia il numero di regioni, fazioni e metodi di conquista.
