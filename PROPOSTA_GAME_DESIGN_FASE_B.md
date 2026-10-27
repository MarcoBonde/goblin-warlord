# Goblin Warlord — Fase B: proposta di game design

Stato: proposta per approvazione, successiva alla Fase A approvata. Questo documento definisce le scelte fondamentali; non è il GDD definitivo, non contiene i kit completi delle sei classi e non avvia lo sviluppo.

## 1. Base approvata e lettura delle fonti

Le risposte **F01–F08 compilate dall'autore in fondo a [AUDIT_DOCUMENTAZIONE.md](./AUDIT_DOCUMENTAZIONE.md)** sono state lette e prevalgono sulle ipotesi precedenti. L'approvazione dell'audit non viene interpretata come approvazione automatica delle raccomandazioni ancora aperte.

| Decisione | Stato attuale | Conseguenza per la Fase B |
|---|---|---|
| Guerriero, Barbaro, Ranger, Chierico, Stregone, Ladro | **Confermato — F01** | Sono le sei classi da progettare in Fase C per demo/MVP. |
| Quattro goblin schierati | **Confermato — F02** | Il vecchio limite di cinque è superato. Non viene riaperto il confronto quattro/cinque. |
| Massimo tre riserve, due nella prima fase | **Confermato — F02** | Cap finale della rosa: sette; cap iniziale: sei. Non significa che tutti i posti siano già occupati alla partenza. |
| Warlord esterno, fonte di passive e comandante | **Confermato — F03** | Non occupa uno dei quattro ranghi e non è una quinta unità bersagliabile. Un eventuale comando attivo specifico resta una proposta. |
| Carica della suprema al posto del cooldown | **Confermato — F04** | Nessun secondo cooldown sulle supreme. Generazione, costo e reset sono ancora da definire. |
| Stadi evolutivi desiderati | **Confermato — F05** | Si pianificano funzione e struttura. Le nuove abilità evolutive non vengono progettate ora. |
| Origini ispirate a umanoidi civilizzati del fantasy | **Confermato — F06** | È autorizzata la proposta di un catalogo; nomi, effetti e quantità non sono già approvati. |
| Kit recenti di CLASSI_E_ABILITA.md | **Confermato — F07** | Sono la base; non si ripropone la scelta fra kit vecchi e nuovi. Gli adattamenti necessari a turni e carica vanno motivati. |
| Atto uno in Accesso Anticipato, demo distinta | **Confermato — F08** | La demo verifica il ciclo; non deve assorbire automaticamente tutto il contenuto del primo atto. |

Restano confermati la campagna in tre atti verso la capitale, il single-player offline, il combattimento manuale automatizzabile, il danno persistente, la morte permanente con rara eccezione narrativa e il tono definito nel piano. Gli atti successivi restano subordinati alle risorse disponibili.

Altri riferimenti: [PIANO_PROGETTO.md](./PIANO_PROGETTO.md), [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md), le risposte nelle [valutazioni 1](./VALUTAZIONE_DESIGN.md), [2](./VALUTAZIONE_DESIGN_2.md), [3](./VALUTAZIONE_DESIGN_3.md) e i problemi della [valutazione 4](./VALUTAZIONE_DESIGN_4.md). Le descrizioni storiche dell'autobattler puro non tornano in vigore.

### Come leggere il resto

- **Confermato:** decisione dell'autore o regola documentata mantenuta, con fonte indicata.
- **Nuova proposta:** soluzione principale consigliata in questa fase; richiede approvazione.
- **Da validare:** parametro o risultato da verificare con prove. Un numero proposto non equivale a un sistema già bilanciato.

Salvo indicazione contraria, le regole operative delle sezioni successive sono **nuove proposte**. Approvare una struttura non obbliga a congelarne tutti i numeri prima dei test.

## 2. Direzione principale

La decisione ricorrente dovrebbe essere: **quale goblin faccio agire adesso, contro quale minaccia, e a cosa rinuncio per farlo?** Il percorso determina quali strumenti possiedo; ordine delle azioni, bersagli e protezione determinano come li uso.

La proposta conserva formazione e accesso ai bersagli come riferimento tattico ispirato a Darkest Dungeon, con meno vincoli sul lanciatore e senza introdurre sistemi paralleli di stress, gestione spaziale o risorse individuali granulari.

| Sistema | Soluzione principale consigliata | Vantaggio cercato |
|---|---|---|
| Campo | Quattro ranghi lineari; prima linea nei primi due ranghi vivi | Esposizione leggibile e targeting semplice |
| Azioni | Base, ordinaria, suprema; Difesa universale e scambio contestuale | Poche scelte ricorrenti, nessun turno inutilizzabile |
| Turni | Attivazioni alternate; scelta libera dell'alleato; coda nemica visibile | Decisioni di ordine senza una statistica Velocità |
| Intenti | Azione nemica impegnata, danno aggiornato, cambio bersaglio regolato | Previsioni affidabili senza nemici immobili alle conseguenze delle azioni |
| Suprema | Due segmenti di carica come prima ipotesi; accumulo per propria azione | Accesso comparabile per danno, protezione e cura |
| Warlord | Passive/artefatto e un ordine semplice per incontro; nessuna Autorità iniziale | Presenza del comandante con poco carico di gestione |
| Crescita | Livelli numerici; conoscenze per disponibilità; stadi qualitativi | Tre funzioni diverse, senza premi duplicati |
| Origini | Una passiva trasversale per origine, compatibile con tutte le classi | Combinazioni interessanti senza kit esclusivi per coppia |
| Sinergie | Stati e situazioni comuni; nessuna abilità dipendente da un partner preciso | Varietà anche nelle campagne sfortunate |
| Esplorazione | Mappa a nodi progettata, variazioni controllate, progressione utilizzabile prima del boss | Percorsi strategici con costo produttivo governabile |

## 3. Combattimento leggero: azioni, statistiche e conseguenze

### 3.1 Una decisione principale per attivazione

**Nuova proposta.** Ogni goblin vivo riceve una normale attivazione per round. In quell'attivazione sceglie una sola azione:

| Azione | Funzione | Costo |
|---|---|---|
| Attacco base | Danno affidabile, con i modificatori della classe | L'attivazione |
| Abilità ordinaria | Effetto caratteristico della classe | L'attivazione e il proprio cooldown |
| Suprema | Picco di potenza da preparare e scegliere | L'attivazione e tutta la carica |
| Difesa | Ridurre il danno in arrivo quando attaccare è meno utile | L'attivazione |
| Riposizionamento | Scambiarsi con un alleato adiacente | L'attivazione dell'esecutore |

