# Goblin Warlord — Valutazione del design e quaderno delle decisioni

Data: 23 ottobre 2026. Fonti: [PIANO_PROGETTO.md](./PIANO_PROGETTO.md) e [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md), nelle versioni attuali.

Questa è una valutazione di pre-produzione: giudica la coerenza delle regole descritte e i rischi prevedibili, senza attribuire al gioco risultati che richiedono una build e playtest. Le raccomandazioni sono proposte, non modifiche già approvate. I documenti di partenza restano invariati.

## 1. Giudizio complessivo

**Il progetto ha una direzione riconoscibile e merita un prototipo mirato. Non è ancora sufficientemente specificato per avviare la produzione estesa di sistemi e contenuti.** La parte più promettente è il legame fra percorso, nemici affrontati e nuove possibilità per l'orda. Se questo legame produce scelte leggibili, può distinguere Goblin Warlord da un normale gioco di combattimenti a squadre con mappa ramificata.

La principale fragilità è l'interazione fra molti sistemi ancora aperti: sei attributi, classi, specie, tratti, talenti, livelli, oggetti, set, personalità e artefatti. Ognuno può essere sensato da solo; insieme rischiano di rendere poco chiaro perché una squadra funzioni e di moltiplicare il lavoro di bilanciamento prima che sia provato il divertimento del combattimento.

Non serve definire ora tutti i numeri o le 28 classi. Serve invece definire il contratto minimo delle regole: chi agisce, quali bersagli può scegliere, quando scadono gli effetti, cosa resta dopo lo scontro e quali conseguenze il giocatore può conoscere prima di decidere.

| Area | Valutazione attuale | Conseguenza operativa |
|---|---|---|
| Visione e limiti generali | Chiari: conquista, squadra piccola, tre atti, single-player | Conservare questi vincoli senza riaprire sistemi fuori ambito |
| Identità distintiva | Promettente, ancora da dimostrare | Verificare che affrontare nemici diversi cambi davvero la squadra |
| Combattimento | Direzione chiara, grammatica incompleta | Scrivere regole ed esempi prima di costruire molti kit |
| Classi | Buona banca di idee, specifiche esecutive incomplete | Adattare inizialmente solo le quattro classi tutorial |
| Progressione e risorse | Ricche di possibilità, con rischi di ridondanza e sfruttamento | Simulare un percorso completo con contatori e bilancio delle cure |
| Mappa e incontri | Impostazione leggibile, quantità non ancora giustificate | Definire prima durata del percorso e costo dei contenuti |
| Ambito produttivo | Limiti utili, prototipo ancora molto carico | Separare prova del combattimento e prova della campagna |
| Accesso Anticipato | Obiettivo definito, valore autonomo ancora da provare | Verificare rigiocabilità e conclusione soddisfacente dell'atto uno |

## 2. Cosa funziona e va preservato

- **Il percorso può costruire l'orda.** Le famiglie nemiche possono essere sia minacce sia opportunità di progressione. È il collegamento più fertile fra mappa e combattimento.
- **Cinque combattenti favoriscono leggibilità e attaccamento.** Nome, classe e origine possono rendere riconoscibili gli individui, purché sostituirli non diventi sempre la scelta ottimale.
- **Manuale come riferimento e automazione opzionale sono una direzione comprensibile.** Va dimostrato che decidere a mano sia interessante e che delegare sia affidabile.
- **Le perdite hanno conseguenze.** L'assenza di resurrezione in battaglia sostiene la tensione; l'evento eccezionale non va trasformato in un recupero su cui basare il bilanciamento.
- **Il catalogo di classi è esplicitamente una riserva di idee.** È corretto non prometterne l'implementazione completa.
- **Placeholder, incontri progettati singolarmente e rinvio dei set sono scelte produttive utili.** Vanno mantenute anche quando emergerà la tentazione di aggiungere contenuti.

## 3. Come compilare questo documento

Rispondi sotto ogni scheda. Puoi scrivere «da verificare», indicando però quale prova servirà a scegliere. Le domande sono raggruppate per decisione, così una risposta può fissare una regola completa.

- **P0:** serve una risposta provvisoria prima di implementare il relativo sistema di base.
- **P1:** va risolta prima di produrre il primo atto completo.
- **P2:** può aspettare la validazione del nucleo, ma deve precedere il rilascio pubblico se la funzione è inclusa.

