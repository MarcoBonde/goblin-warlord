# Goblin Warlord — Piano di progetto

> Documento di pre-produzione. Le decisioni indicate come **proposta** sono una base concreta per il prototipo e potranno essere riviste dopo i primi test.

## 1. Visione

**Goblin Warlord** è un roguelite dark fantasy 2D per pubblico adulto, costruito attorno a una dinastia goblin e alle spedizioni di guerra che ne determinano il futuro. Il giocatore guida un warlord, sceglie come preparare una squadra di figli ed eredi e la conduce attraverso battaglie, razzie e decisioni politiche dalle conseguenze durature.

La presentazione è laterale e gli scontri si svolgono in arene 2D a scorrimento orizzontale. Il cuore strategico, però, è la preparazione della squadra e la lettura dei suoi punti di forza: il combattimento è un **autobattler tattico**, non un action platform da controllare col pad. Questa scelta concentra il lavoro sulle decisioni, sulla dinastia e sulla varietà delle run, evitando di dover realizzare subito un sistema complesso di movimento e combattimento manuale.

### Promessa al giocatore

> Costruisci una dinastia goblin, manda i suoi eredi in guerra e decidi quale prezzo sei disposto a pagare per conquistare il mondo.

### Pubblico e tono

- Pubblico adulto, interessato a dark fantasy, strategia leggera, roguelite e gestione di una fazione.
- Tono cupo, brutale e talvolta ironico; niente estetica infantile nonostante i protagonisti goblin.
- Temi possibili: guerra, potere, sopravvivenza, successione, vendetta, prigionia, tradimento e conseguenze della violenza.
- La maturità deriva da scrittura, atmosfera e dilemmi, non dalla necessità di rappresentare esplicitamente ogni atto violento.
- Le razzie possono essere una scelta del giocatore, ma devono avere costi e conseguenze nel mondo: non essere una fonte di ricompense priva di contraccolpi.

## 2. Genere e formato

- **Genere:** roguelite tattico a squadre con autobattaglie e gestione di una dinastia.
- **Prospettiva:** 2D laterale.
- **Struttura:** base strategica tra le spedizioni; ogni spedizione è una run composta da incontri e scelte.
- **Combattimento:** unità autonome, con ordini tattici semplici prima dello scontro e abilità attivabili o condizioni di comportamento.
- **Piattaforma iniziale proposta:** PC.
- **Tecnologia:** Godot 4, progetto 2D.
- **Modalità iniziale:** giocatore singolo, offline.

## 3. Pilastri di design

1. **La squadra è una dinastia.** Gli eredi hanno identità, tratti e potenziale diversi; la generazione successiva modifica le opzioni strategiche.
2. **Ogni spedizione racconta una guerra.** Nemici, eventi e ricompense compongono una breve campagna con un obiettivo riconoscibile.
3. **La preparazione conta più dei riflessi.** Formazione, classi, equipaggiamento e sinergie determinano l'esito; il combattimento rimane leggibile.
4. **Il potere ha un prezzo.** Saccheggiare, risparmiare, reclutare o vendicarsi cambia risorse, reputazione, alleanze e minacce future.
5. **Una run deve essere breve e rigiocabile.** La varietà viene da combinazioni di unità, eventi e scelte, non da una quantità iniziale ingestibile di contenuti.

## 4. Ciclo di gioco

### Ciclo di una spedizione

1. **Preparazione alla base**
   - Seleziona l'erede capitano e fino a tre combattenti.
   - Assegna equipaggiamento e una formazione.
   - Scegli una regione e un obiettivo: cacciare un mostro, razziare un avamposto, recuperare una reliquia o affrontare un rivale.
2. **Avanzamento**
   - Percorri una mappa a nodi con incontri, eventi, ripari e opportunità di rifornimento.
   - Ogni nodo presenta un incontro breve o una scelta con rischio e ricompensa.
3. **Combattimento**
   - Le unità si affrontano automaticamente nell'arena laterale.
   - Il giocatore osserva le sinergie, usa eventuali ordini limitati e interviene con abilità del capitano.
4. **Ricompensa e conseguenza**
   - Scegli fra risorse, equipaggiamento, reclute o vantaggi temporanei.
   - Le decisioni belliche modificano la reazione delle fazioni e gli eventi futuri.
5. **Obiettivo finale**
   - Completa una missione o sconfiggi il boss della regione.
6. **Ritorno alla base**
   - Converti il bottino in miglioramenti, gestisci feriti e successione, quindi prepara una nuova spedizione.

### Ciclo della dinastia