Le tre azioni di classe restano in evidenza; lo scambio è contestuale sulla formazione. Non si aggiungono movimento libero, punti azione, mana o sottofasi per ogni goblin. Un attacco composto da più colpi è una sola azione, con un solo costo.

**Perché questa soluzione:** Difesa offre una risposta universale agli intenti, utile anche senza tank. Lo scambio dà un costo leggibile al cambiamento di esposizione. Non si raccomanda il movimento gratuito, che permetterebbe di ridistribuire ogni minaccia senza rinunciare al danno.

**Parametro da validare:** Difesa riduce inizialmente il danno ricevuto del 30% fino all'inizio della successiva attivazione del goblin. Non è uno scudo accumulabile. Più riduzioni analoghe non si moltiplicano: prevale quella maggiore; la combinazione con la difesa statistica avrà un tetto definito in C.

La classe deve funzionare già nel primo stadio con base, ordinaria e suprema. Gli stadi non servono a rendere finalmente disponibile il suo ruolo fondamentale.

### 3.2 Statistiche: conservare l'identità, ridurre i calcoli durante il turno

**Confermato nel piano:** Forza, Destrezza, Costituzione, Intelligenza, Saggezza e Carisma sono gli attributi previsti. Non vengono eliminati implicitamente.

**Nuova proposta:** niente distribuzione manuale di punti a ogni livello nella prima versione. Classe e livello determinano il profilo; origine ed equipaggiamento lo modificano. La schermata di combattimento privilegia Salute, danno/effetto dell'azione e mitigazione effettiva. Gli attributi sono consultabili nella scheda completa.

Per la prima validazione raccomando danno deterministico e nessuna precisione, schivata o probabilità di critico universale. Una casualità espressamente identitaria di un'abilità può esistere, ma va dichiarata prima della conferma. Non si aggiunge una statistica Velocità.

**Perché:** con ordine scelto, origine, equipaggiamento e bersagli esistono già più assi decisionali. Colpire un bersaglio raggiungibile non dovrebbe richiedere anche una probabilità nascosta. L'alternativa con precisione/critici è rinviabile se i test dimostrano che serve.

La Fase C dovrà dare ai sei attributi funzioni distinte e verificare eventuali attributi inutili. **Carisma non viene trasformato in Autorità**, né la risposta F03 autorizza una nuova valuta. Formule e numeri delle classi restano fuori da questo documento.

## 4. Formazione e targeting

### 4.1 Quattro ranghi, nessun requisito di posizione del lanciatore

**Nuova proposta:** ranghi numerati dalla posizione più vicina al nemico. Lo schema è speculare:

```text
Goblin:   R4  R3  R2  R1   |   R1  R2  R3  R4   :Nemici
          retrovia fronte  |   fronte retrovia
```

- I primi due ranghi occupati sono la prima linea; gli altri sono la retrovia.
- Un goblin può usare tutte le proprie azioni di classe da qualunque rango.
- La portata limita le **posizioni bersaglio**, non la posizione necessaria per lanciare l'abilità.
- La retrovia non riceve un bonus numerico universale: la protezione principale è l'inaccessibilità alla mischia ordinaria.
- I ruoli possono avere preferenze e sinergie di adiacenza, ma non requisiti che disabilitano il kit.

**Perché preferirlo ai vincoli di lancio per rango:** la formazione continua a decidere chi è esposto, mentre una spinta o una morte non costringono il giocatore a sprecare turni per recuperare comandi bloccati. È una semplificazione intenzionale del riferimento tattico, non una sua riproduzione integrale.

L'adiacenza corrisponde a ranghi consecutivi della stessa fazione. Non esistono diagonali o una seconda griglia nascosta.

### 4.2 Morte, avanzamento e riposizionamento

1. Alla morte l'unità viene rimossa; i superstiti avanzano immediatamente mantenendo il proprio ordine relativo.
2. Non restano cadaveri sul campo. L'eventuale evento di resurrezione usa il registro dei caduti, non un ostacolo occupante un rango.
3. Con due superstiti entrambi appartengono alla prima linea; con un superstite questo occupa R1.
4. Uno scambio volontario interessa due alleati adiacenti: solo chi lo avvia spende l'attivazione. Il compagno non recupera né perde un'azione già usata/disponibile.
5. Niente ingresso delle riserve durante lo scontro: rimane la preparazione prima della battaglia.

Le animazioni «alle spalle» non implicano automaticamente uno spostamento permanente fra gli schieramenti. Un'abilità che sposta davvero un'unità deve dirlo esplicitamente.

**Alternative scartate per il primo perimetro:** cadaveri da distruggere, buchi permanenti e unità che occupano più ranghi. Introducono casi di portata e interfaccia non necessari alle sei classi selezionate. Possono essere riesaminati in seguito, senza considerarli già parte del MVP.

### 4.3 Regole di portata e assenza di stalli

| Categoria | Bersagli ordinari |
|---|---|
| Base in mischia | Una delle prime due unità vive nemiche |
| Base a distanza o magico a distanza | Qualunque unità nemica viva |
| Specialista delle retrovie | Le posizioni indicate dalla specifica azione |
| Area | Gruppo di ranghi indicato; unità assenti semplicemente non vengono colpite |
| Supporto | Alleati vivi validi, secondo l'abilità; sé stessi solo se consentito |

L'attacco base di ogni classe deve avere almeno un bersaglio nemico legale finché esiste un nemico vivo, a meno di un controllo che impedisca l'azione. Gli attacchi specializzati possono essere temporaneamente inutilizzabili: non sono l'unico strumento della classe.

All'inizio della risoluzione si fissano le identità dei bersagli di un'area o di una sequenza di colpi. La compattazione dopo una morte non aggiunge automaticamente un nuovo bersaglio. I colpi residui destinati a un morto si perdono, salvo che l'abilità dichiari esplicitamente il passaggio a un altro bersaglio.

Un comando senza bersaglio valido non consuma attivazione, carica o cooldown: viene disabilitato prima della conferma con una ragione leggibile. Il giocatore può scegliere un'altra azione. Nessun consumo dipende da un tentativo fallito di cliccare un bersaglio.

### 4.4 Provocazione senza eccezioni opache

**Nuova proposta:** la provocazione restringe le azioni offensive a bersaglio singolo al provocatore **solo se questo è già raggiungibile**. Non estende la portata, non devia cure e non annulla gli attacchi ad area.

Se due provocazioni competono sullo stesso attaccante, prevale la più recente ancora valida. Se il provocatore muore o diventa irraggiungibile, resta la normale selezione dei bersagli. La UI mostra il vincolo prima di confermare l'azione.