Distinguere sempre una **regola** («il cooldown diminuisce a inizio turno dell'unità») da un **parametro** («il cooldown vale 3»). Le regole richiedono coerenza; i parametri richiedono soprattutto prove. Non occorre completare tutte le schede prima di iniziare un prototipo esplorativo.

## 4. Decisioni P0 — Fondamenta del prototipo

### D01 — Qual è la decisione centrale del giocatore?

**Valutazione.** Preparazione, combattimento manuale e automazione possono contendersi il ruolo principale. «Strategia leggera» non chiarisce quanta attenzione richieda ogni incontro.

**Domande.** In una battaglia normale, quale decisione vuoi che sia la più interessante? Quale errore dovrebbe far perdere: squadra inadatta, ordine delle azioni, bersaglio sbagliato o cattiva gestione della campagna? Quanto dovrebbe durare uno scontro normale e quanto un boss? Quale motivazione dovrebbe portare a scegliere il manuale?

**Suggerimento.** Scrivere un esempio di battaglia in cui due azioni plausibili producono conseguenze diverse. Se l'abilità pronta è sempre migliore dell'attacco base, manca una scelta ricorrente.

**Risposta / decisione:**
> Da compilare.

### D02 — Qual è la struttura esatta del turno?

**Valutazione.** Il piano lascia aperte iniziativa e sequenza. Questa scelta condiziona cure, controllo, previsioni, contrattacchi e valore della velocità.

**Domande.** Agiscono prima tutti gli alleati, si alternano le unità o esiste una coda di iniziativa? Il giocatore sceglie liberamente l'ordine degli alleati? Ogni unità ha una sola azione? Attendere, difendersi, muoversi e passare sono possibili? Quando si controllano vittoria e sconfitta, inclusa la morte simultanea delle due squadre?

**Suggerimento.** Confrontare su carta un round per fazioni e uno con iniziativa individuale; scegliere una sola struttura provvisoria. Definire separatamente «round», «turno dell'unità» e «azione».

**Risposta / decisione:**
> Da compilare.

### D03 — Che forma ha il campo di battaglia?

**Valutazione.** «Prima linea», «adiacente», «vicino», «più lontano», «zona» e «allineato» non hanno ancora una geometria comune. La visuale laterale non la determina automaticamente.

**Domande.** Quanti slot esistono per linea e per fazione? Quali sono adiacenti? Le posizioni sono fisse durante lo scontro? Cosa accade ai posti vuoti quando un'unità muore? Una retroguardia senza prima linea diventa raggiungibile dalla mischia? Esistono movimento volontario, spinte e scambi; quanto costano? Quanti nemici possono essere presenti?

**Suggerimento.** Disegnare gli slot e tre situazioni: formazione completa, prima linea vuota, una sola unità superstite. Rinviare il movimento se non serve a validare i quattro ruoli iniziali.

**Risposta / decisione:**
> Da compilare.

### D04 — Come si risolvono bersagli, provocazione ed eccezioni?

**Valutazione.** «Distanza contro qualunque nemico» può rendere fragile la funzione protettiva della prima linea. Provocazione, furtività e protezioni richiedono una precedenza comune.

**Domande.** La provocazione obbliga anche gli attacchi a distanza, le aree e le abilità di supporto? Cosa accade se il provocatore è irraggiungibile? Come si risolvono due provocazioni? Le aree possono colpire unità non selezionabili direttamente? Cosa fa un combattente senza bersagli validi? Quanto può la prima linea proteggere concretamente chi sta dietro?

**Suggerimento.** Definire una sequenza unica: bersagli ammessi dall'abilità, restrizioni di posizione, effetti obbligatori, scelta finale. Provare un attacco a distanza, una provocazione e un attacco ad area sulla stessa formazione.

**Risposta / decisione:**
> Da compilare.

### D05 — Quando avanzano cooldown, stati e risorse?

**Valutazione.** «Dura un turno» e «cooldown 1» sono ambigui senza un momento preciso di aggiornamento. Il problema è strutturale, non soltanto numerico.

**Domande.** Le supreme iniziano pronte? Il cooldown diminuisce a inizio o fine turno di chi? Un'azione saltata per stordimento lo fa avanzare? Un'abilità senza bersaglio consuma l'azione o resta selezionabile? Quando scattano veleno, rigenerazione e scadenza degli scudi? Cooldown, energia e stati si azzerano fra scontri? Come si sommano effetti uguali e riduzioni di cooldown?

**Suggerimento.** Scrivere una cronologia di tre round con uso dell'abilità, controllo subito e riutilizzo. Imporre un limite alle riduzioni per evitare cicli infiniti.

**Risposta / decisione:**
> Da compilare.

### D06 — Quale informazione promette la previsione nemica?

**Valutazione.** Un bersaglio previsto è utile solo se il giocatore capisce quando può cambiare. Critici, schivate, bersagli casuali e reazioni possono impedire una cifra esatta.

**Domande.** L'intento nemico è impegnato a inizio round oppure ricalcolato dopo ogni azione? Una provocazione lo cambia immediatamente? La UI mostra danno certo, intervallo o stima condizionata? Come segnala casualità, effetti di stato e bersaglio morto? Il giocatore può annullare una scelta prima della conferma?

**Suggerimento.** Per il primo prototipo usare intenzioni semplici e deterministiche. Nell'automazione la previsione non viene calcolata, come stabilito dal piano: chiarire però che le regole e le scelte nemiche restano le stesse.

**Risposta / decisione:**
> Da compilare.

### D07 — Qual è il modello minimo di statistiche e danno?

**Valutazione.** Sei attributi promettono profondità, ma non hanno ancora funzioni distinte. Carisma e Saggezza rischiano di essere marginali; requisiti di equipaggiamento possono produrre ricompense inutilizzabili.

**Domande.** Che effetto misurabile ha ciascun attributo? Quali statistiche usa ognuna delle quattro classi? Esistono precisione, critici, schivata, resistenze ed elementi già nel prototipo? Come si calcolano danno, mitigazione e cura, con quali arrotondamenti e limiti? La difesa può annullare completamente il danno?

**Suggerimento.** Preparare una scheda con formula ed esempio numerico per ogni statistica effettivamente usata. Introdurre gli attributi che generano decisioni osservabili; eventuali semplificazioni rispetto ai sei previsti vanno approvate esplicitamente.

**Risposta / decisione:**
> Da compilare.

### D08 — Come evitare che curare diventi obbligatorio o sfruttabile?

**Valutazione.** Togliere la resurrezione al Chierico non dimostra che sia facoltativo. Cure ricaricabili, salute persistente e sovracura convertita in scudo possono incentivare a lasciare vivo un nemico debole per recuperare tutto gratuitamente.

**Domande.** È accettabile terminare uno scontro dopo molti round di cura? Gli scudi hanno limite e scadenza; persistono fra incontri? La sovracura di qualunque fonte genera scudo? Quali alternative permettono di completare l'atto senza Chierico? Come si evitano stalli fra squadre che non riescono a infliggersi danni sufficienti?

**Suggerimento.** Confrontare una squadra con cura e una senza; provare deliberatamente a sfruttare l'ultimo nemico. Scegliere un vincolo comprensibile su cure, scudi o durata degli scontri prima di compensare il problema aumentando i danni nemici.

**Risposta / decisione:**
> Da compilare.

### D09 — Che cosa significa delegare a una personalità?

**Valutazione.** Una personalità può rendere riconoscibile il goblin, ma anche sembrare una penalità arbitraria. Alcune passive del catalogo migliorano soltanto le priorità automatiche e rischiano di perdere valore in manuale.

**Domande.** La personalità è fissa, casuale, selezionabile o modificabile? Le sue priorità sono visibili? Quando sceglie attacco base invece di un'abilità pronta? L'automazione si imposta per squadra o individuo? Si può intervenire durante lo scontro e in quale momento sicuro? Ricompense e difficoltà sono identiche nelle due modalità?

**Suggerimento.** Iniziare con poche priorità dichiarate e verificabili. Ogni passiva deve avere un valore esplicito in entrambe le modalità, oppure essere chiaramente presentata come funzione di automazione.

**Risposta / decisione:**
> Da compilare.

### D10 — Chi è il signore della guerra sul campo?

**Valutazione.** Determina partenza e artefatto, ma non è stabilito se sia un combattente. La premessa parla di uno o due goblin iniziali: questo modifica radicalmente ritmo di reclutamento e sopravvivenza.

**Domande.** Il signore della guerra occupa uno dei cinque posti? Se muore, la campagna termina? Se è esterno alla squadra, quali poteri o presenza narrativa ha? Qual è la rosa iniziale esatta del primo prototipo? Quando si raggiungono quattro o cinque membri? Come si insegnano i quattro ruoli con solo uno o due goblin iniziali?

**Suggerimento.** Definire una partenza concreta e i primi tre incontri prima di progettare le tre partenze dell'Accesso Anticipato.

**Risposta / decisione:**
> Da compilare.

## 5. Decisioni P1 — Campagna, economia e contenuti

### D11 — Quali progressi sono della campagna e quali del profilo?

**Valutazione.** Le soglie 5/10/15/20 possono produrre reclutamento, livelli o tratti; non è ancora definito se i conteggi persistano. Da questa distinzione dipende l'intero ritmo della campagna.

**Domande.** Cosa identifica una tipologia: specie, classe, fazione o ruolo? Un nemico avanza più contatori? Le soglie sono cumulative o consumano progresso? Una ricompensa si sceglie o è fissa? Cosa si conserva dopo vittoria e sconfitta? Le evocazioni nemiche contano, permettendo accumulo illimitato?

**Suggerimento.** Compilare una tabella reale: famiglia nemica → progresso per incontro → soglia → ricompensa → persistenza → gestione dei duplicati. Simulare quanti nodi servono al primo sblocco e se le soglie alte siano raggiungibili in un atto.

**Risposta / decisione:**
> Da compilare.

### D12 — Come si trasforma una conoscenza in un nuovo goblin?

**Valutazione.** Sblocco di unità e creazione nei nodi rischiano di sovrapporsi. Una combinazione sbloccata vicino al boss potrebbe non diventare mai utilizzabile.

**Domande.** Le soglie danno direttamente un individuo o una possibilità di crearlo? Quanto costa la creazione? Si scelgono specie e classe liberamente? Attributi e tratti sono casuali e visibili prima di pagare? A quale livello arriva un nuovo membro? Quanto può passare fra sblocco e utilizzo? Cosa accade a una ricompensa con rosa piena?

**Suggerimento.** Garantire almeno una prova completa: conoscere un'opzione, accedere alla creazione, scegliere chi schierare e usarlo in più di una battaglia prima del boss.

**Risposta / decisione:**
> Da compilare.

### D13 — Le riserve sono un'alternativa o una risorsa da vendere?

**Valutazione.** Cinque riserve hanno senso se permettono rotazione e adattamento. La fuga dopo la sconfitta della squadra è già decisa: va resa evidente senza riaprire la regola.

**Domande.** Le riserve ottengono esperienza e cure? Si possono spostare oggetti fra individui? Perché conservare un goblin ferito invece di congedarlo? La caccia è possibile ovunque e anche immediatamente dopo aver creato un'unità? Può produrre più tesoro del costo di reclutamento? Chi può essere rianimato dall'evento e con quale livello/equipaggiamento?

**Suggerimento.** Verificare il ciclo reclutamento → caccia → tesoro → reclutamento per escludere guadagni infiniti. Mostrare la regola della fuga prima della prima battaglia rischiosa.

**Risposta / decisione:**
> Da compilare.

### D14 — Qual è il bilancio di salute e provviste?

**Valutazione.** Una cura automatica può semplificare la gestione, ma senza controllo può consumare risorse nei momenti meno desiderati. Alternare squadra e panchina può diventare contabilità.

**Domande.** Una provvista cura quanti HP e a chi? L'ordine privilegia salute percentuale, squadra o riserve? Si può disattivare la cura o scegliere una priorità? Ogni tratta consuma risorse anche se nessuno è ferito? Cosa accade a zero provviste? Riposo e razzia curano prima o dopo il consumo del viaggio? La rigenerazione di specie può rendere irrilevanti le provviste?

**Suggerimento.** Fare un bilancio per percorso: danni attesi, cure in battaglia, consumo, entrate, recupero ai riposi. Provare sia una marcia buona sia una partita con due errori consecutivi.

**Risposta / decisione:**
> Da compilare.

### D15 — La possessività degli oggetti genera scelte interessanti?

**Valutazione.** Accettare solo rarità superiori caratterizza i goblin, ma può punire un'assegnazione precoce: un oggetto comune utile alla build potrebbe essere bloccato da uno raro poco adatto. Il rifiuto del drop limita il danno, ma non risolve la perdita di possibilità future.

**Domande.** Come funzionano slot vuoti, inventario e oggetti rifiutati? L'oggetto sostituito viene distrutto o recuperato? Si può togliere un oggetto senza sostituirlo? Cosa succede alla morte del proprietario? Quanti gradini di rarità ci sono e con quale frequenza arrivano? Il giocatore conosce il vincolo prima della prima assegnazione? Cosa vende il mercante se molti slot non accettano più acquisti?

**Suggerimento.** Simulare una sequenza di dieci drop e due visite al mercante. Se la maggioranza non offre una decisione, rivedere distribuzione o regola prima di aggiungere set. Una maggiore rarità non garantisce automaticamente maggiore utilità.

**Risposta / decisione:**
> Da compilare.

### D16 — A cosa servono livelli, tratti e talenti separatamente?

**Valutazione.** Passiva di classe, passiva di specie, tratti, talenti e set rischiano di occupare lo stesso spazio. Gli sblocchi tramite uso abilità possono incentivare a prolungare combattimenti già vinti.

**Domande.** Quale decisione esclusiva introduce ogni categoria? Quanti modificatori può avere un individuo? I tratti sono alternative o bonus cumulativi? Si cambiano durante la campagna? L'esperienza premia tutti, solo i vivi o chi partecipa? Gli usi delle abilità contano anche dopo un certo numero di round o in una sconfitta? Come evitare di ripetere azioni inutili per sbloccare contenuti?

**Suggerimento.** Scrivere una scheda completa di goblin a inizio e fine atto. Se risulta difficile spiegarne la forza, rinviare una categoria di modificatori. Gli obiettivi di sblocco dovrebbero premiare il gioco desiderato, non la ripetizione vuota.

**Risposta / decisione:**
> Da compilare.

### D17 — Quanto è lunga una rotta e quali informazioni la rendono strategica?

**Valutazione.** Due mercanti, cinque élite e cinque riposi sono minimi sull'intera mappa, non su ogni percorso: il piano lo chiarisce già. Manca però il numero di tappe effettivamente visitate e il rapporto fra costo dei contenuti e durata vissuta.

**Domande.** Quanti nodi e combattimenti affronta una singola rotta? Quanto dura l'atto, gestione inclusa? Quanti bivi cambiano davvero una scelta? Quali famiglie nemiche sono riconoscibili prima di scegliere, così da perseguire uno sblocco? I riposi sono abbastanza accessibili da rendere praticabili più rotte? «Nessuna ripetizione» vieta la stessa composizione, la stessa regola o anche la stessa famiglia nemica?

**Suggerimento.** Disegnare due percorsi completi con salute, ricompense e progressi segnati nodo per nodo. Stimare i contenuti sull'intero grafo e il ritmo sulla singola rotta; non confondere le due quantità.

**Risposta / decisione:**
> Da compilare.

### D18 — Come rimane interessante una mappa progettata a mano?

**Valutazione.** Evitare incontri casuali ingestibili è sensato. Tuttavia, nascondere contenuti fissi funziona soprattutto la prima volta: nelle campagne successive il giocatore può memorizzarli.

**Domande.** Tra campagne cambiano assegnazione degli incontri, ricompense, eventi, rotte disponibili o soltanto la squadra iniziale? Gli indizi consentono decisioni prima di conoscere la mappa? Come si evita un percorso sempre migliore? Quante campagne diverse deve sostenere l'atto uno da solo?

**Suggerimento.** Testare una seconda e una terza partita sulla stessa mappa. Cercare nuove decisioni prodotte da squadra e progressione prima di ricorrere a generazione procedurale complessa.

**Risposta / decisione:**
> Da compilare.

### D19 — Qual è la grammatica dei nemici e del primo boss?

**Valutazione.** Il catalogo riguarda soprattutto gli alleati. Mancano esempi concreti della resistenza che deve rendere interessanti i loro strumenti.

**Domande.** Quali ruoli nemici insegnano focus, protezione, cure e attacco alle retrovie? I nemici usano gli stessi kit e limiti dei goblin? Quali azioni pericolose sono anticipate? Qual è la meccanica del primo boss e quali due risposte diverse la contrastano? Come funzionano controllo e rendimenti decrescenti sui boss? Una squadra priva di una classe specifica può comunque vincere?

**Suggerimento.** Preparare tre schede di incontro: obiettivo didattico, composizione, intenzioni, risposta attesa, risposta alternativa, ricompensa. Il boss dovrebbe verificare regole già insegnate, aggiungendo una variazione leggibile.

**Risposta / decisione:**
> Da compilare.

### D20 — Che cosa rende personale l'orda e coerente il tono?

**Valutazione.** Nomi e statistiche da soli potrebbero non sostenere l'attaccamento promesso. «Caccia» con perdita definitiva può sembrare un incarico temporaneo; assimilazione astratta e linea materna richiedono una terminologia coerente. Lasciare i fatti fuori campo ne limita la rappresentazione, ma non elimina il loro significato narrativo.

**Domande.** Quali momenti fanno ricordare un goblin: nomi, personalità, eventi, imprese o commemorazione? Perché non torna dalla caccia? Che cosa racconta esattamente la creazione di un nuovo individuo e come si giustificano i tempi nella marcia? Come si distinguono specie goblin, origine materna e classe in una schermata? Quale reazione emotiva cerchi verso conquista e cattura? Come evitare che l'umorismo banalizzi le conseguenze tragiche?

**Suggerimento.** Scrivere tre brevi esempi prima dei sistemi narrativi: reclutamento, perdita, evento comico. Farli leggere senza spiegazioni per verificare che comunichino lo stesso gioco.

**Risposta / decisione:**
> Da compilare.

## 6. Revisione specifica di CLASSI_E_ABILITA.md

Le 28 classi offrono molti temi, ma diversi effetti conservano il linguaggio di un combattimento continuo o di priorità automatiche. Non è necessario rifare tutto il catalogo ora: serve marcare chiaramente cosa è pronto per il prototipo e cosa resta un concetto.

| Punto del catalogo | Dubbio concreto | Chiarimento necessario |
|---|---|---|
| Bardo, Druido, Inquisitore | «Velocità d'attacco» senza una struttura temporale definita | Iniziativa, azioni aggiuntive o altro effetto? |
| Monaco, Samurai, Inquisitore | Interruzioni, attesa breve, abilità «in corso» | Esistono preparazione e reazioni fra azioni, oppure l'interruzione cancella un intento futuro? |
| Cavaliere, Cacciatore, Brawler | Slancio, percorsi, trappole e spinte | Quali movimenti esistono davvero nella geometria a slot? |
| Chierico, Guerriero, Ranger e altri | Bersagli specifici nel testo, scelta libera nelle regole comuni | Sono vincoli dell'abilità o soltanto priorità dell'automazione? |
| Ranger — Occhio del cacciatore | Aumenta una priorità che in manuale decide il giocatore | Offre un beneficio meccanico, informativo o solo automatico? |
| Ranger — Preda costante | «Alleato marcato» mentre Tiro segnato marca un bersaglio nemico | Correggere il referente prima di implementare il tratto |
| Stregone — Riserva vitale | Parla di consumo di salute/difesa; la suprema descrive perdita temporanea di difesa | Decidere se esiste un costo in salute oppure una sola penalità difensiva |
| Stregone — Fiammata erratica | Bersaglio casuale e controllo manuale convivono senza eccezione esplicita | Quando si estrae il bersaglio e cosa conosce il giocatore prima di confermare? |
| Oracolo — Filo del fato | «Predice» un attacco già previsto dalla UI generale | Quale informazione o protezione aggiuntiva lo rende distintivo? |
| Convocatore, Fattucchiere, Cacciatore, Sciamano | Servitori, famigli, animali e totem | Occupano slot, hanno salute, un turno, un limite e possono essere bersagliati? |
| Pistolero | Attacco base sempre disponibile, ma caricatore da ricaricare | La ricarica consuma un'azione? Che cosa può fare senza munizioni? |
| Barbaro | Carica che decade lentamente fuori battaglia | Decade per nodo, tratta o altra unità di tempo? |

### D21 — Quale scelta distingue ciascuna delle quattro classi iniziali? [P0]

**Domande.** Quando il Guerriero rinuncia a provocare? Quando il Ranger marca invece di eliminare subito? Quando lo Stregone accumula energia invece di usare la suprema? Quando il Chierico attacca invece di curare? Con cinque posti e quattro classi sono ammessi duplicati; quale compromesso genera il quinto membro?

**Suggerimento.** Scrivere per ogni classe una situazione favorevole, una debolezza e due azioni entrambe ragionevoli. Il confronto deve avvenire contro nemici reali del prototipo, non soltanto fra descrizioni.

**Risposta / decisione:**
> Da compilare.

### D22 — Come scegliere le prossime classi senza moltiplicare i sistemi? [P1]

**Valutazione.** Mago/Stregone/Arcanista, Ranger/Cacciatore e Bardo/Scaldo hanno temi vicini; la distinzione va dimostrata attraverso decisioni diverse. Evocazioni, trasformazioni e cavalcature richiedono anche interfaccia e asset specifici.

**Domande.** Quale nuova decisione introduce ogni classe candidata? Quali regole già esistenti riusa? Qual è il suo costo aggiuntivo in animazioni, UI e casi limite? Quali classi possono restare esclusivamente concetti fino alla validazione dell'atto uno?

**Suggerimento.** Scegliere l'espansione per valore tattico e costo produttivo. Le categorie «base», «avanzata», «alternativa» e «ibrida» devono indicare accessibilità o complessità, senza implicare automaticamente maggiore potenza.

**Risposta / decisione:**
> Da compilare.

### Scheda minima di abilità da completare per il prototipo

```text
Classe / abilità:
Decisione tattica che deve creare:
Tipo di azione e costo:
Bersagli validi / portata / area:
Scelta manuale / priorità automatica / eventuale casualità:
Effetto e formula provvisoria:
Disponibilità iniziale / cooldown / momento di riduzione:
Durata / accumulo / limiti:
Interazioni con provocazione, scudi e morte del bersaglio:
Segnale mostrato nell'interfaccia:
Caso in cui è preferibile non usarla:
```

## 7. Decisioni P2 — Esperienza pubblica e sostenibilità

### D23 — Qual è il prodotto autonomo dell'atto uno?

**Valutazione.** Un atto completo può sostenere un Accesso Anticipato, ma il suo valore non deriva automaticamente dall'esistenza di una roadmap. Non serve fissare ora il prezzo; serve sapere quale esperienza si intende offrire.

**Domande.** Dopo il boss dell'atto uno si vede una vittoria provvisoria, un epilogo o una campagna sospesa? Cosa succede agli individui sopravvissuti? Si può iniziare subito un altro tentativo? Quale motivo concreto sostiene la terza campagna? Il primo atto sarebbe soddisfacente anche con una lunga attesa degli atti successivi?

**Risposta / decisione:**
> Da compilare.

### D24 — Come si gestiscono apprendimento, perdita e ripresa?

**Valutazione.** Danni persistenti, rarità vincolante e fuga delle riserve possono sembrare punizioni impreviste se apprese solo dopo una perdita. Salvare fra nodi non chiarisce cosa succede chiudendo durante una battaglia lunga.

**Domande.** Quali regole devono essere insegnate prima della prima sconfitta? Esiste un riepilogo che spiega perché si è perso? Chiudere in battaglia riprende, ricomincia l'incontro o perde i progressi successivi all'ultimo nodo? Quali comandi sono rimappabili? Il gioco è usabile da tastiera e senza distinguere i colori? Sono disponibili velocità delle animazioni, riduzione degli effetti e ispezione senza limiti di tempo?

**Suggerimento.** Provare il tutorial senza interventi dell'autore. Per una decisione irreversibile, testo e conferma devono esporre la conseguenza concreta, evitando avvisi generici ripetuti.

**Risposta / decisione:**
> Da compilare.

### D25 — Qual è il budget reale di produzione?

**Valutazione.** Anche con asset gratuiti restano costi di integrazione, testi bilingui, animazioni, audio, bilanciamento e verifica. Un primo atto con molti sistemi può superare i mezzi prima di arrivare al rilascio.

**Domande.** Quante persone e ore settimanali sono disponibili? Quali competenze sono già presenti? Qual è il tempo massimo da investire prima di rivalutare il progetto? Quanti nemici, incontri, eventi, oggetti e specie sono sostenibili? Quali tre funzionalità si tagliano per prime se il prototipo richiede il doppio del previsto?

**Suggerimento.** Misurare quanto costa produrre e verificare un singolo incontro rappresentativo, poi stimare il primo atto includendo revisioni e localizzazione. Non derivare il budget dal numero di idee nel catalogo.

**Risposta / decisione:**
> Da compilare.

## 8. Proposta di validazione in ordine di rischio

Questa sequenza restringe temporaneamente il prototipo descritto nel piano. È una raccomandazione da approvare, non una sostituzione già decisa della roadmap.

| Passaggio | Contenuto minimo | Domanda verificata | Condizione per proseguire |
|---|---|---|---|
| A — Regole su carta | Slot, ordine di turno, quattro kit, tre incontri | Esistono scelte comprensibili e casi limite risolvibili? | Un round completo è descrivibile senza inventare regole durante l'esecuzione |
| B — Combattimento isolato | Placeholder, manuale, previsione, stati; poi automazione sullo stesso scontro | È interessante scegliere e affidabile delegare? | I tester spiegano almeno una scelta e la causa di un esito sfavorevole |
| C — Catena breve | Salute persistente, provviste, riposo e oggetti | Le vittorie lasciano conseguenze senza incentivare attese e cure infinite? | Esistono più modi praticabili di gestire il logoramento |
| D — Mini-campagna | Due rotte, una famiglia di progressione, creazione, riserva e boss | Il percorso cambia concretamente l'orda? | Le due rotte producono scelte di squadra differenti prima del boss |
| E — Seconda campagna | Uno sblocco persistente e partenza alternativa | Si vuole ricominciare per provare qualcosa? | Il nuovo tentativo cambia decisioni senza richiedere ripetizione obbligatoria |

Per la prova B si possono schierare quattro unità fisse, rinviando la piena gestione della panchina alla prova D; il limite finale di cinque resta quello del progetto. Set, 28 kit, eccezioni agli slot e varianti artistiche complete non servono a rispondere alle prime domande.

### D26 — Quali risultati ci faranno cambiare idea? [P0]

**Domande.** Quanti tester esterni coinvolgiamo e con quale familiarità con il genere? Quali durate desideriamo per combattimento e atto? Quale osservazione ci porterà a semplificare una regola, togliere un sistema o ripetere una prova? Chi decide quando una prova è superata?

**Risposta / criteri concordati:**
> Da compilare.

Misurare almeno durata e round degli scontri, azioni scelte, uso dell'automazione, danni e cure nette, perdite, momento del primo reclutamento, drop rifiutati e scelte di percorso. Registrare anche il motivo dichiarato dal giocatore: due squadre uguali possono derivare da preferenza o da un sistema che non offre alternative reali. Pochi test esplorativi individuano problemi; non dimostrano da soli un bilanciamento generale.

## 9. Decisioni da fissare per prime

Per iniziare senza trasformare la pre-produzione in un lavoro infinito, affrontare in quest'ordine:

1. D01–D03: esperienza centrale, turno e campo di battaglia.
2. D04–D08: bersagli, tempi, previsione, statistiche e sostenibilità delle cure.
3. D10 e D21: partenza concreta e quattro kit effettivamente giocabili.
4. D09: automazione applicata alle stesse regole già definite.
5. D11–D17: un ciclo completo di progressione, recupero e scelta del percorso.
6. D26: criteri osservabili per decidere se espandere il prototipo.

Le risposte possono essere provvisorie. Devono però essere abbastanza precise da evitare che implementazione, UI e contenuti assumano tre versioni diverse della stessa regola.

### Registro delle decisioni approvate

Compilare quando una risposta diventa una regola condivisa; trasferirla poi nel documento di progetto o nel catalogo di classi pertinente.

| ID | Decisione approvata | Provvisoria / definitiva | Prova richiesta | Documento da aggiornare |
|---|---|---|---|---|
| Da compilare | | | | |

### Parcheggio delle idee

Usare questo spazio per conservare proposte interessanti senza renderle immediatamente requisiti del prototipo.

| Idea | Beneficio atteso | Costo o regole aggiuntive | Quando rivalutarla |
|---|---|---|---|
| Da compilare | | | |

Il criterio guida della prossima fase è dimostrare che **scegliere chi affrontare cambia chi possiamo schierare, e che questa nuova squadra apre decisioni tattiche interessanti**. Se quel collegamento funziona con pochi contenuti, l'espansione avrà una base verificabile.
