# Goblin Warlord — Piano di progetto

> Documento di pre-produzione aggiornato con le decisioni attuali. I dettagli indicati come da bilanciare restano soggetti a prototipazione e playtest.

## 1. Visione

**Goblin Warlord** è un roguelite dark fantasy 2D per pubblico adulto, costruito attorno a una campagna di conquista. Il giocatore sceglie un warlord goblin e guida una piccola armata in un'unica marcia attraverso il mondo fino alla capitale, conquistando territori e sbloccando specie e job da integrare nell'orda.

La campagna si sviluppa in tre atti su una mappa di nodi in stile *Slay the Spire*: il giocatore vede i tipi di nodo accessibili, sceglie il percorso e affronta un boss alla fine di ogni atto; il boss del terzo atto si trova nella capitale ed è l'obiettivo conclusivo. La presentazione degli scontri è laterale, in 2D; il combattimento è un **autobattler senza interventi durante la battaglia**. La strategia sta nella composizione del roster, nell'equipaggiamento e nell'ordine delle unità: le abilità si attivano seguendo la disposizione scelta prima di avviare lo scontro.

### Promessa al giocatore

> Scegli il tuo warlord, costruisci un'orda di massimo cinque goblin e marcia fino alla capitale: ogni battaglia e ogni scelta di percorso determinano quali specie, job, talenti ed equipaggiamenti potrai usare.

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
- **Combattimento:** autobattler; dopo l'avvio dello scontro non c'è input del giocatore. Il roster e l'ordine delle unità/abilità vengono preparati prima della battaglia.
- **Piattaforma iniziale proposta:** PC.
- **Tecnologia:** Godot 4, progetto 2D.
- **Lingue previste:** italiano e inglese.
- **Modalità:** giocatore singolo, offline. Nessun multiplayer nel progetto attuale; non va pianificato né implementato.

## 3. Pilastri di design

1. **La campagna è una marcia verso la capitale.** Ogni atto avvicina al boss e all'obiettivo finale.
2. **L'armata cresce imparando dai nemici.** Le vittorie sbloccano conoscenze di specie e job; la discendenza dei nuovi goblin può ereditare peculiarità della specie materna.
3. **La preparazione è il combattimento.** Il giocatore non interviene durante l'autobattaglia: composizione, oggetti e ordine delle unità determinano la sequenza delle abilità.
4. **La squadra è piccola e personale.** Ogni membro è un individuo con specie, job, statistiche ed equipaggiamento.
5. **Le run sbloccano opzioni.** Nuovi warlord, classi iniziali, passivi, talenti e oggetti ampliano le possibilità delle campagne successive.

## 4. Ciclo di gioco

### Ciclo della campagna

1. **Scegli un warlord:** la scelta determina il profilo iniziale e se l'armata parte con uno o due goblin base.
2. **Scegli il prossimo nodo** fra quelli visibili sulla mappa: battaglia, battaglia élite, evento casuale, accampamento, creazione di unità, mercante o boss.
3. **Prepara il party** con un massimo di cinque personaggi. Prima di ogni battaglia puoi modificare liberamente la composizione e l'ordine; quando sei pronto, avvii lo scontro.
4. **Combatti automaticamente:** non ci sono comandi o abilità attivabili dal giocatore durante la battaglia. L'ordine in cui sono disposti i personaggi determina l'ordine di attivazione delle loro abilità.
5. **Ottieni ricompense** legate a ciò che hai affrontato: specie e job dipendono dal nemico; incontri più difficili e con più avversari danno ricompense maggiori.
6. **Gestisci salute e risorse:** spendi provviste per curare il party fra gli scontri, usa il tesoro da mercanti o in eventi, riposa e potenzia negli accampamenti.
7. **Avanza attraverso i tre atti**, sconfiggi i rispettivi boss e punta alla capitale e al boss finale.
8. **Vinci o perdi la run.** Una sconfitta conclude la campagna; gli sblocchi persistenti ampliano le opzioni per i tentativi successivi.

## 5. Sistemi principali

### 5.1 Personaggi, specie, job e discendenza