Conseguenza voluta: un Guerriero in retrovia non può assorbire per provocazione gli attacchi di mischia che non lo raggiungono. Può invece attirare quelli a distanza. La posizione resta una scelta concreta.

**Perché:** una provocazione assoluta renderebbe il tank una soluzione universale; una provocazione solo probabilistica renderebbe inaffidabile la pianificazione. Il controllo deterministico entro portata conserva entrambi i ruoli.

## 5. Turnazione e iniziativa

### 5.1 Confronto e scelta

| Modello | Vantaggio | Limite per questo progetto | Valutazione |
|---|---|---|---|
| Iniziativa individuale con Velocità | Differenzia l'ordine tramite statistiche | Aggiunge una curva da bilanciare e rende meno immediato coordinare la squadra | Non consigliato per il primo sistema |
| Tutti gli alleati, poi tutti i nemici | Molto semplice | Favorisce eliminazioni prima di qualsiasi risposta e concentra troppe scelte consecutive | Troppo favorevole all'apertura offensiva |
| Attivazioni alternate con scelta dell'alleato | Il giocatore decide chi è urgente e il nemico risponde frequentemente | Va esplicitato il vantaggio numerico e il comportamento delle code | **Soluzione principale** |

### 5.2 Sequenza proposta

Un **round** comprende le attivazioni disponibili delle due fazioni. Una **attivazione** è la finestra in cui una singola unità risolve un'azione.

1. All'inizio del round vengono mostrati ordine e intenti nemici. Ogni goblin vivo e ogni nemico normale vivo riceve una attivazione.
2. Il giocatore apre scegliendo qualsiasi goblin non ancora attivato; il rango non impone l'ordine degli alleati.
3. Agisce il prossimo nemico disponibile nella coda visibile, fissata per quel round.
4. Si continua alternando. Quando una fazione esaurisce le proprie attivazioni, l'altra completa quelle residue.
5. Si risolvono gli effetti di fine round e si prepara quello successivo.

La coda nemica ordinaria segue i ranghi all'inizio del round, da R1 verso il fondo. Se le unità si muovono dopo, le attivazioni sono ancora legate alla loro identità: la coda non si riordina a sorpresa. I round successivi riflettono la nuova formazione.

Il giocatore apre ogni round: è una regola visibile, non un tiro di iniziativa. Un'eventuale imboscata è esclusa dal primo perimetro e richiederebbe un segnale prima di iniziare lo scontro.

**Perché non alternare automaticamente la fazione che apre ogni round:** si evita una sequenza imprevedibile di azioni a cavallo fra due round. Il vantaggio dell'apertura resta deliberato e andrà misurato, soprattutto nelle eliminazioni al primo round.

### 5.3 Casi limite

| Situazione | Risoluzione |
|---|---|
| Quattro goblin contro due nemici | G–N–G–N–G–G. Non si inventano azioni aggiuntive per compensare i due nemici. |
| Due goblin contro quattro nemici | G–N–G–N–N–N. La perdita di membri aumenta concretamente il rischio. |
| Muore un nemico prima di agire | La sua attivazione viene rimossa; non passa a un altro nemico. |
| Muore un'unità dopo aver agito | Non cambia il numero di azioni già risolte. |
| Un lato non ha più attivazioni ma ha unità vive | L'altro completa il round; non inizia un nuovo round in anticipo. |
| Nuovo rinforzo durante il round | Non riceve attivazione prima del round successivo. Nessuna catena infinita di evocazioni. |
| Sconfitta dell'ultimo goblin schierato | Fine della campagna secondo la regola approvata; nessun ingresso delle riserve. |
| Ultime unità delle due fazioni eliminate dallo stesso pacchetto di effetti | Prevale la sconfitta del giocatore: non resta nessuno a continuare la marcia. |

Per la prima versione, i nemici occupano al massimo quattro ranghi. **Proposta per i boss:** fino a due attivazioni distinte e anticipate per round, con un tetto di quattro attivazioni nemiche totali, inclusi gli aiutanti. L'ordine delle due finestre del boss rispetto agli aiutanti è fissato dal pattern e mostrato prima del round; sostituisce la normale coda per rango di quell'incontro. È un'eccezione dichiarata per rendere minaccioso un boss senza limitarsi ad aumentargli la salute; non raddoppia gli scatti degli effetti periodici. Pattern e numero effettivo saranno progettati in C.

### 5.4 Controllo e fine dell'azione

Per le sei classi iniziali privilegiare indebolimento, esposizione, protezione e provocazione rispetto alla perdita ripetuta del turno. Lo stordimento duro non fa parte delle azioni universali né deve essere ripetibile sull'attacco base.

Se in seguito un effetto fa saltare un'attivazione alleata, il goblin resta selezionabile: il giocatore sceglie quando consumare quella finestra, che risolve il salto e passa normalmente la mano al nemico. Non si cancellano in anticipo tutte le finestre controllate, alterando occultamente l'alternanza. Limiti ai controlli concatenati e resistenze dei boss restano da definire prima di includere tali effetti nei kit.

Un'azione multi-colpo termina prima di passare alla fazione avversaria. Ogni colpo applica danni e morti; le condizioni finali dello scontro vengono verificate al termine del pacchetto d'azione, senza inserire una cura successiva alla caduta per aggirare il divieto di resurrezione. Nessuna reazione genera una catena illimitata di altre reazioni.

## 6. Intenti, previsione e automazione

### 6.1 Nemici leggibili, capaci di reagire alle conseguenze

**Confermato:** in manuale sono mostrati bersagli e danni previsti; la previsione non è calcolata nell'automazione.

**Nuova proposta:** a inizio round il nemico impegna un'azione e il bersaglio per identità. Il giocatore vede anche quale nemico agirà dopo. Dopo ogni azione:

- il danno previsto si aggiorna per protezioni, scudi e indebolimenti;
- se il bersaglio resta vivo e legale, l'intento non viene sostituito opportunisticamente;
- provocazione e perdita di raggiungibilità possono cambiare il bersaglio secondo regole visibili;
- se serve un sostituto, la priorità standard è rango valido più avanzato, poi identità stabile per risolvere parità;
- se l'abilità non ha più alcun bersaglio valido, il nemico usa il proprio attacco base contro un bersaglio valido. Il cambio appare immediatamente dopo l'azione che lo ha provocato, prima della prossima scelta del giocatore.

Un pattern può dichiarare una priorità diversa, per esempio il ferito: deve essere visibile nell'ispezione e seguire un criterio deterministico. Non si tira nuovamente il bersaglio casuale a ogni aggiornamento della UI.