**Reclutare/allearsi → scegliere un erede → prepararlo → guidarlo in spedizione → acquisire esperienza e cicatrici → successione → eredi futuri con nuove combinazioni di tratti.**

La successione deve essere una decisione strategica, non soltanto un incremento lineare delle statistiche. Il giocatore può mantenere un erede esperto oppure investire in una nuova generazione con potenziale diverso.

## 5. Sistemi principali

### 5.1 Eredi, lignaggio e consorti

- Ogni erede ha nome, ritratto, classe, statistiche, tratti ereditati e un tratto personale.
- Due rami della dinastia contribuiscono al profilo dell'erede: per esempio, un tratto fisico e uno culturale/tattico.
- Il lignaggio influisce sulle probabilità e sulle opzioni di classe iniziale, non determina automaticamente la vittoria.
- Adulti di altre comunità possono diventare alleati o consorti attraverso diplomazia, debiti, liberazione, alleanze o accordi narrativi.
- La loro storia, i loro obiettivi e il loro consenso restano parte del mondo; non sono oggetti o statistiche da bottino.
- La coercizione e la prigionia possono comparire come temi o conseguenze della guerra, ma non sono un sistema di riproduzione forzata né un premio sessualizzato. I prigionieri possono essere liberati, riscattati, scambiati o coinvolti in eventi politici.
- Nel prototipo si usano pochi tratti leggibili e combinazioni controllate: niente simulazione genetica complessa.

### 5.2 Classi e ruoli

**Classi MVP proposte**

- **Bruto:** combattente resistente in prima linea.
- **Predone:** danno rapido e pressione sui bersagli vulnerabili.
- **Sciamano:** supporto, cura limitata o potenziamenti.

**Possibili classi successive**

- Tiratore, sabotatore, domatore, campione, stregone del sangue.

Le classi descrivono il ruolo tattico, mentre tratti ed equipaggiamento aggiungono variazione. Ogni unità deve restare leggibile senza obbligare il giocatore a studiare decine di statistiche.

### 5.3 Combattimento autobattler

- Formazione iniziale su due file: **prima linea** e **retroguardia**.
- Le unità scelgono bersaglio e azione in base a regole semplici e visibili.
- Statistiche iniziali: salute, attacco, velocità, armatura e portata.
- Ogni classe ha un'abilità distintiva; il capitano può avere un ordine speciale con usi limitati.
- Effetti di stato iniziali: sanguinamento, stordimento breve, protezione e ispirazione.
- Il giocatore può decidere se attivare manualmente il potere del capitano o impostare una condizione semplice.
- Nessun RNG opaco: mostrare sempre salute, bersagli, portate e motivi principali delle abilità.

### 5.4 Progressione durante la spedizione

- Esperienza e miglioramenti temporanei per i sopravvissuti.
- Equipaggiamento trovato o sottratto ai nemici.
- Ricompense alternative, così ogni nodo è una decisione e non solo un combattimento.
- Ferite o debuff temporanei rendono importante la gestione della squadra.
- Per il primo MVP non eliminare permanentemente gli eredi: la sconfitta termina o penalizza la run, mentre morte permanente e successioni traumatiche sono opzioni da valutare solo dopo aver verificato il tono e il bilanciamento.

### 5.5 Razzie, risorse e fazioni

**Risorse iniziali proposte**

- **Rottami e metallo:** equipaggiamento e fortificazioni.
- **Provviste:** spedizioni e recupero dei feriti.
- **Influenza:** accordi, reclutamento e politica.
- **Tesoro:** miglioramenti generali della base.

Le razzie possono fornire risorse e vantaggio militare, ma aumentano allarme, ostilità o rischio di rappresaglia. Le alternative includono caccia ai mostri, scambio, tributi, accordi temporanei e missioni di liberazione.

Le fazioni possono ricordare eventi importanti in forma semplice: una comunità saccheggiata può alzare le difese o allearsi con un rivale; una comunità risparmiata può commerciare o chiedere aiuto. Per l'MVP bastano due variabili per regione, come **paura** e **fiducia**.

### 5.6 Base del warlord

La base offre poche decisioni utili, con schermate snelle:

- **Sala del clan:** successione, lignaggio e gestione degli eredi.
- **Fucina:** acquisto e miglioramento dell'equipaggiamento.
- **Infermeria:** recupero delle unità ferite.
- **Mappa:** scelta della spedizione e consultazione delle minacce.

Per l'MVP la base è un menu funzionale, non un livello esplorabile.

## 6. Struttura narrativa

### Premessa

Il warlord ha riunito clan goblin divisi, ma la sua presa sul potere è fragile. Mostri, signori umanoidi e clan rivali contendono le terre di confine. Ogni spedizione allarga o indebolisce l'orda; ogni successione stabilisce quale idea di potere erediteranno i goblin.