- Il roster/party ha un massimo di **cinque personaggi**. All'inizio il warlord scelto determina se si parte con uno o due goblin base e quali opzioni iniziali sono disponibili.
- I personaggi sono individui persistenti, non pedine fungibili. Ognuno ha nome/identità, specie (linea materna), job, salute, attacco e difesa.
- Le specie conferiscono peculiarità innate; i job definiscono il ruolo e le abilità. Specie e job sono sistemi distinti e possono combinarsi come in un gruppo fantasy.
- L'assimilazione è un reclutamento forzato astratto: non si mostra come avviene, ma si ottengono nuove **conoscenze** di specie/job, come se l'orda imparasse dai vinti.
- Ogni battaglia fornisce progressi/conoscenze di specie e job in quantità determinate dal tipo di avversario; incontri più difficili, con più nemici o con boss danno ricompense maggiori, con limiti di bilanciamento per evitare strategie di farming banali.
- I goblin creati durante la campagna possono ereditare peculiarità dalla specie materna acquisita. La cattura e la riproduzione restano implicite e fuori campo: non si mostrano rapporti o atti sessuali. Una razzia può occasionalmente sbloccare una nuova linea materna o una specie, come ricompensa narrativa e di progressione.
- I nodi dedicati permettono di creare nuovi goblin usando le conoscenze/specie e i job disponibili. Il loro scopo è offrire nuovi membri al party entro il limite di cinque, non espandere all'infinito una riserva; se il party è già pieno, il giocatore deve sostituire un membro o rinunciare alla nuova unità.
- I rapporti di forza e le caratteristiche specie/job devono essere leggibili e creare scelte; non ogni combinazione richiede una regola o un'animazione esclusiva.

**Job di partenza per il prototipo:** tre ruoli chiaramente distinti (per esempio bruto, predone e sciamano). Nel gioco completo si prevede una selezione più ampia di job fantasy, con complessità simile alla scelta dei ruoli in un gruppo d'avventura.

**Specie di partenza e progressione:** il roster iniziale è goblin; nuove specie e peculiarità si scoprono affrontando nemici e attraverso eventi. Limitare il numero di specie/job implementati per l'Accesso Anticipato in base agli asset e al tempo disponibili.

### 5.2 Combattimento autobattler

- Prima di ogni scontro il giocatore può modificare liberamente il party e disporre i personaggi nell'ordine desiderato, poi avvia la battaglia con un comando esplicito.
- **Nessun input del giocatore durante lo scontro.** Niente abilità manuali, ordini, pausa tattica o cambi di bersaglio mentre la battaglia è in corso.
- Le unità agiscono automaticamente; l'ordine in cui il giocatore le dispone determina l'ordine in cui si attivano le loro abilità. Questo ordine è il principale strumento tattico e deve produrre sinergie comprensibili.
- Statistiche iniziali: salute, attacco e difesa; altri parametri si aggiungono soltanto se necessari alla distinzione dei job.
- Ogni job possiede abilità e funzione riconoscibili. Le abilità e i loro effetti devono essere leggibili prima di premere **Start battaglia**.
- La presentazione deve rendere comprensibili bersagli, attivazioni, danni e ordine delle abilità senza richiedere microgestione.
- Gli oggetti, le specie, i job e l'ordine del party sono le leve di preparazione; l'abilità del giocatore consiste nel prevedere la sequenza e costruire una squadra coerente.

### 5.3 Progressione durante e fra le campagne

- Durante una campagna, le battaglie sbloccano conoscenze di specie e job in base agli avversari sconfitti; difficoltà e numero di nemici influenzano la quantità ottenuta.
- Eventi, razzie e nodi di creazione possono fornire risorse, guarigione leggera, nuovi goblin o nuove linee/specie materne. Le razzie sono eventi senza combattimento, con ricompense inferiori a una battaglia ma con provviste e una piccola cura; occasionalmente possono sbloccare una specie o una madre particolare.
- Le unità mantengono i danni subiti fra battaglie. Le provviste sono la risorsa principale per curare il party fra gli scontri; accampamenti e alcuni eventi possono offrire riposo o potenziamenti.
- La sconfitta conclude la run e richiede di ricominciare.
- Le vittorie e sconfitte possono sbloccare contenuti persistenti per le run successive: warlord o classi iniziali, passivi, talenti ed equipaggiamenti. Gli sblocchi aggiungono opzioni, alcune potenzialmente più forti; il bilanciamento deve evitare che il progresso permanente renda inutile la preparazione o imponga grind.
- Talenti da assegnare ai goblin e nuove opzioni possono essere sbloccati giocando più campagne. La progressione persistente va comunicata chiaramente e non deve essere confusa con il roster di cinque individui della run corrente.

### 5.4 Equipaggiamento e risorse