**Perché preferire questa soluzione:** intenti completamente ricalcolati cancellerebbero troppo spesso il valore della preparazione; intenti totalmente immobili farebbero attaccare bersagli inesistenti o fuori portata. Si conserva l'azione annunciata e si regolano esplicitamente le eccezioni.

Gli effetti casuali mostrano un insieme di esiti possibili, non una falsa cifra certa. Durante la scelta non si consuma casualità; una selezione casuale effettiva avviene solo alla risoluzione prevista dalla regola.

### 6.2 Automazione sullo stesso sistema

L'automazione non ha turni più rapidi in termini di regole, bonus nascosti o bersagli diversi. Usa la stessa alternanza, gli stessi costi e la stessa carica.

**Nuova proposta:** prima versione con poche personalità leggibili, che ordinano priorità comuni: proteggere una minaccia imminente, curare un alleato in pericolo, eliminare un nemico, infliggere danno. Le condizioni precise saranno definite per le sei classi in C. Nessuna personalità deve sprecare deliberatamente un'abilità senza effetto.

Le descrizioni «più vicino», «più ferito» e simili dei kit recenti diventano priorità automatiche **quando non sono esplicitamente dichiarate come vincoli dell'abilità**. La casualità identitaria dello Stregone è invece un'eccezione da conservare e rendere visibile, non una priorità da ignorare in manuale.

Si può attivare o disattivare l'automazione fra due azioni complete; la scelta di usare anche le supreme resta configurabile. Si può tornare in manuale al prossimo punto di scelta del giocatore. Le passive delle classi devono avere un effetto utile anche nel manuale, non soltanto scegliere al posto del giocatore.

## 7. Cooldown ordinari, carica delle supreme e limiti al recupero

### 7.1 Cooldown solo dove serve

Le ordinarie iniziano disponibili. Il cooldown si misura in **attivazioni proprie da attendere dopo l'uso**, non in azioni complessive delle due fazioni.

Esempio proposto: un'ordinaria con «Ricarica 1» usata al round 1 è bloccata nell'attivazione del round 2 e torna pronta al round 3. Con «Ricarica 2» si attendono le attivazioni dei round 2 e 3 e si riusa al round 4. La UI mostra il numero di proprie attivazioni ancora da attendere.

Il tempo avanza anche se si usa Difesa, ci si riposiziona o si salta l'azione per controllo. A fine battaglia i cooldown si azzerano. Questa convenzione va approvata per evitare che lo stesso «1 turno» significhi due cose diverse.

### 7.2 Una barra individuale comune alle regole delle supreme

**Confermato — F04:** la carica sostituisce il cooldown della suprema.

**Nuova proposta principale:**

- Barra a **due segmenti**, vuota all'inizio di ogni incontro.
- Una propria azione valida diversa dalla suprema aggiunge un segmento alla fine della sua risoluzione, fino al limite.
- Base, ordinaria, Difesa e scambio valido possono caricare. Un salto dovuto al controllo non carica.
- Il numero di bersagli, colpi, uccisioni o cure prodotte non moltiplica la carica.
- Una suprema richiede la barra piena, consuma la normale attivazione e tutta la barra; non ricarica sé stessa.
- La carica non si trasferisce al prossimo incontro e non si accumula in panchina.

**Cronologia:** azione al round 1 → un segmento; azione al round 2 → due; dal round 3 si può usare la suprema oppure conservarla e scegliere altro. Dopo una suprema al round 3, due nuove azioni permettono un secondo uso dal round 6.

**Perché non caricare principalmente da danni, uccisioni o colpi subiti:** queste fonti favorirebbero specifiche classi, squadre già vincenti o chi può colpire molti bersagli. Una regola per attivazione permette di confrontare le sei classi prima di introdurre eccezioni.

Il primo modello è volutamente regolare, vicino a un ritmo di preparazione: non si finge che una barra da sola generi profondità. La scelta nasce dal conservare la suprema, dalla rinuncia a un'azione diversa e dalle condizioni del campo. **Due segmenti e disponibilità al terzo round sono parametri da validare**, specialmente negli scontri brevi.

La Magia incanalata dello Stregone dovrà interagire con questa barra, senza aggiungere ora una seconda energia. È un adattamento del kit recente richiesto dal cambio approvato a carica, non un ritorno alle abilità storiche.

### 7.3 Recupero finito e scudi temporanei

**Problema:** il solo reset della carica non impedisce di lasciare vivo un nemico debole per recuperare tutta la salute prima del prossimo nodo.

**Nuova proposta principale:** le azioni che recuperano direttamente HP hanno un numero limitato di usi per combattimento, oltre all'eventuale cooldown. Prima ipotesi per l'ordinaria di cura: **due usi per incontro**. Una cura secondaria legata alla stessa azione consuma il medesimo uso, non un secondo contatore. La Fase C deve definire un limite anche per ogni futura fonte ripetibile di recupero HP; niente rigenerazione materna illimitata nella prima selezione.

Non si aggiunge mana: il costo è visibile sulla capacità, per esempio «2/2». Le classi che curano mantengono attacchi utili dopo l'esaurimento delle cure. Il cooldown evita di concentrare tutti gli usi in due attivazioni consecutive; il limite impedisce un recupero infinito aspettando.

**Scudi:** sovracura ancora convertita in scudo, come nel piano. Proposta di limite iniziale al 25% della salute massima; applicazioni diverse mantengono il valore maggiore invece di sommarsi. Il valore conservato mantiene la propria scadenza; una nuova applicazione lo sostituisce solo se almeno equivalente. Lo scudo scade alla fine del round successivo a quello di applicazione e sparisce comunque a fine battaglia.

**Perché rispetto a un timer punitivo:** un limite esplicito alle cure affronta la fonte del recupero gratuito senza fare comparire danni arbitrari dopo un certo numero di round. Rimane possibile usare bene le cure disponibili; non è garantita l'assenza di ogni incentivo a prolungare lo scontro, che andrà misurato.

Nessuna cura è usabile liberamente fuori battaglia: lì operano provviste e servizi dei nodi. L'eliminazione del nemico finale conclude lo scontro al termine del pacchetto d'azione già in risoluzione, come in §5.4; non concede una successiva attivazione o fase gratuita di cure.

## 8. Warlord: comando significativo con poco carico

**Confermato — F03:** il Warlord resta esterno, concede passive e comanda. Non può morire sul campo come un membro della squadra.

**Nuova proposta principale:** tre componenti, con funzioni diverse:

