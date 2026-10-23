# Goblin Warlord — Piano di progetto

> Documento di pre-produzione aggiornato con le decisioni attuali, incluse le risposte alla terza valutazione. I dettagli indicati come da bilanciare restano soggetti a prototipazione e playtest.

## 1. Visione

**Goblin Warlord** è un roguelite dark fantasy 2D per pubblico adulto, costruito attorno a una campagna di conquista. Il giocatore sceglie un signore della guerra goblin e guida una piccola armata in un'unica marcia attraverso il mondo fino alla capitale, conquistando territori e sbloccando specie e classi da integrare nell'orda.

La campagna si sviluppa in tre atti su una mappa di nodi in stile *Slay the Spire*: il giocatore legge tipo e difficoltà del nodo, sceglie il percorso e affronta un boss alla fine di ogni atto; il boss del terzo atto si trova nella capitale ed è l'obiettivo conclusivo. La presentazione degli scontri è laterale, in 2D. Il combattimento è **a turni**, con scelta di azioni e bersagli simile a un gioco di ruolo tattico; può anche essere automatizzato, mantenendo la battaglia automatica come opzione. La strategia sta nella composizione e nelle posizioni della squadra, nella scelta delle azioni, nell'equipaggiamento e nell'anticipazione dei bersagli nemici.

### Promessa al giocatore

> Scegli uno dei signori della guerra, prepara una squadra di massimo cinque goblin e marcia fino alla capitale: in battaglia puoi decidere personalmente azioni e bersagli oppure affidarti all'automazione, mentre percorso e vittorie determinano le specie, classi, tratti ed equipaggiamenti disponibili.

### Pubblico e tono

- Pubblico adulto, interessato a dark fantasy, strategia leggera e roguelite.
- Tono principalmente tragico, con momenti di stupidità e umorismo goblin soprattutto negli eventi.
- La fantasia centrale è guidare un'armata goblin spietata fino alla conquista del mondo; non esistono percorsi politici o diplomatici alternativi all'obiettivo.
- Violenza senza sangue esplicito: attacchi e magie fanno intuire il danno senza rappresentarlo graficamente.
- Temi maturi e rapporti con persone catturate restano impliciti o fuori campo; la riproduzione non viene mostrata. La componente di eredità è trattata come sistema di gioco e di lore, senza scene esplicite.

## 2. Genere e formato

- **Genere:** roguelite tattico a squadre, con mappa ramificata, progressione dell'armata e combattimento a turni automatizzabile.
- **Prospettiva:** 2D laterale.
- **Struttura:** campagna single-player in tre atti; un'unica avanzata ramificata verso la capitale, con un boss alla fine di ogni atto.
- **Combattimento:** sistema a turni con scelta manuale di azione e bersaglio per ogni goblin; battaglia automatica opzionale con scelte basate sulla personalità dell'unità. Tempi di ricarica e azioni hanno regole comuni e leggibili.
- **Piattaforma iniziale proposta:** PC.
- **Tecnologia:** Godot 4, progetto 2D.
- **Lingue previste:** italiano e inglese.
- **Modalità:** giocatore singolo, offline. Nessun multiplayer nel progetto attuale; non va pianificato né implementato.

### 2.1 Glossario IT/EN

Il termine italiano è quello da usare nei testi di progetto e, salvo vincoli tecnici, nell'interfaccia. Il termine inglese è la traduzione di riferimento per la localizzazione. Il nome inglese può comparire alla prima occorrenza o nella documentazione tecnica, ma non va alternato liberamente al termine italiano.

| Termine italiano canonico | Termine inglese | Significato e uso |
|---|---|---|
| Campagna | Campaign | Un tentativo completo di conquista attraverso gli atti; evitare di alternare con *run*. |
| Atto | Act | Una sezione della campagna che termina con un boss. |
| Nodo | Node | Tappa selezionabile sulla mappa della campagna. |
| Incontro | Encounter | Una battaglia o situazione definita all'interno di un nodo. |
| Signore della guerra | Warlord | Goblin scelto all'inizio, con rosa iniziale e artefatto distintivi. |
| Unità | Unit | Singolo goblin o nemico presente nella campagna o in battaglia. |
| Rosa | Roster | Insieme delle unità disponibili nella campagna, inclusa la squadra e la panchina. |
| Squadra | Party | Fino a cinque unità selezionate per uno scontro. |
| Panchina | Bench | Riserve non schierate, fino a cinque unità. |
| Classe | Class | Ruolo fisso di un goblin, che determina attacchi e abilità; non usare *job*. |
| Specie materna | Maternal species | Specie da cui il goblin eredita una passiva; usare *specie* per la categoria generale. |
| Passiva | Passive | Effetto sempre attivo della classe, della specie o di un tratto. |
| Tratto | Trait | Modificatore sbloccabile che cambia una capacità o una regola dell'unità. |
| Attacco base | Basic attack | Attacco sempre disponibile durante il turno dell'unità. |
| Abilità ordinaria | Core ability | Abilità con tempo di ricarica breve o medio; sostituisce l'espressione informale *abilità spam*. |
| Abilità suprema | Ultimate ability | Abilità potente con tempo di ricarica lungo; in modalità manuale la sceglie il giocatore. |
| Tempo di ricarica | Cooldown | Turni che devono trascorrere prima che un'abilità sia di nuovo disponibile. |
| Combattimento a turni | Turn-based combat | Modalità principale: il giocatore sceglie azioni e bersagli nei turni della squadra. |
| Battaglia automatica | Auto-battle | Opzione che affida azioni e bersagli all'automazione basata sulla personalità dell'unità. |
| Modalità manuale | Manual mode | Il giocatore sceglie azione e bersaglio per ogni unità. |
| Turno | Turn | Finestra d'azione alternata fra la squadra e i nemici, secondo le regole da definire. |
| Bersaglio | Target | Unità selezionata per ricevere un attacco o un'abilità. |
| Portata | Range | Insieme dei bersagli raggiungibili da un attacco o un'abilità. |
| Mischia | Melee | Attacco ravvicinato, normalmente limitato alla prima linea nemica. |
| Attacco a distanza | Ranged attack | Attacco che può raggiungere la retroguardia, salvo provocazioni o altri effetti. |
| Provocazione | Taunt | Effetto che forza o modifica la scelta del bersaglio. |
| Effetto di stato | Status effect | Condizione temporanea mostrata con un'icona vicino alla salute dell'unità. |
| Potenziamento | Buff | Effetto di stato positivo che migliora un'unità. |
| Indebolimento | Debuff | Effetto di stato negativo che ostacola un'unità. |
| Punti salute | Health points (HP) | Risorsa che misura quanto danno un'unità può subire prima di cadere. In interfaccia usare **Salute**. |
| Scudo | Shield | Valore temporaneo che assorbe danni prima dei punti salute. |
| Artefatto del signore della guerra | Warlord artifact | Oggetto iniziale distintivo che modifica lo stile o la progressione della campagna. |
| Provviste | Supplies | Risorsa che cura automaticamente la squadra durante il viaggio fra nodi. |
| Tesoro | Treasure | Risorsa usata per acquisti ed eventi; può essere ottenuta mandando una riserva a caccia. |
| Élite | Elite encounter | Incontro di difficoltà e ricompensa superiori a una battaglia normale. |
| Boss | Boss | Incontro chiave con una meccanica distintiva anticipata al giocatore. |
| Razzia | Raid | Nodo senza combattimento che offre provviste, cure e una rara possibilità di sbloccare una specie materna. |
| Accampamento | Camp | Nodo di riposo che cura o potenzia la squadra. |
| Bottino | Loot | Oggetti o risorse ottenuti dopo un incontro. |
| Meta-progressione | Meta-progression | Sblocchi persistenti fra campagne, distinti dalla crescita delle unità nella campagna corrente. |
| Roguelite | Roguelite | Genere con campagne ripetibili e sblocchi persistenti fra i tentativi. |
| Albo degli eroi | Hall of Fame | Archivio commemorativo dei goblin migliori, senza sopravvivenza dei personaggi fra campagne. |
| Accesso Anticipato | Early Access | Pubblicazione di una versione giocabile prima del completamento dell'intero progetto. |