Ogni personaggio ha tre slot: **arma, armatura e oggetto speciale**. Gli oggetti sono personali e i goblin sono possessivi: durante la run un oggetto può sostituirne uno già equipaggiato solo se è considerato migliore. Il criterio pratico di confronto (statistiche, qualità o confronto esplicito nell'interfaccia) va reso chiaro al giocatore; gli oggetti possono essere acquisiti o acquistati senza introdurre inventari complessi.

**Risorse della run**

- **Provviste:** usate per curare il party fra le battaglie; senza spesa o un nodo di riposo, i danni restano.
- **Tesoro:** usato con i mercanti e in eventi che chiedono un sacrificio o pagamento.
- **Influenza:** non inclusa nel prototipo/MVP. In precedenza era stata ipotizzata per eventi e controllo di goblin forti, ma la sua funzione non è ancora abbastanza definita; reinserirla solo se emergerà una decisione distinta che non possono già svolgere le provviste o il tesoro.

Le risorse devono avere utilizzi distinti e poche schermate di gestione: non aggiungere valute solo per simulare la logistica.

### 5.5 Mappa della campagna e tipi di nodo

- Il mondo è una marcia in avanti verso la capitale, suddivisa in tre atti. Ogni atto termina con un boss; il boss del terzo atto si trova nella capitale ed è il boss finale.
- La mappa può avere bivi e percorsi alternativi, ma non deviazioni verso campagne o strategie di conquista indipendenti: tutti i percorsi servono l'obiettivo di conquistare il mondo.
- Prima di scegliere, il giocatore vede il **tipo di nodo** raggiungibile, come in *Slay the Spire*; non è necessario rivelare in anticipo ogni nemico o ricompensa.
- Tipi di nodo previsti: battaglia normale, battaglia élite, evento casuale, accampamento (riposo o potenziamento), creazione di nuovi goblin, mercante e boss.
- Villaggi, città e razzie possono essere rappresentati come incontri o eventi associati ai tipi di nodo, non richiedono un sistema diplomatico autonomo.
- Gli eventi possono offrire sotterfugi e scelte utili alla stessa avanzata militare. Non ci sono vittorie diplomatiche o un percorso di governo pacifico.
- La conquista dei villaggi/città e le razzie devono offrire differenze leggibili di rischio e ricompensa, ma non richiedono un simulatore di fazioni per l'MVP.

## 6. Struttura narrativa

### Premessa

Un warlord goblin avvia una marcia di conquista verso la capitale, attraversando tre atti di territori difesi da eserciti, mostri e insediamenti. L'orda parte con uno o due goblin base; battaglie ed eventi forniscono conoscenze di specie/job e opportunità per creare nuovi membri, fino al limite di cinque. La storia segue l'avanzata militare e le conseguenze della conquista.

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

- Una battaglia autobattler ripetibile con 1-2 unità iniziali, più job/specie di prova e un ordine di attivazione configurato dal giocatore.
- Roster massimo di cinque; il giocatore cambia party e ordine prima di ogni scontro.
- Ricompense di specie/job variabili per tipo e difficoltà dell'incontro.
- Una prima prova di creazione di goblin, discendenza/specie materna, provviste, oggetti e danni persistenti.
- Una mini-mappa corta con un bivio, un evento, un accampamento, un mercante e un boss.
- Asset gratuiti e placeholder; usare strumenti AI per supportare i test iniziali. Nessuna spesa significativa in produzione artistica prima di validare lo slice.

### Accesso Anticipato — primo atto

- Prima release pubblica in Accesso Anticipato: il **primo atto completo**, dalla partenza al primo boss.
- Un warlord selezionabile o un piccolo insieme di warlord, con partenze di uno o due goblin e differenze riconoscibili.
- Roster massimo di cinque; un set contenuto ma significativo di specie e job, con almeno una linea materna alternativa.
- Tipi di nodo principali presenti nel piano: battaglie normali/élite, eventi casuali, accampamenti, creazione di unità, mercanti e boss dell'atto.
- Tre slot equipaggiamento per personaggio (arma, armatura, speciale), provviste per la cura e tesoro per acquisti/eventi.
- Sconfitta della run e primi sblocchi persistenti: nuove opzioni di partenza, passivi, talenti e oggetti.
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
- Un roster superiore a cinque personaggi nella run.
- Influenza come risorsa finché non viene definita una funzione necessaria e distinta.
- Produzione artistica costosa prima della validazione e del finanziamento.
- Dialoghi doppiati e cinematiche.
- Rappresentazione esplicita di rapporti sessuali o riproduzione.
- Gestione esplorabile della base.

## 8. Roadmap di produzione

### Fase 0 — Prototipo economico

- Creare il progetto Godot 4 e una scena di battaglia leggibile usando placeholder e asset gratuiti.
- Definire le risorse dati di personaggio, specie, job, abilità e oggetti.
- Sperimentare roster massimo cinque, partenze da uno o due goblin e ordine di attivazione delle abilità.
- Verificare che la battaglia automatica sia comprensibile senza input durante lo scontro.

**Uscita:** un prototipo di combattimento con schermata pre-battaglia, scelta del party e sequenza automatica osservabile.

### Fase 1 — Progressione del party

- Implementare salute persistente, provviste e recupero.
- Aggiungere tre slot oggetto e sostituzione solo con equipaggiamento migliore, spiegando il confronto nell'interfaccia.
- Aggiungere ricompense di specie/job legate agli avversari e alla difficoltà.
- Provare creazione di nuovi goblin e peculiarità ereditate dalla linea materna.

**Uscita:** sconfiggere un incontro modifica il party e le opzioni in modo visibile, senza superare cinque personaggi.

### Fase 2 — Mappa e primo atto giocabile

- Creare una mappa authored con bivi; mostrare i tipi di nodo raggiungibili.
- Implementare battaglia, élite, evento, accampamento, creazione, mercante e boss.
- Collegare le ricompense, la cura tramite provviste, il tesoro e la preparazione prima dello start.
- Completare la marcia fino al boss del primo atto.

**Uscita:** un primo atto completo dall'inizio al boss, con vittoria e sconfitta gestite.

### Fase 3 — Sblocchi e run successive

- Salvare gli sblocchi persistenti fra campagne.
- Implementare una selezione iniziale di warlord, classi, passivi, talenti e oggetti sbloccabili.
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
    equipment/
    events/
    route_nodes/
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
│   ├── PreBattleScreen
│   └── BattleScreen
│       ├── Battlefield
│       └── BattleHUD
└── CampaignState
```

### Responsabilità

- **CampaignManager:** atto, nodo corrente, avanzamento verso la capitale e condizioni di vittoria/sconfitta.
- **RosterManager:** massimo cinque personaggi della run, composizione, specie/job conosciuti e ordine di attivazione.
- **BattleController:** esegue automaticamente lo scontro a partire dal party confermato; non espone input tattici durante la battaglia.
- **CharacterDefinition / SpeciesDefinition / JobDefinition / SkillDefinition:** dati statici di personaggi e regole di specie/job/abilità.
- **EquipmentDefinition:** dati degli oggetti per arma, armatura e slot speciale.
- **RouteNodeDefinition / EncounterDefinition / EventDefinition:** mappa, composizioni nemiche, eventi e ricompense.
- **MetaProgressionManager:** sblocchi persistenti di warlord, classi iniziali, passivi, talenti e oggetti.
- **SaveManager:** serializzazione dello stato della campagna e degli sblocchi, con versione dei salvataggi.
- **ScreenRouter:** cambio fra mappa, preparazione, battaglia automatica e risultati.

Evitare un manager globale che contenga ogni regola. Non introdurre networking o dipendenze multiplayer: il progetto è single-player offline.

## 11. Interfaccia, localizzazione e accessibilità

- Schermata pre-battaglia: roster disponibile, party attuale, ordine delle abilità, statistiche, oggetti e comando **Start battaglia**.
- La mappa mostra chiaramente i tipi di nodo accessibili e la direzione generale verso il boss/atto successivo.
- Durante il combattimento, l'interfaccia comunica automaticamente ordine e risultato delle abilità; il giocatore non deve intervenire.
- Testi e interfaccia in italiano e inglese per la prima release.
- Accessibilità da definire con il prototipo; prevedere almeno testo leggibile e ridimensionabile, contrasto adeguato, icone/forme oltre al colore, sottotitoli per ogni contenuto audio e controlli audio separati.
- Salvare ai passaggi sicuri fra nodi e mantenere recuperabili gli sblocchi persistenti.

## 12. Verifica del design e criteri di successo

Il prototipo è sulla strada giusta se:

- il giocatore capisce che le decisioni tattiche avvengono prima dello scontro e può spiegare come l'ordine del party cambia la sequenza delle abilità;
- il party massimo di cinque e le partenze da uno o due goblin creano una progressione leggibile;
- una ricompensa specie/job dipende in modo comprensibile dall'avversario affrontato e dalla difficoltà;
- le unità ferite, le provviste e i tre slot oggetto producono scelte senza diventare contabilità eccessiva;
- almeno due percorsi sulla mappa producono composizioni, ricompense o livelli di rischio differenti;
- una campagna del primo atto può essere completata o persa senza blocchi, e la sconfitta conduce a sblocchi comprensibili;
- gli sblocchi ampliano la varietà senza rendere necessario ripetere run per grindare potenza;
- il giocatore vuole provare una seconda run per un warlord, job, talento, equipaggiamento o percorso diverso.

### Test manuali minimi

- Iniziare con ciascun warlord disponibile e verificare il numero e le opzioni delle unità iniziali.
- In battaglia, cambiare l'ordine delle unità prima dello start e verificare che cambi l'ordine di attivazione delle abilità.
- Verificare che durante la battaglia non ci siano comandi tattici o cambi di formazione.
- Sconfiggere avversari diversi e controllare le ricompense specie/job e la relazione fra difficoltà, numero di nemici e guadagno.
- Creare un goblin e verificare l'ereditarietà di una peculiarità della linea materna acquisita.
- Controllare roster massimo cinque e sostituzione di oggetti solo quando il nuovo è considerato migliore.
- Spendere provviste per curare, acquistare dal mercante con tesoro e scegliere eventi con/senza costo.
- Completare e perdere l'atto uno; verificare gli sblocchi e il riavvio della run.
- Chiudere e riaprire il gioco per verificare salvataggio di run e progressione persistente.
- Verificare testi in italiano e inglese, leggibilità, simboli non dipendenti solo dal colore e impostazioni audio.

## 13. Rischi e mitigazioni

| Rischio | Effetto | Mitigazione |
|---|---|---|
| Autobattaglia passiva o poco leggibile | Senza input durante lo scontro, il giocatore può sentirsi spettatore | Rendere la preparazione e l'ordine delle abilità determinanti; mostrare chiaramente la sequenza e testare prima di produrre molti contenuti |
| Ricompense che creano palla di neve | Più vittorie producono forza sempre crescente e azzerano la sfida | Limitare il roster a cinque, tarare il guadagno su difficoltà/numero nemici e verificare le curve per atto |
| Troppe combinazioni specie/job | Aumenta il costo di arte, implementazione e bilanciamento | Definire ruoli attraverso i job e peculiarità limitate per specie; ampliare solo se una combinazione introduce una scelta |
| Sblocchi permanenti obbligatori | La meta-progressione rende le prime run frustranti o il grind necessario | Sbloccare opzioni e vantaggi bilanciati; provare la campagna anche senza grind ripetitivo |
| Risorse ridondanti | Provviste/tesoro/influenza diventano contabilità senza decisioni | MVP con provviste e tesoro; escludere influenza finché non ha un uso distinto |
| Crescita del team oltre i mezzi | Arte e sviluppo superano il budget disponibile | Prototipare con asset gratuiti/placeholder e usare l'Accesso Anticipato per finanziare eventuale produzione successiva |
| Accesso Anticipato percepito come incompleto senza contesto | Il primo atto può sembrare una demo se roadmap e stato non sono chiari | Completare e rifinire il primo atto, comunicare limiti, obiettivi e dipendenza degli atti successivi dai fondi |
| Temi maturi rappresentati in modo incoerente | Il tono implicito rischia di diventare gratuito o confuso | Niente sangue o rappresentazioni esplicite; mantenere cattura e riproduzione fuori campo e il tono principalmente tragico |

## 14. Dettagli da definire durante il prototipo

Le decisioni di direzione sono state definite. Restano da bilanciare o specificare:

- Cadenza esatta di attivazione delle abilità nell'ordine del party e regole per abilità che interagiscono.
- Statistiche e bilanciamento dei job/specie e criterio esatto per definire un oggetto "migliore".
- Come il warlord influenza partenza, abilità/passivo e numero di goblin iniziali.
- Quantità di specie/job, nodi e ricompense sostenibile per il primo atto.
- Forma e costo dei talenti persistenti e degli sblocchi fra run.
- Durata dell'atto uno, prezzo dell'Accesso Anticipato e date, da valutare quando esiste una build giocabile.
- Funzionalità di accessibilità ulteriori rispetto alla base prevista.
- Budget e forma della collaborazione artistica dopo il prototipo.

Non rientrano nel design attuale: diplomazia come percorso alternativo, interventi durante l'autobattaglia, influenza come risorsa e multiplayer.

## 15. Prossimo passo operativo

Realizzare un prototipo economico con un warlord, uno o due goblin iniziali, party massimo cinque e pochi job/specie. Prima di ogni battaglia il giocatore compone il party e ordina le unità; premendo **Start battaglia** osserva la sequenza automatica delle abilità senza poter intervenire. Una vittoria assegna specie/job in base al nemico e alla difficoltà; le provviste curano, il tesoro permette acquisti e un nodo di creazione genera un goblin con possibili peculiarità materne. Collegare poi questi sistemi a una mappa breve con i tipi di nodo previsti e al boss dell'atto uno. Se questo ciclo non produce decisioni interessanti e desiderio di riprovare, correggere il combattimento e le ricompense prima di espandere il contenuto o investire in arte definitiva.