1. **Partenza:** determina opzioni iniziali e conoscenze già disponibili, come previsto dal piano.
2. **Passiva/artefatto distintivo:** orienta la campagna senza rendere obbligatorio continuare con la stessa famiglia di classi.
3. **Un ordine attivo per incontro:** un intervento semplice, scelto prima dell'azione di un goblin e confermato insieme a essa. Non occupa un rango e non dà una seconda azione completa.

Il primo ordine da provare può applicare Protezione a un alleato esposto. È un esempio funzionale per valutare il comando, non il kit definitivo dei tre Warlord. Non infligge una raffica autonoma, non resuscita, non riempie la carica e non permette di intervenire a metà di un attacco nemico.

Non si introduce **Autorità** nella prima versione. Un indicatore «ordine disponibile/usato» basta. Il nome Warlord deve risultare significativo soprattutto nelle decisioni di squadra e nella passiva, senza creare una seconda rotazione di abilità.

**Perché rispetto alle alternative:** solo una passiva rischia di rendere il comandante poco percepibile; una risorsa di comando con più ordini aggiunge un'altra economia non ancora dimostrata. Un singolo intervento permette di misurarne l'utilità prima di moltiplicare le scelte.

In automazione l'ordine segue una priorità visibile e può essere escluso dall'uso automatico. Non cambia il bilanciamento di base né le ricompense. Uso automatico e potenza esatta andranno provati, non dichiarati equivalenti al manuale.

## 9. Livelli, conoscenze e stadi: tre funzioni separate

### 9.1 Soluzione principale

| Sistema | Funzione proposta | Cosa non fa |
|---|---|---|
| Livello individuale | Crescita numerica contenuta nella campagna | Non cambia classe e non aggiunge pulsanti ogni livello |
| Conoscenze | Disponibilità di classi, origini e successive alternative | Non sono contemporaneamente la principale esperienza individuale |
| Stadio | Evoluzione qualitativa delle possibilità dell'individuo | Non è un secondo livello composto solo da percentuali |
| Tratti | Scelte di specializzazione, quando introdotte | Non diventano un'altra valuta o un contatore per ogni abilità |
| Equipaggiamento | Specializzazione tramite i tre slot esistenti | Non serve a rendere funzionante il kit di base |
| Meta-progressione | Nuove opzioni fra campagne | Non trasferisce automaticamente individui e crescita del tentativo sconfitto |

**Perché:** nel piano le soglie per nemico possono dare unità, livello o tratto. Separare i compiti rende comprensibile cosa si sta ottenendo e impedisce che la scelta del percorso controlli tutte le forme di potenza contemporaneamente.

Questa è una modifica proposta alla progressione precedente, non una decisione già approvata in F01–F08.

### 9.2 Livelli e riserve

**Nuova proposta:** esperienza per incontro vinto, uguale per tutti i goblin vivi della rosa, attivi e riserve. Il premio è definito dall'incontro e dalla sua difficoltà; non viene diviso fra i membri e non aumenta con colpi finali, cure ripetute o evocazioni eliminate.

Proposta iniziale di perimetro: livelli 1–6 nel primo atto; una progressione complessiva fino a 12 è soltanto un riferimento per il futuro gioco completo. La curva XP e i valori esatti appartengono a C.

La crescita per livello dovrebbe restare contenuta: come ordine di grandezza da verificare, circa +5% di salute massima e +3% di potenza rispetto ai valori di livello 1 per livello aggiuntivo, senza moltiplicazione composta. Cinque livelli aggiuntivi significherebbero circa +25% salute e +15% potenza, non il raddoppio del ruolo tattico.

Il livello non cura: la salute corrente assoluta non aumenta automaticamente quando cresce il massimo. Nessuna distribuzione manuale ripetitiva dei punti attributo nella prima versione.

**Perché rispetto alla sola esperienza degli schierati:** le riserve devono poter essere scelte in base all'incontro, non punite per essere state conservate. Non si richiedono squadre sempre allo stesso livello: ingressi in momenti diversi e differenze di esperienza restano possibili.

### 9.3 Reclute utilizzabili senza azzerare il costo della morte

Il livello di arruolamento dipende da traguardi di campagna già raggiunti, non dalla media dei superstiti. Il primo atto può offrire, indicativamente, reclute di livello 1 all'inizio, 2 dopo il primo blocco di incontri e 3–4 nella parte finale. È una tabella da calibrare, non una scalatura dinamica contro il giocatore.

Una nuova origine scoperta tardi deve poter essere usata senza ripartire da livello 1. Le reclute non arrivano necessariamente al livello del veterano migliore, né con i suoi tratti e oggetti.

La morte conserva peso: si perde l'individuo, la sua esperienza eccedente il minimo di arruolamento e la specializzazione acquisita. **Proposta sugli oggetti:** il bottino del caduto viene recuperato se la squadra vince; non in caso di annientamento. Riassegnarlo rispetta comunque la regola di accettazione per rarità. Si evita che una singola perdita cancelli anche tre investimenti senza introdurre la resurrezione.

**Confermato:** se muoiono tutti gli attivi, le riserve fuggono e il tentativo termina. Il recupero qui proposto riguarda esclusivamente perdite parziali.

### 9.4 Stadi: pianificarli senza progettare ora le nuove abilità

**Confermato — F05:** gli stadi sono desiderati; l'eventuale espansione delle abilità va tenuta in considerazione, non sviluppata adesso.

**Nuova proposta di struttura:** tre stadi di esperienza e maturazione guerriera, con nomi di lavoro **Recluta → Temprato → Veterano**. Non si assume una simulazione dell'età biologica durante pochi giorni di marcia.

| Stadio | Collocazione proposta | Funzione futura |
|---|---|---|
| I — Recluta | Alla partenza e nella prima parte della campagna | Kit già completo e funzionante |
| II — Temprato | Prima opportunità circa a metà dell'atto uno, in un nodo di creazione/sviluppo | Prima trasformazione qualitativa di una possibilità già esistente |
| III — Veterano | Riservato agli atti successivi, indicativamente dopo l'atto due | Ulteriore specializzazione, senza essere prerequisito della demo |

L'accesso allo stadio II richiede un traguardo di campagna e un livello minimo, inizialmente 3, poi una scelta nel nodo dedicato con costo in tesoro. Non si aggiunge una valuta «evoluzione» o una barra separata. Le reclute tardive possono essere offerte con accesso allo stadio già disponibile nella campagna, senza ripetere l'inizio dell'atto.

Il costo deve competere con reclutamento e acquisti, senza rendere automaticamente dominante evolvere un solo membro. L'evoluzione non cura, non resuscita e non aumenta il numero di attivazioni.