## 3. Pilastri di design

1. **La campagna è una marcia verso la capitale.** Ogni atto avvicina al boss e all'obiettivo finale.
2. **L'armata cresce imparando dai nemici.** Le vittorie sbloccano unità, classi e tratti tramite progressi legati alle tipologie nemiche; la discendenza dei nuovi goblin può ereditare una passiva della specie materna.
3. **La tattica è leggibile e modulabile.** Il combattimento a turni permette di scegliere azioni e bersagli; l'automazione resta un'opzione per chi preferisce delegare le decisioni.
4. **La squadra è piccola e personale.** Ogni membro è un individuo con specie, classe, attributi ed equipaggiamento.
5. **Le campagne sbloccano opzioni.** Nuovi signori della guerra, classi iniziali, passive, talenti e oggetti ampliano le possibilità dei tentativi successivi.

## 4. Ciclo di gioco

### Ciclo della campagna

1. **Scegli un signore della guerra:** tre archetipi iniziali sono orientati rispettivamente al combattimento ravvicinato, agli attacchi a distanza e alla magia. Ognuno offre una rosa iniziale e un artefatto distintivo, senza rendere un'opzione obbligatoriamente superiore.
2. **Scegli il prossimo nodo** conoscendone il tipo e la difficoltà, ma non il contenuto preciso: battaglia, élite, boss, tesoro, evento casuale o razzia; la mappa include anche riposi e mercanti.
3. **Prepara la squadra** prima di ogni scontro: scegli fino a cinque combattenti da una rosa che può includere fino a cinque riserve, quindi definisci formazione e posizioni.
4. **Combatti a turni:** scegli azione e bersaglio per ogni goblin oppure attiva l'automazione, regolabile per usare solo le abilità ordinarie o anche le ultimate; posizioni, portata e provocazioni determinano i bersagli validi.
5. **Ottieni ricompense** pertinenti ai nemici affrontati: il conteggio delle tipologie sconfitte avanza soglie per sbloccare unità o migliorarne livello/tratti; difficoltà e composizione influenzano le ricompense.
6. **Gestisci salute e risorse:** i punti salute persi restano fino a una cura; le provviste curano automaticamente la squadra durante il viaggio fra nodi, mentre i luoghi di riposo forniscono recupero extra. Usa il tesoro da mercanti o eventi.
7. **Avanza attraverso i tre atti**, sconfiggi i rispettivi boss e punta alla capitale e al boss finale.
8. **Vinci o perdi la campagna.** Una sconfitta conclude il tentativo; gli sblocchi persistenti ampliano le opzioni per i tentativi successivi.

## 5. Sistemi principali

### 5.1 Personaggi, specie, classi e discendenza