### Temi e conflitti

- Unificazione contro autonomia dei clan.
- Sopravvivenza contro conquista.
- Paura come strumento di governo e fonte di ribellione.
- Eredità personale contro necessità politica.
- Le conseguenze delle razzie per chi le compie e per chi le subisce.

### Presentazione sostenibile

- Eventi testuali brevi con due o tre scelte.
- Ritratti e battute distintive per capitani, rivali e personaggi ricorrenti.
- Nessun albero di dialogo esteso nel prototipo.
- Tono maturo senza affidarsi a shock gratuito: le conseguenze si vedono nelle scelte, nelle fazioni e nello stato del clan.

## 7. Ambito: MVP e contenuti esclusi

### MVP: fetta verticale giocabile

- Una base con mappa, sala del clan, fucina e infermeria semplificate.
- Un clan goblin e una regione.
- Tre classi giocabili e una squadra fino a tre unità.
- Un sistema di eredi con un numero limitato di tratti ereditabili.
- Tre nemici comuni e un boss.
- Una spedizione breve con almeno un bivio e un evento.
- Un incontro di caccia e una missione di razzia con conseguenze chiare.
- Un equipaggiamento per slot o categoria, con poche varianti.
- Vittoria, sconfitta, ricompensa, ritorno alla base e avvio della spedizione successiva.
- Salvataggio locale dei dati essenziali.
- Asset provvisori coerenti e leggibili; non serve animazione definitiva.

### Fuori ambito per l'MVP

- Combattimento action controllato direttamente, platforming e fisica di precisione.
- Multiplayer, modalità online o servizi server.
- Mondo aperto, campagne ramificate lunghe o mappe generate proceduralmente complesse.
- Decine di classi, razze, biomi, boss o risorse.
- Dialoghi doppiati e cinematiche.
- Simulazione dettagliata della genetica o della riproduzione.
- Gestione esplorabile della base.
- Morte permanente degli eredi prima che il giocatore abbia provato il ciclo di successione.

## 8. Roadmap di produzione

### Fase 0 — Fondamenta

- Creare il progetto Godot 4 e fissare risoluzione, input e convenzioni.
- Scegliere stile visivo provvisorio, palette e formato dei dati.
- Definire il foglio di una unità e una bozza delle regole di combattimento.

**Uscita:** progetto avviabile, schermata iniziale e scena arena vuota.

### Fase 1 — Prototipo di combattimento

- Implementare unità, bersagli, attacchi automatici, salute e vittoria/sconfitta.
- Aggiungere tre ruoli e una formazione a due file.
- Rendere visibili bersagli, portate, danni e abilità.

**Uscita:** una battaglia ripetibile che permette di confrontare almeno due composizioni.

### Fase 2 — Spedizione e ricompense

- Aggiungere sequenza di incontri, bivio, evento e premio.
- Salvare lo stato della run mentre si procede.
- Aggiungere un boss e una condizione di completamento.

**Uscita:** una spedizione completa, dall'ingresso al risultato.

### Fase 3 — Dinastia e base

- Creare eredi con tratti e classi.
- Implementare scelta del capitano e passaggio alla generazione successiva.
- Collegare risorse, cura, equipaggiamento e base.

**Uscita:** ciclo completo tra generazioni e spedizioni.

### Fase 4 — Vertical slice e tono

- Sostituire i placeholder essenziali con arte, animazioni, effetti e audio coerenti.
- Aggiungere eventi narrativi e conseguenze delle scelte di razzia.
- Verificare leggibilità, durata, difficoltà e chiarezza dell'interfaccia.

**Uscita:** una versione breve che comunica la promessa del gioco e può essere testata esternamente.

### Fase 5 — Espansione controllata

- Aggiungere regioni, nemici, eventi, equipaggiamento e tratti solo se i test indicano bisogno di maggiore varietà.
- Valutare morte permanente, nuove modalità di spedizione e ulteriori opzioni di gestione.
- Preparare accessibilità, localizzazione, opzioni e distribuzione.

**Uscita:** contenuti aggiuntivi basati su sistemi già verificati, non nuovi sistemi in parallelo.

## 9. Architettura Godot proposta

Organizzare i dati separatamente dalle scene, usando `Resource` personalizzate per le definizioni statiche e nodi per la presentazione e l'esecuzione.

```text
res://
  scenes/
    main/
    base/
    expedition/
    battle/
    ui/
  scripts/
    managers/
    battle/
    dynasty/
    expedition/
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
├── BaseScreen
├── ExpeditionScreen
│   ├── RouteMap
│   └── EncounterScreen
│       ├── Battlefield
│       └── BattleHUD
└── GameState
```