**Vincolo di leggerezza proposto:** in battaglia restano tre slot di azioni di classe. Futuri sblocchi evolutivi potranno modificare o sostituire un'azione equipaggiata, oppure dare una passiva, invece di aggiungere indefinitamente nuovi pulsanti. Nessuna variante evolutiva delle sei classi viene definita in questa fase.

**Perché rispetto a uno stadio per nuovo atto:** la prima release contiene soltanto l'atto uno e deve poter mostrare la caratteristica desiderata. Numero, nomi, costo, livello minimo e collocazione degli stadi sono ancora da approvare/validare; l'esistenza degli stadi non lo è più.

## 10. Origini materne e classi

### 10.1 Due assi indipendenti

**Confermato come direzione:** classe e origine sono componenti distinte. La classe rimane fissa e definisce le azioni; l'origine materna fornisce una passiva.

**Nuova proposta:** ogni origine disponibile è compatibile con tutte le sei classi. Non esistono classi vietate per origine, kit esclusivi per coppia o un'origine necessaria per compensare una classe incompleta. La disponibilità nel nodo dipende dalle conoscenze, non da una combinazione sempre garantita.

La passiva può favorire uno stile senza risultare ugualmente forte in ogni squadra. Non deve però fare soltanto «Forza per combattenti, Intelligenza per maghi»: la combinazione diventerebbe una scelta quasi automatica.

### 10.2 Primo insieme candidato

**Nuova proposta:** profilo iniziale goblin più due origini umanoidi fantasy, elfica e nanica. Il profilo materno goblin è una proposta esplicita, non una scheda già esistente nei vecchi documenti. I nomi seguenti sono generici e provvisori.

| Origine candidata | Unica passiva proposta, come direzione di lavoro | Utilità trasversale |
|---|---|---|
| Goblin — Tenacia | La prima volta che l'unità scende sotto metà salute in uno scontro ottiene una breve Protezione | Riduce il rischio di perdita sia dei combattenti esposti sia dei supporti raggiunti |
| Elfica — Precisione d'apertura | Il primo attacco base riuscito dello scontro applica Vulnerabilità dopo il proprio danno | Qualunque classe prepara un bersaglio per la successiva azione della squadra |
| Nanica — Tempra | Scudo iniziale piccolo e temporaneo, soggetto alle stesse regole degli altri scudi | Aumenta il margine iniziale di qualsiasi ruolo, senza rigenerare salute indefinitamente |

Sono esempi sufficienti a confrontare le combinazioni, non un catalogo definitivo o una promessa artistica. Valori e soglie esatte saranno calibrati con le classi.

Esempio: un Guerriero di origine elfica può attaccare per preparare un nemico prima di difendere; uno di origine nanica assorbe meglio la prima pressione. Un Chierico elfico ha un motivo ulteriore per usare Fiamma sacra; uno nanico può sopravvivere meglio a un attacco alle retrovie. Le azioni restano quelle della stessa classe.

**Perché questo insieme rispetto a doppia arma, slot extra o rigenerazione:** usa stati già necessari al combattimento, non moltiplica slot, animazioni o fonti di cura. Le idee precedenti restano nella banca di design, ma la riduzione del cooldown della suprema è incompatibile con F04 e dovrà essere ripensata se recuperata.

Non si trasferiscono alla campagna successiva personaggi o intere rose. Le origini sbloccate persistentemente sono opzioni di partenza o disponibilità futura secondo la meta-progressione, da distinguere dalle conoscenze raccolte nel tentativo.

## 11. Sinergie ampie, senza coppie obbligatorie

### 11.1 Vocabolario limitato

**Nuova proposta principale:** le sei classi condividono poche condizioni universali. I nomi narrativi delle abilità non creano automaticamente un nuovo tipo di stato.

| Condizione | Regola di lavoro proposta | Limite di complessità |
|---|---|---|
| Vulnerabilità | Potenzia il prossimo attacco diretto ricevuto | Una carica; un'azione multi-colpo la consuma una volta e ne applica il beneficio all'intera azione; niente moltiplicazione di marchi esclusivi |
| Indebolimento | Riduce il danno della prossima azione offensiva | Non toglie l'intera attivazione |
| Danno periodico | Danno a fine round per una breve durata dichiarata | Un solo scatto per round, anche su boss con due attivazioni; potenza e accumulo limitati in C |
| Protezione | Riduzione temporanea del danno ricevuto | Non accumula riduzioni analoghe; tetto con la difesa |
| Scudo | Assorbimento temporaneo prima degli HP | Limiti e scadenza di §7.3 |
| Provocazione | Restrizione del bersaglio singolo entro portata | Regole di §4.4 |

Salvo una specifica eccezione dell'abilità, gli effetti dichiarati «dopo il danno» si applicano al termine dell'intera azione, non fra i suoi colpi. Non modificano retroattivamente il danno che li ha applicati. Vulnerabilità e Indebolimento non consumati scadono entro la fine del round successivo all'applicazione; il danno periodico mostra chiaramente gli scatti residui. Non si sommano più copie dello stesso effetto per ottenere aumenti illimitati.

Questo non è ancora il catalogo completo degli status: formule, durate dei singoli kit e conversioni dei tratti restano in C. La proposta da approvare è riutilizzare un linguaggio ristretto e deterministico.

### 11.2 Cosa rende flessibile una sinergia

- La marca del Ranger dovrebbe usare o veicolare una vulnerabilità utile a più attaccanti, non una chiave esclusiva per il Ladro.
- Il Ladro beneficia di un nemico ferito da qualunque fonte; non richiede una particolare classe che lo prepari.
- La protezione permette a diversi goblin di restare esposti; non serve a rendere giocabile una sola coppia.
- Il danno periodico continua a fare pressione mentre un alleato cura, difende o cambia posizione.
- Il Barbaro può sfruttare la protezione di più fonti, ma il kit non deve presupporre di essere continuamente guarito dal Chierico.

Le sei classi approvate coprono ruoli, non sei posti obbligatori in una squadra da quattro. Duplicati ammessi quando disponibili; nessun bonus automatico per avere quattro classi diverse. Ogni classe deve poter contribuire con almeno tre compagni differenti: è un criterio della Fase C da dimostrare, non un risultato già raggiunto.

**Perché rispetto a combo esclusive:** l'accesso alle unità dipende dal percorso. Una sinergia che richiede due nomi precisi trasformerebbe una ricompensa mancante in una squadra incompleta. La sinergia generica modifica invece il valore relativo di più opzioni.

### 11.3 Oggetti e tratti: preservare le decisioni, riconoscere il rischio

**Confermato nel piano:** arma, armatura e speciale; sostituzione accettata soltanto con rarità strettamente superiore, scelta di rifiutare il drop.