- La squadra schierata ha un massimo di **cinque personaggi**; la rosa può contenere fino a **cinque riserve aggiuntive**. Si può modificare la squadra prima di ogni battaglia. Le classi assegnate ai goblin sono fisse: non è previsto cambiare liberamente classe a un'unità già creata.
- All'inizio il signore della guerra scelto determina la rosa disponibile e le conoscenze iniziali; il giocatore sceglie i goblin di partenza fra le opzioni previste per quell'archetipo. I tre archetipi tematici sono combattimento ravvicinato, attacchi a distanza e magia; ciascuno ha un artefatto distintivo, con vantaggi da bilanciare.
- I personaggi sono individui persistenti, non pedine fungibili. Ognuno ha nome/identità, specie (linea materna), classe, salute e attributi: **Forza, Destrezza, Costituzione, Intelligenza, Saggezza e Carisma**. Gli attributi contribuiscono a statistiche e requisiti/effetti di classi ed equipaggiamento, da definire nel prototipo.
- Le specie materne conferiscono una passiva comune alle classi, che modifica attributi o capacità del goblin. Esempi da valutare: rigenerazione a turno, slot speciale aggiuntivo, doppia arma o riduzione del tempo di ricarica dell'abilità suprema. Le passive devono essere utili con più classi: non è richiesta parità competitiva perfetta, ma nessuna scelta dovrebbe risultare inutile o obbligatoria.
- L'assimilazione è un reclutamento forzato astratto: non si mostra come avviene, ma si ottengono nuove **conoscenze** di specie/classi, come se l'orda imparasse dai vinti.
- Le vittorie fanno avanzare una progressione per tipologia di nemico sconfitto. Le soglie iniziali candidate sono **5, 10, 15 e 20 nemici**: possono sbloccare una nuova unità o migliorarne livello/tratto. L'associazione precisa fra tipologia, soglia e ricompensa, nonché eventuali bonus da riposo, va definita e provata nel prototipo.
- Le ricompense dipendono da tipo e difficoltà dell'incontro e dai nemici affrontati; incontri più difficili possono avanzare più progressioni, senza premiare soltanto il numero grezzo di nemici.
- I goblin possono salire di livello durante la campagna; anche livello e qualità delle ricompense possono crescere con la progressione, mantenendo i valori numerici contenuti e leggibili.
- I goblin creati durante la campagna possono ereditare la passiva della specie materna acquisita. La cattura e la riproduzione restano implicite e fuori campo: non si mostrano rapporti o atti sessuali. Una razzia può occasionalmente sbloccare una nuova linea materna o una specie, come ricompensa narrativa e di progressione.
- I nodi dedicati permettono di creare nuovi goblin usando specie e classi sbloccate. Il giocatore può mandare una riserva a caccia per ottenere tesoro: il goblin viene perso definitivamente; è anche un modo per liberare uno slot, con ricompensa da bilanciare.
- I rapporti di forza e le caratteristiche specie/classe devono essere leggibili e creare scelte; non ogni combinazione richiede una regola o un'animazione esclusiva.

**Classi:** il documento [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) raccoglie kit proposti per 28 classi, come banca di design e non come promessa di implementazione integrale. Il tutorial/prototipo usa quattro ruoli: **Guerriero** (armatura, difesa e provocazione), **Ranger** (attacco a distanza), **Stregone** (attacco magico) e **Chierico** (cura). Le abilità del catalogo sono spunti da adattare al combattimento a turni; le ultimate non si attivano automaticamente in modalità manuale.

**Specie di partenza e progressione:** il roster iniziale è goblin; nuove specie e peculiarità si scoprono affrontando nemici e attraverso eventi. Limitare il numero di specie/classi implementati per l'Accesso Anticipato in base agli asset e al tempo disponibili.

### 5.2 Combattimento a turni e automazione