### Responsabilità

- **GameState / RunManager:** stato della campagna e della spedizione attuale.
- **BattleController:** avvio, avanzamento e conclusione di uno scontro.
- **UnitDefinition / EnemyDefinition:** dati statici di unità e nemici.
- **TraitDefinition / EquipmentDefinition:** modificatori e regole dichiarative.
- **DynastyManager:** creazione degli eredi e passaggio della successione.
- **SaveManager:** serializzazione dei dati persistenti e versione del salvataggio.
- **ScreenRouter:** cambio fra base, spedizione, battaglia e risultati.

Evitare un manager globale che contenga ogni regola. Prima implementare solo ciò che serve al percorso completo dell'MVP.

## 10. Interfaccia e accessibilità

- Rendere evidente chi è in prima linea, chi sta attaccando e quanto è vicina la sconfitta.
- Mostrare statistiche dettagliate su richiesta, senza sovraccaricare la schermata di battaglia.
- Distinguere le squadre anche con forme e icone, non solo con il colore.
- Consentire di mettere in pausa gli scontri e rallentarli.
- Includere volume separato per musica ed effetti, riduzione di flash/scuotimenti e testo leggibile.
- Salvare dopo eventi importanti e prima di avviare una nuova run.

## 11. Verifica del design e criteri di successo

Il prototipo funziona se:

- una spedizione si può iniziare, completare o fallire e concludere alla base senza blocchi;
- una battaglia è comprensibile guardandola e leggendo le informazioni dell'interfaccia;
- cambiare composizione o formazione produce differenze tattiche osservabili;
- i tratti ereditati creano variazioni utili ma non garantiscono la vittoria;
- almeno una scelta di razzia ha un beneficio immediato e una conseguenza successiva riconoscibile;
- il ciclo offre una decisione significativa alla base e durante la spedizione;
- il giocatore capisce cosa può fare prima di impegnarsi in un sistema più ampio.

### Test manuali minimi

- Avviare una run nuova e arrivare al boss.
- Vincere e tornare alla base; poi ripetere perdendo uno scontro.
- Chiudere e riaprire il gioco per verificare caricamento e salvataggio.
- Provare una squadra composta da tre unità uguali e una squadra con ruoli diversi.
- Verificare che un tratto non applicabile o una risorsa insufficiente non causi errori o ricompense inconsistenti.

## 12. Rischi e mitigazioni

| Rischio | Effetto | Mitigazione |
|---|---|---|
| Troppi generi insieme | Progetto eccessivo prima di avere una run divertente | Mantenere l'autobattler come unica modalità di combattimento dell'MVP |
| Combattimento automatico passivo | Il giocatore non sente di influire sull'esito | Formazione, scelta di bersagli/ordini limitati, abilità del capitano e informazioni chiare |
| Progressione ereditaria sbilanciata | Alcuni tratti o discendenze diventano obbligatori | Limiti ai bonus, tratti con compromessi, test su più generazioni |
| Razzie senza conseguenze | Il tema morale diventa cosmetico e la scelta è ovvia | Collegare la violenza a paura, rappresaglie, reclutamento e diplomazia |
| Contenuti narrativi troppo ampi | Scrittura e localizzazione rallentano il prototipo | Eventi brevi e riutilizzabili; ampliare dopo i test |
| Produzione artistica costosa | Mancanza di contenuti visivi sufficienti | Usare sagome leggibili e palette coerente; limitare le animazioni iniziali |
| Permadeath frustrante | Il giocatore perde investimenti prima di comprendere il sistema | Escluderla dall'MVP e valutarla solo con test mirati |

## 13. Decisioni da prendere dopo il prototipo

Non sono prerequisiti per iniziare:

- Quanto spazio dare al controllo manuale durante la battaglia.
- Se la campagna è infinita, a capitoli o orientata a una singola conquista finale.
- Quanto è punitiva la sconfitta e se esiste la morte permanente.
- Quanto le fazioni persistono fra le spedizioni.
- Stile artistico definitivo e grado di rappresentazione esplicita della violenza.
- Prezzo, piattaforme aggiuntive e strategia di rilascio.

## 14. Prossimo passo operativo

Il primo prototipo deve dimostrare soltanto questo: **preparare tre goblin con ruoli distinti, osservarli combattere in un'arena laterale, scegliere una ricompensa e affrontare l'incontro successivo**. Se quel ciclo è leggibile e divertente, si aggiungono dinastia, base e conseguenze politiche; altrimenti si correggono le fondamenta prima di produrre altro contenuto.