Non si rimuove questa regola per facilitare le combinazioni. **Proposta:** mostrare l'impegno prima dell'assegnazione e non richiedere set o oggetti precisi per le prime sinergie. Niente set nella prima validazione. Inventario e gestione degli oggetti sostituiti saranno specificati successivamente.

Rimane un conflitto da testare: una squadra con origini e ruoli flessibili può essere bloccata da un equipaggiamento assegnato presto. Non si dichiara risolto questo rischio soltanto perché il drop può essere rifiutato.

## 12. Ritmo della campagna, esplorazione e reclutamento

### 12.1 La scelta del nodo è l'esplorazione principale

**Nuova proposta:** mantenere il viaggio tramite mappa a nodi. Niente camminata esplorabile o secondo sistema di movimento. «Esplorazione» può descrivere eventi e scoperte, senza richiedere un nuovo tipo di nodo autonomo.

La topologia è progettata a mano. Per le campagne successive si possono selezionare varianti da pochi schemi verificati e assegnare incontri/eventi da insiemi compatibili con profondità e ricompense. Le composizioni nemiche restano progettate, non assemblate casualmente.

**Perché rispetto alla proceduralità completa:** controlla la curva e il costo dei contenuti, lasciando varietà nella rotta e nelle disponibilità. Rispetto a una sola mappa immutabile, la selezione controllata aiuta a non risolvere tutte le campagne memorizzando un percorso.

Resta il divieto di ripetere lo stesso incontro nella singola campagna. Riutilizzare una famiglia nemica è ammesso: ciò che varia significativamente è composizione, regola o problema tattico, non solo un numero di salute.

### 12.2 Obiettivi di durata da validare

| Elemento | Ipotesi iniziale | Scopo |
|---|---|---|
| Battaglia normale | 2–4 round; 30–90 secondi dopo l'apprendimento | Una decisione tattica riconoscibile, senza consumare tutte le risorse |
| Élite | 4–6 round; 2–3 minuti | Richiede un investimento o accettazione del rischio |
| Boss | 5–8 round; 3–5 minuti | Verifica più scelte e un pattern leggibile |
| Demo | 8–10 nodi visitati; circa 20–30 minuti | Un ciclo di percorso, sblocco, creazione, crescita e boss |
| Primo atto | 12–14 nodi visitati; circa 30–45 minuti | Spazio per adattare la squadra senza diluire il ritmo |

I tempi includono decisioni e animazioni; demo e atto includono anche lettura, ricompense e gestione. Non sono somme garantite: saranno misurati separando prima partita, partite successive e automazione. Trenta secondi è realistico come obiettivo soltanto per alcuni incontri brevi, non per ogni battaglia con quattro goblin.

Le animazioni brevi, il comando rapido sull'azione già selezionata e l'assenza di finestre ridondanti servono al ritmo. Nessun limite di tempo reale alla scelta del giocatore e nessuna sconfitta automatica perché si supera il target di round.

### 12.3 Conoscenze e luoghi di creazione

**Nuova proposta:** conoscenze assegnate per famiglia da una tabella dell'incontro. Un élite può concedere più progresso di molti avversari deboli. Il premio non cresce con nemici evocati o rigenerati all'infinito.

Le soglie candidate 5/10/15/20 diventano, se mantenute per la prima prova, **punti di conoscenza**, non corpi necessariamente eliminati. È una modifica esplicita al modello precedente. Le ricompense delle soglie aprono disponibilità, non sostituiscono l'esperienza del livello.

I contatori di conoscenza si azzerano a ogni campagna. Gli sblocchi persistenti registrano le opzioni disponibili per le future partenze, senza trasferire il numero accumulato o saltare automaticamente tutte le soglie.

Il nodo di creazione/sviluppo — nome italiano da fissare per Breeding Grounds — consente di:

- creare un individuo da classe e origine conosciute e disponibili;
- usare il livello di arruolamento previsto per quel punto della campagna;
- accedere allo stadio consentito, con costo in tesoro;
- gestire la saturazione della rosa con rifiuto del reclutamento o congedo esplicito.

Nessuna nuova valuta: tesoro per gli investimenti, provviste per il recupero. Compenso del congedo e costo di creazione devono impedire il ciclo redditizio crea → caccia → ricrea. Non si crea un goblin gratis dopo ogni battaglia.

**Vincolo di percorso proposto:** ogni rotta deve offrire uno sblocco utile e un nodo di creazione accessibile entro due tappe da quello sblocco, con almeno uno scontro prima del boss per usarlo. La demo deve mostrare almeno un ciclo completo; le quantità di conoscenza vanno scelte in funzione di quel vincolo, non viceversa.

### 12.4 Frequenza di gestione e servizi

Prima di ogni battaglia rimangono consentiti cambio di squadra, posizioni e consultazione dei membri. La gestione lunga si concentra su creazione, riposo e mercante. Una ricompensa ordinaria non dovrebbe imporre di aprire sette schede.

**Nuova proposta per partire:** quattro goblin nel prototipo e nella demo, anziché uno o due come nella premessa storica. I quattro ruoli tutorial possono essere introdotti con un primo incontro guidato. Il limite iniziale è di due riserve; gli individui che occupano questi posti si acquisiscono durante il percorso. Si evita che l'inizio con una o due unità non rappresenti affatto la tattica promessa. Non si presume di possedere tutte e sei le classi dall'inizio.

**Confermato come vincolo del piano:** due mercanti, cinque élite e cinque riposi riguardano il grafo complessivo del primo atto, non ogni rotta. Il tesoro/razzia a metà riguarda invece tutti i percorsi. Questi minimi non si applicano automaticamente alla demo e restano un costo di produzione da misurare.

Provviste e cure di viaggio rimangono. **Proposta di controllo:** mostrare prima del movimento il consumo e il recupero previsti; dare una priorità configurabile senza aprire una finestra obbligatoria a ogni tratta. Quantità, inclusione delle riserve e possibilità di disattivazione saranno definite con l'economia, non inventate dal combattimento.

Il riposo dovrebbe offrire una scelta fra recupero affidabile e preparazione tattica temporanea. Non deve diventare un secondo nodo di creazione con tutti gli stessi servizi. Né riposo né avanzamento di stadio sono un modo per aggirare il divieto di resurrezione.

## 13. Conflitti e migrazioni rispetto ai documenti precedenti

I file precedenti restano invariati in questa fase: questa tabella rende visibile dove dovranno essere allineati dopo l'approvazione.