- Prima dello scontro, il giocatore sceglie fino a cinque membri dalla rosa, che può avere fino a cinque riserve, e dispone la formazione. La modalità manuale è quella di riferimento: nel proprio turno sceglie per ogni goblin attacco base o abilità disponibile e il bersaglio.
- L'attacco base è sempre disponibile. Le abilità ordinarie hanno tempi di ricarica brevi, inizialmente nell'ordine di **1-2 turni**; le abilità supreme hanno tempi più lunghi, indicativamente **3-5 turni o più**. Valori e ritmo vanno verificati col prototipo.
- Il gioco conserva anche l'opzione di battaglia automatica: l'intelligenza artificiale seleziona azione e bersaglio secondo una personalità/priorità definita per ciascun goblin. L'automazione può essere impostata per usare solo le abilità ordinarie oppure anche quelle supreme; il giocatore può scegliere in anticipo il livello di automazione.
- Un'abilità si attiva solo se è pronta e trova un bersaglio valido entro la propria portata; se non lo trova, non viene usata. Le regole precise sul tempo di ricarica e sul turno di riattivazione restano da testare.
- Il giocatore sceglie normalmente i bersagli. Provocazione e altri effetti di controllo possono forzare o modificare il bersaglio; portata e posizione limitano le opzioni disponibili.
- Gli attacchi base in mischia possono colpire solo nemici in prima linea; gli attacchi a distanza possono raggiungere qualunque nemico, salvo provocazione o effetti analoghi. Ogni abilità specifica una propria portata e un insieme di bersagli validi.
- Le regole di targeting valgono anche per i nemici. Nella modalità a turni l'interfaccia anticipa il bersaglio nemico e mostra una stima del danno previsto; questa previsione non viene calcolata nell'autobattle.
- Posizioni e formazione determinano accessibilità dei bersagli, protezione della retroguardia e possibili sinergie di vicinanza. Posizioni preferite o modificatori ulteriori si introducono solo dopo aver validato le regole base.
- Il kit iniziale si basa su [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md), adattato al nuovo sistema: **Guerriero** (armatura, difesa e provocazione), **Ranger** (attacco a distanza), **Stregone** (attacco magico) e **Chierico** (Fiamma sacra e Cura; l'abilità suprema crea uno scudo di squadra invece di resuscitare). Le cure oltre la salute massima si convertono in scudo.
- Nessuna classe può resuscitare unità durante il combattimento. Questo limita la dipendenza obbligatoria dal Chierico e dà peso alle perdite. Un evento di campagna può eccezionalmente riportare in vita un caduto; se non ci sono caduti, lo stesso evento offre un beneficio alternativo.
- Tutti i buff, debuff e stati sono rappresentati con icone vicino a nome e barra della salute. Un menu di pausa permette di consultare nel dettaglio effetti e regole dei nemici.
- Le statistiche includono salute e sei attributi (**Forza, Destrezza, Costituzione, Intelligenza, Saggezza e Carisma**); valori derivati come attacco e difesa vanno mantenuti leggibili e definiti nel prototipo.
- Il combattimento deve comunicare turni, azioni, cooldown, portata, bersagli, previsioni di danno ed effetti senza richiedere calcoli esterni o microgestione dell'interfaccia.

### 5.3 Progressione durante e fra le campagne

- Durante una campagna, le vittorie fanno avanzare contatori per tipologia di nemico sconfitta. Le soglie candidate **5/10/15/20** sbloccano o migliorano goblin, livello o tratti; l'associazione precisa fra tipologia, soglia e ricompensa va prototipata.
- Le unità ottenute e i miglioramenti sono legati alle famiglie di nemici affrontate, così la scelta del percorso influenza il roster. Gli artefatti dei warlord possono alterare le soglie o le possibilità di ottenere goblin.
- I goblin possono salire di livello durante la campagna; i valori e le ricompense crescono in modo controllato e leggibile.
- Eventi, razzie e nodi di creazione possono fornire risorse, guarigione, nuovi goblin o nuove linee/specie materne. Le razzie sono nodi dedicati senza combattimento: forniscono provviste e una piccola cura; al massimo una volta per atto possono sbloccare una linea materna/specie rara.
- Le unità mantengono gli HP persi finché non ricevono cure. Durante il viaggio fra un nodo e il successivo le provviste curano automaticamente; i luoghi di riposo forniscono recupero aggiuntivo. Quantità e frequenza restano da bilanciare.
- Il giocatore può mandare una riserva a caccia per ottenere tesoro: il goblin viene perso definitivamente. È anche un modo per liberare uno slot; la ricompensa e il momento in cui proporre la scelta vanno bilanciati.
- Se tutto il party schierato viene sconfitto, le riserve rimaste fuggono nel panico e la run termina; non entrano automaticamente nello scontro. Un raro evento di campagna è l'unica eccezione alla perdita permanente dei goblin caduti e offre un beneficio alternativo quando non c'è nessuno da riportare in vita.
- La sconfitta conclude la run e richiede di ricominciare.
- Nessun goblin sopravvive alla sconfitta della run. Una **Hall of Fame** può registrare gli eroi migliori con statistiche, classe e linea materna/specie di origine; è una funzione commemorativa, non un sistema di persistenza dei personaggi.
- Gli sblocchi persistenti ampliano soprattutto le alternative: nuovi oggetti per classi/specie, specie materne, classi non tutorial, armi, armature, oggetti speciali, artefatti dei warlord e tratti alternativi o aggiuntivi. La prima selezione di contenuti è disponibile senza grind obbligatorio; la forza relativa si verifica col playtest.
- Tratti specifici di classe si sbloccano giocando quella classe e usando le sue abilità; alcune opzioni possono inoltre sbloccarsi vincendo con uno specifico warlord.
- Talenti da assegnare ai goblin e nuove opzioni possono essere sbloccati giocando più campagne. La progressione persistente va comunicata chiaramente e non deve essere confusa con il roster di cinque individui della run corrente.
- I talenti/oggetti possono appartenere a set: possedere/equipaggiare un numero definito di pezzi attiva un bonus aggiuntivo. I set vanno introdotti con cautela, per evitare combinazioni eccessivamente potenti.

### 5.4 Equipaggiamento e risorse

Ogni personaggio ha come base tre slot: **arma, armatura e oggetto speciale**. Oggetti e passiva della specie modificano attributi o capacità; alcune specie possono concedere eccezioni esplicite, come un ulteriore slot speciale o l'uso di due armi. Il sistema deve mostrare chiaramente gli slot effettivi della singola unità. Gli oggetti sono personali e i goblin sono possessivi: un personaggio accetta la sostituzione solo se il nuovo oggetto ha rarità superiore a quello equipaggiato; un oggetto di pari rarità o inferiore non viene accettato. Il giocatore sceglie se assegnare o rifiutare il nuovo oggetto. Bonus di set possono essere aggiunti in seguito: raccogliere più pezzi dello stesso set può attivare un effetto aggiuntivo; il numero di set e pezzi iniziali va mantenuto contenuto.

**Risorse della run**

- **Provviste:** curano automaticamente gli HP persi durante il viaggio fra un nodo e il successivo; gli accampamenti e i luoghi di riposo aggiungono recupero. Valori precedentemente ipotizzati (5 HP da provviste, 10 HP a ogni personaggio in accampamento e +5 provviste da razzia) sono parametri di test, non numeri definitivi.
- **Tesoro:** usato con i mercanti e in eventi che chiedono un sacrificio o pagamento.
- **Influenza:** non inclusa nel prototipo/MVP. In precedenza era stata ipotizzata per eventi e controllo di goblin forti, ma la sua funzione non è ancora abbastanza definita; reinserirla solo se emergerà una decisione distinta che non possono già svolgere le provviste o il tesoro.

Le risorse devono avere utilizzi distinti e poche schermate di gestione: non aggiungere valute solo per simulare la logistica.

### 5.5 Mappa della campagna e tipi di nodo

- Il mondo è una marcia in avanti verso la capitale, suddivisa in tre atti. Ogni atto termina con un boss; il boss del terzo atto si trova nella capitale ed è il boss finale.
- La mappa può avere bivi e percorsi alternativi, ma non deviazioni verso campagne o strategie di conquista indipendenti: tutti i percorsi servono l'obiettivo di conquistare il mondo.
- Prima di scegliere, il giocatore vede icone per il **tipo e la difficoltà del nodo**, ma non l'incontro completo. Le icone possono offrire indizi sulla minaccia principale (per esempio un villaggio con una croce o una chiesa indica una presenza significativa di chierici); composizione e dettagli restano nascosti. Gli eventi casuali sono rappresentati da un punto interrogativo.
- Ogni atto prevede almeno **due nodi mercante, cinque incontri élite e cinque riposi** distribuiti sulla mappa; non tutti devono essere raggiungibili in ogni percorso. Ogni percorso deve invece includere un nodo obbligatorio di tesoro o razzia circa a metà dell'atto.
- Il resto dei nodi varia fra battaglie normali ed eventi. Gli incontri di battaglia (composizione nemica e scenario/regole dell'incontro) non si ripetono all'interno della stessa campagna: le combinazioni e i contenuti devono bastare a sostenere i percorsi possibili.
- I raid/razzie sono nodi dedicati senza combattimento: forniscono provviste e una cura leggera; raramente possono sbloccare una linea materna o specie speciale. La ricompensa rara è limitata a una per atto al massimo.
- Villaggi e città possono essere tematizzati negli incontri o negli eventi, senza richiedere un sistema diplomatico autonomo.
- Gli eventi possono offrire sotterfugi e scelte utili alla stessa avanzata militare. Non ci sono vittorie diplomatiche o un percorso di governo pacifico.
- La conquista dei villaggi/città e le razzie devono offrire differenze leggibili di rischio e ricompensa, ma non richiedono un simulatore di fazioni per l'MVP.
- Gli incontri nemici sono progettati e bilanciati singolarmente: numero, tipologia e combinazioni dei nemici cambiano fra scontri; abilità e comportamenti sono definiti per incontro, non combinati casualmente in modo da produrre avversari invincibili.
- I boss hanno meccaniche riconoscibili e una gimmick comunicata prima dello scontro. In modalità a turni, i bersagli previsti e il danno stimato dei nemici sono leggibili durante la selezione delle azioni; il boss deve restare affrontabile con più di una composizione.

## 6. Struttura narrativa

### Premessa

Un warlord goblin avvia una marcia di conquista verso la capitale, attraversando tre atti di territori difesi da eserciti, mostri e insediamenti. L'orda parte con uno o due goblin base; battaglie ed eventi forniscono progressi legati alle specie, alle classi e alle tipologie di nemici, oltre a opportunità per creare nuovi membri, fino a cinque nel party e cinque in panchina. La storia segue l'avanzata militare e le conseguenze della conquista.

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

- Un prototipo di combattimento a turni con opzione autobattle, un warlord e un gruppo iniziale di goblin che rappresenti i ruoli di tutorial.
- Quattro classi tutorial: Guerriero (difesa/provocazione), Ranger (attacco a distanza), Stregone (danno magico) e Chierico (cura e scudo di squadra); le classi dei goblin sono fisse.
- Party di battaglia massimo cinque e panchina di riserva fino a cinque personaggi; il giocatore cambia membri e posizioni prima di ogni scontro.
- Azioni manuali e scelta del bersaglio per ogni goblin; modalità automatica con priorità di comportamento specifiche e opzione per includere o escludere le ultimate.
- Attacchi base, abilità a cooldown, provocazione, portata melee/ranged e previsione del bersaglio/danno nemico in modalità a turni.
- Ricompense legate alle tipologie nemiche e soglie candidate 5/10/15/20 per sbloccare o migliorare unità e tratti.
- Posizioni che influenzano i bersagli e almeno una sinergia di vicinanza o posizione preferita.
- Una gimmick di boss leggibile e anticipata.
- Una prima prova di creazione di goblin, passiva di specie materna, provviste con cura automatica fra nodi, oggetti e danni persistenti.
- Una mini-mappa authored con icone-indizio per le battaglie e nodi evento indicati da "?"; i dettagli degli incontri restano nascosti.
- Asset gratuiti e placeholder; usare strumenti AI per supportare i test iniziali. Nessuna spesa significativa in produzione artistica prima di validare lo slice.

### Accesso Anticipato — primo atto

- Prima release pubblica in Accesso Anticipato: il **primo atto completo**, dalla partenza al primo boss.
- Almeno **tre warlord** iniziali, orientati a mischia, distanza e magia; roster di partenza e artefatto unico differenziano le run.
- Gli artefatti possono potenziare il relativo stile (per esempio danno melee, ranged o magico) oppure influire su ritrovamento di goblin e soglie di progressione; gli effetti sono alternative da testare, non un elenco obbligatorio.
- Party massimo cinque e panchina fino a cinque; un set contenuto ma significativo di specie e classi, con almeno una linea materna alternativa.
- Un roster di classi tutorial che copra difesa/provocazione, attacchi a distanza, magia e cura; classi ulteriori sbloccate come alternative, non come requisiti di potenza.
- Tipi di nodo principali: battaglie normali/élite, eventi casuali, accampamenti, creazione di unità, mercanti, tesoro/raid e boss dell'atto.
- Per l'atto: almeno due nodi mercante, cinque élite e cinque riposi sulla mappa complessiva; tesoro o raid obbligatorio circa a metà per ciascun percorso. Non tutti i nodi garantiti devono essere raggiungibili da ogni rotta.
- Nessuna battaglia o composizione d'incontro ripetuta durante una campagna; il numero di incontri distinti sostenibili va definito prima del contenuto finale dell'atto.
- Tre slot equipaggiamento base per personaggio (arma, armatura, speciale), con eccezioni esplicite conferite da alcune specie; provviste per la cura automatica fra i nodi e tesoro per acquisti/eventi.
- Sconfitta della run, Hall of Fame e primi sblocchi persistenti: nuove opzioni di partenza, passivi, talenti e oggetti. I tratti di classe si sbloccano usando le abilità della classe o vincendo con specifici warlord.
- Solo placeholder e asset gratuiti finché non sarà possibile collaborare con un artista e finanziare la produzione visiva definitiva.
- Italiano e inglese per testi e interfaccia.
- Pubblicare come Accesso Anticipato solo quando il primo atto offre un ciclo completo e giocabile; comunicare chiaramente che atti successivi dipendono da finanziamenti e sviluppo futuro.

### Gioco completo previsto

- Tre atti in un'unica campagna di conquista; il boss finale presidia la capitale.
- Ulteriori warlord, specie, classi, talenti, oggetti, eventi e contenuti per i tre atti, dimensionati in base ai risultati, al tempo e ai fondi.
- L'espansione oltre il primo atto non è una promessa di data o contenuto finché non viene finanziata.

### Fuori ambito per l'MVP

- Combattimento action controllato direttamente, platforming e fisica di precisione.
- Multiplayer, cooperativa, modalità online o servizi server. Il multiplayer resta una possibilità remota da considerare solo dopo il rilascio del single-player; non va progettato o implementato nell'MVP.
- Mondo aperto, deviazioni verso campagne alternative o mappe generate proceduralmente complesse.
- Diplomazia, conquista pacifica o sistemi geopolitici autonomi.
- Un party schierato superiore a cinque personaggi; una panchina fino a cinque riserve è il target corrente.
- Influenza come risorsa finché non viene definita una funzione necessaria e distinta.
- Produzione artistica costosa prima della validazione e del finanziamento.
- Dialoghi doppiati e cinematiche.
- Rappresentazione esplicita di rapporti sessuali o riproduzione.
- Gestione esplorabile della base.

## 8. Roadmap di produzione

### Fase 0 — Prototipo economico

- Creare il progetto Godot 4 e una scena di battaglia leggibile usando placeholder e asset gratuiti.
- Definire le risorse dati di personaggio, specie materne, classi, abilità, tratti e oggetti.
- Usare come riferimenti per i quattro ruoli di tutorial i kit di Guerriero, Ranger, Chierico e Stregone proposti in [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md), adattando cooldown ed effetti al sistema a turni; il Chierico offre scudo di squadra e non resurrezione in battaglia.
- Sperimentare party schierato massimo cinque, panchina fino a cinque, partenze da uno o due goblin e warlord con conoscenze iniziali differenti.
- Implementare turni, attacco base sempre disponibile, abilità con cooldown e scelta manuale dell'azione e del bersaglio; aggiungere un'automazione basata sulla personalità dei goblin e l'opzione di includere le ultimate.
- Provare le regole di bersaglio: melee contro prima linea, ranged contro qualunque nemico, eccezioni da provocazione e portata per abilità.
- Mostrare anticipazione dei bersagli nemici e stima dei danni in modalità manuale; non calcolare la previsione nell'autobattle.
- Provare le posizioni e la leggibilità delle icone degli stati.

**Uscita:** un prototipo di combattimento con schermata pre-battaglia, scelta party/posizioni, scelta fra controllo manuale e automatico, nemici con bersagli leggibili e boss con gimmick anticipata.

### Fase 1 — Progressione del party

- Implementare salute persistente, provviste e recupero.
- Aggiungere tre slot oggetto e accettazione dei drop solo se hanno rarità superiore all'oggetto equipaggiato, comunicando chiaramente la regola.
- Aggiungere soglie di progressione candidate 5/10/15/20 legate alle tipologie di nemici sconfitti e a sblocco/unità/livello/tratto.
- Aggiungere level up dei goblin e ricompense che crescono con la progressione mantenendo valori numerici bassi.
- Provare creazione di nuovi goblin e passive ereditate dalla specie materna, con benefici applicabili a classi diverse.
- Provare il congedo di una riserva mandata a caccia in cambio di tesoro.
- Provare sblocco di tratti alternativi e contenuti tramite uso delle abilità e vittorie con warlord specifici.
- Selezionare dal documento [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) pochi tratti sbloccabili per classe e provarli prima di espandere il catalogo.

**Uscita:** sconfiggere un incontro modifica le opzioni del party; il party schierato resta entro cinque unità e la panchina entro cinque riserve.

### Fase 2 — Mappa e primo atto giocabile

- Creare una mappa authored con bivi; mostrare i tipi di nodo raggiungibili.
- Implementare battaglia, élite, evento, accampamento, creazione, mercante e boss.
- Collegare le ricompense, la cura automatica tramite provviste fra i nodi, il tesoro e la preparazione prima dello start.
- Creare una gimmick unica per il boss e comunicarla prima della battaglia.
- Progettare incontri authored con composizione, abilità e comportamenti nemici bilanciati individualmente; evitare composizioni generate casualmente durante la run.
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
- Aggiungere nuovi nemici, classi, specie, oggetti, eventi e boss solo nella misura sostenibile.
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
    classes/
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
- **RosterManager:** party schierato massimo cinque, panchina fino a cinque, classi fisse, progressione delle tipologie nemiche e assegnazione alle posizioni.
- **BattleController:** gestisce turni, azioni manuali o automatizzate, cooldown, validità dei bersagli, provocazioni, portata, danno previsto e condizioni di sconfitta.
- **CharacterDefinition / SpeciesDefinition / ClassDefinition / SkillDefinition / TraitDefinition:** personaggi, specie materne, classi, attributi, abilità, tratti e modificatori di equipaggiamento.
- **EquipmentDefinition:** dati degli oggetti per arma, armatura e slot speciale.
- **RouteNodeDefinition / EncounterDefinition / EventDefinition:** mappa, composizioni nemiche, eventi e ricompense.
- **EnemyProgressionManager:** contatori per tipologia di nemico e soglie per sbloccare o migliorare unità e tratti.
- **MetaProgressionManager:** sblocchi persistenti di warlord, tratti di classe, specie materne, talenti, oggetti e set.
- **HallOfFame:** statistiche commemorative dei goblin migliori, inclusa la linea materna/specie d'origine.
- **SaveManager:** serializzazione dello stato della campagna e degli sblocchi, con versione dei salvataggi.
- **ScreenRouter:** cambio fra mappa, preparazione, battaglia manuale/automatica e risultati.

Evitare un manager globale che contenga ogni regola. Non introdurre networking o dipendenze multiplayer: il progetto è single-player offline.

## 11. Interfaccia, localizzazione e accessibilità

- Schermata pre-battaglia: roster disponibile, party attuale, formazione/posizioni, statistiche, oggetti e scelta fra controllo manuale e autobattle.
- La mappa usa icone per tipo e difficoltà, nasconde la composizione precisa e può indicare la minaccia principale con simboli dedicati; gli eventi casuali sono punti interrogativi.
- La formazione spiega bersagli, portata melee/ranged, provocazioni, accessibilità delle retrovie e bonus di vicinanza.
- Nella modalità a turni l'interfaccia mostra il bersaglio nemico previsto e una stima del danno; nell'autobattle la previsione non viene calcolata.
- Durante il combattimento, l'interfaccia comunica turno, azioni, cooldown, bersagli ed effetti. Le icone di stato si accumulano vicino al nome e alla barra salute; il menu di pausa consente di ispezionare gli effetti.
- Testi e interfaccia in italiano e inglese per la prima release.
- Accessibilità da definire con il prototipo; prevedere almeno testo leggibile e ridimensionabile, contrasto adeguato, simboli affiancati ai colori per distinguere classi, keyword e stati (incluso supporto al daltonismo), sottotitoli per ogni contenuto audio e controlli audio separati.
- Salvare ai passaggi sicuri fra nodi e mantenere recuperabili gli sblocchi persistenti.

## 12. Verifica del design e criteri di successo

Il prototipo è sulla strada giusta se:

- il giocatore capisce il flusso dei turni, cooldown, portata, provocazione e bersagli validi;
- il giocatore può spiegare le decisioni manuali e comprende l'automazione basata sulla personalità dei goblin;
- la previsione dei bersagli/danni nemici è utile e corretta nella modalità a turni, senza calcoli superflui nell'autobattle;
- icone e ispezione pausa rendono leggibili stati e debuff;
- il party massimo di cinque e la panchina massima di cinque riserve creano una progressione leggibile;
- le soglie per tipologia nemica e le ricompense sono comprensibili e incidono sulla composizione del roster;
- le unità ferite, le provviste e i tre slot oggetto producono scelte senza diventare contabilità eccessiva;
- almeno due percorsi sulla mappa producono composizioni, ricompense o livelli di rischio differenti;
- il giocatore comprende il tipo/difficoltà dei nodi, ma trova comunque significativa la scoperta del contenuto;
- le meccaniche dei boss sono anticipate e leggibili, senza richiedere un solo counter;
- una campagna del primo atto può essere completata o persa senza blocchi, e la sconfitta conduce a sblocchi comprensibili;
- gli sblocchi ampliano la varietà senza rendere necessario ripetere run per grindare potenza;
- il giocatore vuole provare una seconda run per un warlord, una classe, un tratto, un equipaggiamento o un percorso diverso.

### Test manuali minimi

- Iniziare con ciascuno dei tre warlord e verificare roster, scelta dei goblin iniziali e artefatto, senza vantaggi dominanti.
- Cambiare composizione e posizionamento; verificare accesso ai bersagli, prima linea, provocazione, portata e sinergie.
- Verificare la scelta manuale di azione e bersaglio e confrontarla con l'autobattle, sia con ultimate automatiche abilitate sia disabilitate.
- Controllare cooldown di 1-2 turni per abilità normali e 3-5 o più per ultimate, inclusi i casi senza bersaglio valido.
- Controllare che le previsioni di bersaglio e danno siano corrette nella modalità a turni e assenti nell'autobattle.
- Sconfiggere tipologie diverse e verificare contatori e soglie 5/10/15/20, sblocchi di unità/livelli/tratti e differenze per incontro.
- Creare un goblin e verificare la passiva della specie materna, i sei attributi e le eccezioni agli slot equipaggiamento.
- Controllare limite di cinque in party e fino a cinque riserve, cambio di party fra battaglie e gestione della panchina piena.
- Verificare gli oggetti: stessa rarità o inferiore non sostituisce; rarità superiore può essere assegnata o rifiutata.
- Verificare la cura automatica da provviste fra nodi e il recupero aggiuntivo ai riposi.
- Mandare una riserva a caccia, controllare rimozione dal roster e tesoro ottenuto.
- Verificare le icone-indizio delle battaglie, gli eventi mostrati con "?" e i bersagli/dettagli nascosti prima dell'incontro.
- Verificare i nodi garantiti dell'atto, il raid/tesoro obbligatorio a metà e l'assenza di composizioni o regole d'incontro ripetute.
- Eliminare tutti i membri schierati e verificare che le riserve fuggano e la run termini; controllare l'evento dedicato sia con un caduto da resuscitare sia senza caduti.
- Completare e perdere l'atto uno; verificare gli sblocchi e il riavvio della run.
- Verificare Hall of Fame dopo la sconfitta e tratti sbloccati con uso abilità/vittorie di warlord.
- Chiudere e riaprire il gioco per verificare salvataggio di run e progressione persistente.
- Verificare testi in italiano e inglese, leggibilità, simboli non dipendenti solo dal colore e impostazioni audio.

## 13. Rischi e mitigazioni

| Rischio | Effetto | Mitigazione |
|---|---|---|
| Modalità a turni lenta o automazione poco affidabile | Troppe scelte rallentano gli scontri; l'autobattle può sembrare arbitrario | Prototipare entrambe le modalità sullo stesso incontro; rendere leggibili priorità, cooldown e personalità |
| Bersagli e stime errati | Il giocatore non può pianificare né fidarsi della previsione | Usare regole di targeting condivise tra UI e simulazione; testare melee, distanza, provocazione e range delle abilità |
| Progressione per conteggio crea farming | Si sceglie l'incontro solo per accumulare il tipo di nemico più efficiente | Usare soglie specifiche per tipologia e legare ricompense a difficoltà/ruolo dell'incontro, non solo al volume |
| Risorse e livelli creano palla di neve | Le prime vittorie rendono il resto della campagna automatico | Limitare il party a cinque, contenere bonus permanenti e verificare curve di soglie e cure |
| Troppe combinazioni specie/classe | Aumenta il costo di arte, implementazione e bilanciamento | Le classi definiscono ruoli, le specie forniscono passive riutilizzabili; ampliare solo se una combinazione introduce una scelta |
| Sblocchi permanenti obbligatori | La meta-progressione rende le prime run frustranti o il grind necessario | Sbloccare opzioni e vantaggi bilanciati; provare la campagna anche senza grind ripetitivo |
| Risorse ridondanti | Provviste/tesoro/influenza diventano contabilità senza decisioni | MVP con provviste e tesoro; escludere influenza finché non ha un uso distinto |
| Requisiti minimi dei nodi troppo costosi | Cinque élite e cinque riposi per atto, più mercanti, raid ed eventi, richiedono molti contenuti distinti | Usare mappe ramificate authored, riutilizzare regole e set di animazioni; definire quanti incontri unici richiedono davvero variazione |
| Nessuna battaglia ripetuta | La produzione di incontri può superare budget e capacità | Creare varianti di composizione e gimmick mantenendo gli incontri meccanicamente distinti; prototipare un atto prima di impegnarsi sui tre |
| Party e panchina saturi | Le ricompense e la creazione perdono valore se non c'è spazio | Consentire di mandare a caccia una riserva in cambio di tesoro; comunicare che è una perdita permanente |
| Sconfitta improvvisa del party | Le riserve non possono salvare una run altrimenti persa | Anticipare la regola della fuga e garantire che la difficoltà degli incontri sia leggibile |
| Passiva di specie o attributi troppo dominanti | Alcune origini diventano sempre migliori a prescindere dalla classe | Valutare le passive su più classi e mantenere gli effetti differenti ma utili, senza bilanciamento competitivo artificiale |
| Targeting e posizionamento troppo complicati | Portata, provocazione, prossimità e artefatti possono rendere la schermata indecifrabile | Introdurre una regola alla volta e mostrare bersagli e danno previsto nella modalità a turni |
| Oggetto “migliore” definito solo dalla rarità | Un drop superiore in rarità può peggiorare la build o forzare una scelta frustrante | Far sì che la regola impedisca l'assegnazione degli oggetti di pari/inferiore rarità, ma lasciare sempre il rifiuto del drop al giocatore |
| Crescita del team oltre i mezzi | Arte e sviluppo superano il budget disponibile | Prototipare con asset gratuiti/placeholder e usare l'Accesso Anticipato per finanziare eventuale produzione successiva |
| Accesso Anticipato percepito come incompleto senza contesto | Il primo atto può sembrare una demo se roadmap e stato non sono chiari | Completare e rifinire il primo atto, comunicare limiti, obiettivi e dipendenza degli atti successivi dai fondi |
| Temi maturi rappresentati in modo incoerente | Il tono implicito rischia di diventare gratuito o confuso | Niente sangue o rappresentazioni esplicite; mantenere cattura e riproduzione fuori campo e il tono principalmente tragico |

## 14. Dettagli da definire durante il prototipo

Le decisioni di direzione sono state definite. Restano da bilanciare o specificare:

- Sequenza dei turni: iniziativa, ordine fra unità alleate e nemiche, durata massima e condizioni di fine turno.
- Quando e come il cooldown scala; se un'abilità senza bersaglio valido mantiene o consuma il cooldown.
- Personalità e priorità dell'autobattle, incluse le condizioni in cui usare abilità ordinarie e ultimate.
- Formula della previsione del danno e gestione dei modificatori; mantenerla affidabile e abbastanza economica da aggiornare in modalità manuale.
- Valori e curve dei sei attributi, statistiche derivate, requisiti di classi/equipaggiamento e bilanciamento delle passive specie.
- Mappatura esatta delle soglie 5/10/15/20 a sblocco, livello, classe o tratto; definire se i conteggi si azzerano a ogni run o persistono.
- Quantità di cura automatica da provviste per tratta e bonus dei riposi; impatto delle ferite persistenti sulla durata dell'atto.
- Portata specifica delle abilità e lista di effetti che provocano, proteggono, accumulano stati o alterano i bersagli.
- Effetti e disponibilità dei roster/artefatti dei tre warlord; evitare che una riduzione di soglia o un bonus di danno diventi dominante.
- Compenso in tesoro per una riserva mandata a caccia e momento in cui la decisione viene proposta.
- Quali specie concedono slot speciali aggiuntivi, doppia arma, rigenerazione o riduzione del cooldown dell'ultimate; mantenere interfaccia e scheda goblin chiare.
- Distribuzione concreta sulla mappa dei due mercanti, cinque élite, cinque riposi e nodo tesoro/raid garantito su ogni percorso.
- Numero di incontri authored sostenibili, contenuto esatto degli indizi sulle icone e selezione degli eventi casuali.
- Forma e costo dei tratti alternativi, degli oggetti sbloccabili e dei set.
- Durata dell'atto uno, prezzo dell'Accesso Anticipato e date, da valutare quando esiste una build giocabile.
- Contenuto della Hall of Fame e quali statistiche dei personaggi sconfitti conservare.
- Funzionalità di accessibilità ulteriori rispetto alla base prevista, incluso testo leggibile, icone e simboli per classi/stati e opzioni per daltonismo.
- Budget e forma della collaborazione artistica dopo il prototipo.

Non rientrano nel design attuale: combattimento action/platforming, diplomazia come percorso alternativo, influenza come risorsa e multiplayer. L'autobattle resta una modalità di gioco; il combattimento tattico a turni è il modello principale. Gli atti due e tre sono obiettivo del gioco completo, ma il loro sviluppo resta dipendente da finanziamenti e validazione dell'atto uno.

## 15. Prossimo passo operativo

Realizzare un prototipo economico con un warlord, quattro ruoli tutorial (Guerriero, Ranger, Stregone e Chierico), party attivo fino a cinque e un piccolo gruppo di riserva. Implementare turni, attacco base, abilità con cooldown, scelta manuale di azione/bersaglio e autobattle con e senza ultimate; confrontare targeting melee/ranged, provocazione e portata. Mostrare in modalità a turni il bersaglio nemico e il danno previsto, e in entrambe le modalità icone degli stati. Includere una soglia di progressione nemica, cura automatica da provviste fra nodi, riposo, un oggetto e un goblin con passiva materna; provare il congedo di una riserva per tesoro. Collegare poi i sistemi a una mini-mappa con icone-indizio, eventi "?" e un boss con gimmick anticipata. Se i tester non capiscono le cause dell'esito o non trovano significativa la scelta manuale rispetto all'automazione, correggere le regole prima di aumentare classi e incontri o investire in arte definitiva.