| Tema | Documento precedente | Stato e trattamento attuale |
|---|---|---|
| Squadra e rosa | Piano: cinque attivi e cinque riserve | **Superato da F02:** quattro attivi, tre riserve al massimo, due inizialmente. |
| Suprema | Piano/catalogo: cooldown lungo | **Superato da F04:** carica. I valori di generazione sono nuove proposte, non vecchi cooldown rinominati. |
| Passive materne sulla suprema | Esempio «un turno di cooldown in meno» | Incompatibile con F04: da convertire o rinviare, senza inventare ora una seconda regola. |
| Kit | Alternative storiche nelle risposte della seconda valutazione | **F07 conferma i kit recenti.** Si adattano le parti incompatibili, non si riapre la scelta storica. |
| Warlord | Piano incentrato su rosa e artefatto; presenza in campo aperta nell'audit | **F03 conferma l'esterno.** L'ordine singolo è una proposta aggiuntiva. |
| Stadi | Assenti dal piano come sistema generale | **F05 li desidera.** Numero, collocazione e accesso sono nuove proposte; abilità evolutive rinviate. |
| Turni e velocità | Struttura aperta, residui di «velocità d'attacco» nei kit | Proposta di alternanza senza Velocità; eventuali effetti temporali vanno tradotti senza creare azioni extra per inerzia. |
| Bersagli dei kit | Vicino/ferito/pericoloso spesso nel testo dell'azione | Proposta di distinguere vincoli, priorità automatiche e casualità esplicita; la scelta manuale resta. |
| Soglie nemiche | Sblocco, livello o tratto da conteggi 5/10/15/20 | Proposta di punti per incontro e separazione dall'esperienza individuale. Richiede approvazione. |
| Cura/scudo | Conversione della sovracura, senza limiti dettagliati | Regola mantenuta; limiti d'uso, cap e scadenza sono nuovi. |
| Partenza | Piano: uno o due goblin | Proposta di quattro nel prototipo/demo, motivata dalla verifica della tattica di squadra. |
| Recupero equipaggiamento | Oggetti del caduto non definiti | Proposta di recupero solo dopo vittoria, senza riabilitare l'individuo. |
| Mappa | Authored e nessuna composizione casuale; qualche riferimento storico alla casualità | Proposta di schemi e assegnazioni controllate, conservando incontri progettati e verificati. |
| Rarità degli oggetti | Sostituzione solo con rarità superiore | Confermata nel piano, non rimossa. Il conflitto con la riconfigurazione resta un rischio da provare. |

## 14. Cosa deve verificare la Fase C

Dopo l'approvazione delle strutture, la Fase C progetterà i sei kit completi, confronterà valori e simulerà gli incontri. Le principali domande di verifica saranno:

- La scelta di chi agisce adesso produce alternative reali, o basta attivare sempre il massimo danno?
- La prima linea e la compattazione cambiano i bersagli senza rendere inutili le classi?
- Il vantaggio numerico e l'apertura del giocatore consentono risposte nemiche significative?
- La prima suprema compare abbastanza presto e vale la rinuncia a un'altra azione?
- La riserva di cure limita il recupero gratuito senza rendere la cura una tassazione obbligatoria?
- È possibile una squadra senza Chierico e una senza Guerriero, oltre a quelle con entrambi?
- Le tre origini candidate restano utili su tutte le sei classi, pur con differenze di valore?
- Una recluta ottenuta dopo una perdita parziale può contribuire prima del prossimo boss?
- Il primo atto può mostrare uno stadio qualitativo senza aumentare il carico di comandi?
- I tempi si avvicinano agli obiettivi anche dopo aver incluso ispezione, animazioni e ricompense?

Non vengono ancora prodotte la matrice 6×6, le sei composizioni complete, le simulazioni numeriche o le abilità di ogni stadio. Nessun test giocato è stato eseguito e nessun equilibrio è dichiarato raggiunto.

## 15. Decisioni da approvare prima della Fase C

Non richiedono una seconda approvazione le scelte F01–F08 già compilate. Restano da approvare **queste nuove soluzioni**, anche con modifiche mirate:

| ID | Decisione proposta | Approvazione / correzioni |
|---|---|---|
| B01 | Quattro ranghi lineari; primi due vivi in prima linea; lancio da ogni rango; compattazione immediata; niente cadaveri o corpi multirango iniziali; Difesa e scambio come azioni universali. | approvato |
| B02 | Alternanza con scelta dell'alleato, coda nemica pubblica, giocatore primo, niente Velocità; casi asimmetrici come descritti e fino a due attivazioni dichiarate per un boss. | approvato |
| B03 | Intenti nemici impegnati e aggiornamenti deterministici; provocazione solo su bersaglio singolo raggiungibile; danno deterministico senza critico/schivata universali iniziali. | approvato |
| B04 | Carica da propria azione non suprema, senza bonus per colpi/uccisioni; reset fra incontri; prima prova con due segmenti. Cooldown ordinari con la convenzione proposta. | approvato |
| B05 | Cure HP con usi limitati per incontro; scudi temporanei, non sommati e azzerati a fine battaglia. Due cure e cap scudo al 25% come valori iniziali da testare. | non scudi che durano 1 turno, massimo 2 se si tratta di un ultimate o di passive che lo permettono di aumentare |
| B06 | Warlord con passive/artefatto e un ordine semplice per incontro; nessuna risorsa Autorità nella prima versione. | approvato |
| B07 | XP da vittorie condivisa con le riserve; conoscenze separate dai livelli e azzerate per campagna; livello d'arruolamento per traguardi; recupero degli oggetti dei caduti dopo vittoria. | riserve prendono lo stesso xp delle altre, non è proprio una condivisione, ma proprio esperienza di gruppo... potremmo fare che è il warlord a livellare e di conseguenza salgono tutti i goblin assieme |
| B08 | Tre stadi come struttura, prima evoluzione nell'atto uno e accesso nei nodi con tesoro; mantenere tre azioni di classe equipaggiate. Niente progettazione delle nuove abilità evolutive adesso. | approvato |
| B09 | Tutte le origini compatibili con tutte le classi; primo catalogo candidato goblin/elfico/nanico con una passiva trasversale ciascuno; stati condivisi per le sinergie. | approvato |
| B10 | Partenza a quattro nella demo; mappa progettata con variazioni controllate e ciclo sblocco–creazione utilizzabile prima del boss. Durate e quantità di tappe come obiettivi di test. | partenza a 2 per rendere le cose più semplici e poi aggiungiamo 1 goblin alla volta come ricompensa iniziale tutorial  |

L'approvazione può riguardare l'impianto lasciando esplicitamente liberi i parametri numerici per il bilanciamento. La Fase B si conclude qui: la progettazione completa delle classi e l'implementazione richiedono i passaggi successivi autorizzati dall'autore.
