# Goblin Warlord — Valutazione di game design

> Revisione critica del concept e del piano di progetto. È una valutazione di pre-produzione: i giudizi sono ipotesi da verificare con un prototipo, non risultati di playtest.

## Sintesi per il team

**Il concept ha un'identità riconoscibile e un buon nucleo di rigiocabilità potenziale:** conquistare una nazione scegliendo il percorso e incorporando specie e classi sconfitte nella propria armata. La combinazione fra mappa a nodi in stile *Slay the Spire* e combattimento autobattler può funzionare, ma il progetto deve dimostrare una cosa prima di investire in contenuti: che il giocatore sente di prendere decisioni tattiche rilevanti anche quando le unità combattono da sole.

Il rischio principale non è la mancanza di sistemi; è che i sistemi restino giustapposti. La mappa deve cambiare la campagna, le vittorie devono modificare la squadra in modo interessante, e la squadra deve richiedere scelte tattiche prima e durante gli scontri. Se la scelta si riduce a guardare una battaglia già decisa dalla composizione, la promessa di strategia si indebolisce rapidamente.

### Giudizio preliminare

| Area | Valutazione | Osservazione |
|---|---|---|
| Identità del concept | Promettente | Conquista e assimilazione danno una fantasia di potere chiara, distinta dal roguelite fantasy generico. |
| Potenziale di giocabilità | Interessante, da provare | La preparazione della squadra è adatta all'autobattler; manca ancora una definizione concreta di quanto il giocatore possa intervenire. |
| Rigiocabilità | Alta in potenza, non ancora dimostrata | Percorsi e roster variabile aiutano solo se cambiano le decisioni, non soltanto gli incontri o i numeri. |
| Fattibilità dell'MVP | Buona con una riduzione mirata | Una regione e pochi contenuti sono sufficienti; le combinazioni di specie/job possono moltiplicare il costo di bilanciamento. |
| Potenziale commerciale | Più chiaro come premium PC | Il pubblico di nicchia può apprezzare un prodotto focalizzato; monetizzazione ricorrente non è adatta al single-player descritto. |

## 1. Giocabilità e qualità delle decisioni

### Cosa funziona già nel concept

- **Una fantasia d'azione leggibile:** si parte con poco, si vince, si incorporano nuove forze e si punta a conquistare una nazione.
- **Una decisione ricorrente forte:** scegliere il prossimo nodo significa scegliere nemici, rischi e ricompense.
- **Un ponte naturale fra mappa e combattimento:** la composizione dell'armata può rispondere alle minacce previste nel percorso.
- **Una presentazione 2D laterale compatibile con l'autobattler:** le battaglie possono essere spettacolari e leggibili senza richiedere controlli d'azione.
- **Conflitto tematico coerente:** conquista, paura, assimilazione e resistenza possono influenzare sia l'atmosfera sia le regole.

### Il problema centrale dell'autobattler

Il giocatore deve capire quali decisioni sono sue. Se sceglie la squadra prima dell'incontro e poi non può influire in modo significativo, l'esito rischia di sembrare una verifica numerica: "ho portato il counter giusto?".

Per l'MVP suggerisco di mantenere il combattimento automatico, ma provare **un solo livello d'intervento**, non una combinazione di controlli manuali:

1. **Prima dello scontro:** composizione, formazione e una scelta di comportamento/bersaglio.
2. **Durante lo scontro:** osservazione, pausa e velocità regolabile; eventualmente una sola abilità del warlord con uso limitato.
3. **Dopo lo scontro:** una ricompensa che modifica la squadra o il piano della campagna.

La prova è che preparazione, lettura dell'incontro e ricompensa formino un'unica decisione. Evitare inizialmente ordini per ogni unità, microgestione in tempo reale e alberi di comportamento configurabili: rischierebbero di trasformare il sistema in un RTS ridotto senza risolvere la chiarezza.

### Domande di design prioritarie sul combattimento

- La squadra di tre unità è una scelta di scope o una regola definitiva? Tre può essere leggibile, ma potrebbe offrire poche combinazioni per sostenere un autobattler. Testare tre contro quattro o cinque unità prima di fissare la dimensione.
- Il giocatore sceglie un **roster di riserva** e poi schiera una squadra, oppure ogni unità disponibile combatte? Un roster più ampio con schieramento limitato crea decisioni; tutto il roster in campo riduce la scelta.
- Quanto dura uno scontro? Se dura troppo e l'intervento è minimo, la ripetizione diventa passiva. Il prototipo dovrebbe sperimentare scontri brevi e una velocità 2x.
- Quali informazioni sono visibili prima di scegliere il nodo? Rivelare tutto elimina la sorpresa; rivelare troppo poco rende la pianificazione arbitraria.
- La sconfitta è causata da errori correggibili (formazione, composizione, target) o da statistiche e casualità non leggibili?

### Unità: separare specie e job senza moltiplicare il lavoro

La distinzione fra specie e job è forte, ma ogni combinazione potenzialmente richiede statistiche, animazioni, abilità, effetti e bilanciamento. Il numero di combinazioni può crescere più rapidamente dei contenuti percepiti dal giocatore.

**Raccomandazione per il prototipo:** definire i job come principali portatori del ruolo tattico; la specie modifica solo una o due caratteristiche distintive. Con tre job e due specie test si ottengono già sei combinazioni, sufficienti per verificare il sistema. Evitare inizialmente abilità uniche per ogni coppia specie-job.

Decidere anche cosa significa concretamente “assimilare”:

- reclutare unità specifiche nel roster;
- sbloccare una specie come origine per future unità;
- imparare un job o una tecnica senza aggiungere persone;
- ottenere una combinazione di queste opzioni.

Queste ricompense non sono equivalenti. Il prototipo dovrebbe sceglierne una come forma primaria e usare al massimo una seconda forma occasionale. Una ricompensa troppo ampia può gonfiare il roster; una ricompensa solo cosmetica non soddisfa la fantasia di crescita dell'armata.

### Rischio di palla di neve

Vincere fornisce unità e vantaggi; con più forza si vince più facilmente, quindi la campagna può diventare decisa dopo i primi incontri. Servono costi o vincoli comprensibili: capienza della squadra, provviste, ferite, unità situazionali, attrito o reazioni nemiche. Non aggiungere tutte queste risorse insieme: selezionare un solo meccanismo d'attrito per il test iniziale.

La scelta di assimilazione dovrebbe essere interessante anche quando il giocatore ha già una squadra forte. Per esempio, un nuovo alleato potrebbe aprire una sinergia o un approccio diverso, invece di essere sempre un miglioramento diretto alle statistiche.

## 2. Rigiocabilità

### Fonti di varietà che possono funzionare

1. **Percorso:** cambia i tipi di nodo e le opportunità disponibili.
2. **Composizione dell'armata:** le unità accessibili e le sinergie differiscono da una campagna all'altra.
3. **Approccio alla conquista:** forza, terrore/razzia e accordi alterano costi, ricompense e resistenze.
4. **Eventi e boss:** creano contesto e sfide che mettono alla prova squadre diverse.
5. **Obiettivi:** condizioni di vittoria o priorità diverse possono dare una ragione per deviare dal percorso più efficiente.

Un percorso non è davvero diverso solo perché mostra nodi in ordine diverso. Deve chiedere compromessi diversi: per esempio, una strada con un boss militare più forte ma una ricompensa di reclutamento esclusiva contro una strada più sicura con risorse limitate.

### Progressione fra campagne

La progressione persistente può motivare a riprovare, ma può anche ridurre le campagne successive a un'attesa di potenziamenti. Per il primo prototipo consiglierei:

- conservare preferenze, statistiche o contenuti sbloccati, se utile;
- non rendere la vittoria dipendente da bonus permanenti di potenza;
- premiare la conoscenza e le opzioni, non rendere obsolete le sfide iniziali;
- verificare che una campagna nuova sia interessante anche senza grind.

Non è ancora necessario decidere se il gioco sarà un roguelite con meta-progressione, un roguelike più autonomo o una campagna a capitoli. Prima serve verificare se una singola campagna breve è divertente e se il giocatore vuole ripeterla.

### Test di rigiocabilità

Realizzare almeno tre configurazioni di campagna con:

- una mappa o ordine di nodi diverso;
- almeno una ricompensa/specie/job differente;
- un boss o una combinazione di minacce diversa;
- due approcci alla conquista con conseguenze verificabili.

Chiedere ai tester non soltanto se vogliono giocare ancora, ma **che cosa farebbero diversamente nella run successiva e perché**. Se non sanno nominare una scelta diversa, la varietà è probabilmente superficiale.

## 3. Level design: mappa di campagna e arene

Il gioco ha due scale di level design che vanno progettate insieme ma prototipate separatamente.

### Mappa della campagna

Per l'MVP, la soluzione più economica è una **mappa costruita a mano con varianti controllate**, non generazione procedurale libera. Si possono variare ricompense, incontri o alcuni collegamenti mantenendo il controllo sul ritmo e sul bilanciamento.

Una struttura didattica per una mini-campagna:

1. **Apertura:** un incontro semplice insegna la formazione e dà una prima ricompensa di unità.
2. **Primo bivio:** un nodo di combattimento più rischioso contro un evento/rifornimento.
3. **Prima conquista:** villaggio o avamposto introduce la scelta fra razziare, reclutare o risparmiare.
4. **Preparazione al boss:** un percorso di recupero più sicuro contrapposto a un incontro duro con ricompensa migliore.
5. **Boss di regione:** verifica composizione, comprensione dei ruoli e uso delle ricompense.
6. **Esito:** la conquista o sconfitta mostra una conseguenza chiara e permette di riavviare.

Ogni nodo dovrebbe rispondere a tre domande: **che cosa rischio, che cosa posso guadagnare e che cosa cambia dopo?** Se due nodi danno lo stesso tipo di battaglia e ricompensa, uno dei due probabilmente non aggiunge valore.

### Arene 2D laterali

La scena laterale deve avere funzione di gioco, non essere solo uno sfondo per icone che combattono. Per il prototipo basta un'arena con terreno e formazioni leggibili; poi si può introdurre una sola variabile ambientale che interagisca con la squadra.

Possibili variabili da testare in seguito:

- copertura o elevazione che favorisce la retroguardia;
- terreno che rallenta una classe o una specie;
- ostacoli distruttibili o punti di strozzatura;
- obiettivi di battaglia alternativi all'eliminazione totale.

Ogni elemento ambientale deve produrre una scelta comprensibile nella composizione o formazione. Evitare piattaforme e salti se le unità si muovono autonomamente: aggiungerebbero costo di animazione e pathfinding senza necessariamente aumentare la profondità.

### Villaggi, città e boss come livelli

Non basta aumentare salute e numero di nemici per far sembrare una città diversa da una pattuglia. Ogni scala d'incontro deve introdurre una regola:

- **Pattuglia:** incontro breve, utile a presentare una minaccia o un job.
- **Villaggio:** difensori e una decisione di conquista con conseguenze sociali o di reclutamento.
- **Città/fortezza:** più fasi, difese o un obiettivo specifico, con preparazione della squadra prima dell'ingresso.
- **Boss:** una meccanica leggibile che cambia priorità e mette alla prova una sinergia.

Queste sono direzioni di design, non requisiti da implementare tutte subito: per la vertical slice è sufficiente una versione ridotta ma riconoscibile di ciascun incontro chiave.

## 4. Monetizzazione e posizionamento

### Raccomandazione

Per un gioco single-player PC di questo tipo, la direzione più coerente è **premium a prezzo unico**. Il giocatore compra il gioco completo; la progressione non è legata a pagamenti, energia, timer o acquisti casuali.

È una raccomandazione di modello, non una previsione di vendite. Prezzo e piattaforme vanno decisi dopo aver definito durata, qualità, volume di contenuti e confronto con il mercato al momento del lancio.

### Opzioni da valutare

- **Demo gratuita:** utile per far provare il loop di autobattaglia e la promessa dell'assimilazione; dovrebbe includere una mini-campagna rappresentativa, non soltanto una battaglia isolata.
- **Accesso anticipato:** possibile solo se il team è pronto a pubblicare una versione già divertente e ricevere feedback frequenti. Non sostituisce un MVP funzionante e una roadmap onesta.
- **DLC o espansioni:** in futuro possono aggiungere campagne, fazioni, regioni, boss o contenuti narrativi sostanziali. Da considerare solo dopo aver verificato il gioco base.
- **Cosmetici:** non prioritari per un progetto piccolo; richiedono comunque produzione e interfaccia e non devono diventare un sostituto di nuovi contenuti.

### Da evitare per il concept attuale

- free-to-play con valute premium, energia o timer;
- vendita di unità, specie o job che influenzano la forza dell'armata;
- loot box per reclute o equipaggiamento;
- pass stagionali o eventi a tempo che presuppongono aggiornamenti continui;
- multiplayer inserito per sostenere una monetizzazione ricorrente.

Questi sistemi entrerebbero in conflitto con la promessa di una campagna strategica single-player e aumenterebbero costi operativi, bilanciamento e aspettative di contenuti.

## 5. Rischi di design e contromisure

| Rischio | Perché conta | Come verificarlo |
|---|---|---|
| Autobattaglie passive | Il giocatore può percepire che la vittoria era già decisa | Dopo un incontro chiedere quale decisione del giocatore ha cambiato l'esito; variare preparazione e interventi in un test controllato |
| Assimilazione poco chiara | Non è evidente se si recluta, si copia una tecnica o si sblocca una specie | Prototipare un solo tipo di ricompensa e verificare che i tester ne sappiano spiegare l'effetto |
| Palla di neve | Le prime vittorie rendono il resto della campagna automatico | Confrontare le percentuali di vittoria e il tempo di completamento nodo per nodo |
| Troppe combinazioni | Specie × job × equipaggiamento aumenta test e bilanciamento | Limitare le combinazioni MVP; aggiungerne una soltanto se introduce una decisione distinta |
| Scelte di percorso cosmetiche | La mappa sembra una schermata di selezione anziché una decisione | Confrontare campagne con itinerari diversi e controllare che cambino davvero composizione, rischio o strategia |
| Risorse ridondanti | Le risorse diventano contabilità senza scelte | Ogni risorsa deve avere almeno due usi significativi; rimuovere quelle senza trade-off |
| Tema di conquista senza conseguenze | La fantasia dark resta solo estetica | Far reagire almeno una fazione o un nodo a una scelta precedente |
| Scope visivo eccessivo | Ogni specie/job e città richiede asset aggiuntivi | Usare un linguaggio visivo modulare e misurare il costo per una nuova unità completa |

## 6. Dubbi di design da risolvere

Queste domande non richiedono tutte una risposta prima del prototipo. Le prime cinque invece cambiano direttamente le regole fondamentali e vanno definite in forma provvisoria.

### Priorità 1 — Decisioni fondamentali

1. **Che cosa si assimila?** Persone reclutate, intere unità, specie, job, tecniche o una scelta fra questi?
2. **Come si costruisce la squadra?** Qual è la dimensione del roster e quante unità si schierano in battaglia?
3. **Che controllo ha il giocatore durante l'autobattaglia?** Solo pausa/velocità, un'abilità attiva, ordini iniziali o interventi limitati?
4. **Qual è la condizione di vittoria della campagna?** Conquistare una capitale, sconfiggere un sovrano, controllare una quota di territori o completare una sequenza di boss?
5. **Qual è il costo della sconfitta?** Fine run, perdita di una risorsa, ferite permanenti o una via di recupero?

### Priorità 2 — Struttura e progressione

6. Una campagna è una nazione intera in una run oppure una singola regione che fa parte di una campagna più lunga?
7. L'itinerario è interamente autoconclusivo o ci sono nodi di ritorno, assedi e regioni persistenti?
8. Quanto è casuale la mappa? Quali informazioni il giocatore vede prima di scegliere il percorso?
9. Gli sblocchi fra campagne aggiungono opzioni o potenza diretta?
10. Quanto spesso il giocatore può cambiare roster e formazione?
11. Che funzione hanno provviste, tesoro e influenza? È possibile ridurre il numero di risorse?
12. Le unità sono individui con identità/ferite o elementi fungibili di una riserva?

### Priorità 3 — Identità, tono e pubblico

13. "Assimilare" significa integrazione nell'orda, reclutamento forzato, sottomissione o appropriazione culturale? Il gioco può offrire più letture, ma deve comunicare cosa avviene in termini di storia e regole.
14. Le razzie sono una scelta strategica praticabile o la principale attività del giocatore? Quali costi concreti hanno?
15. Qual è il livello di rappresentazione della violenza e quali temi maturi si vogliono mostrare o lasciare fuori campo?
16. Il giocatore deve sentirsi un conquistatore spietato, un capo pragmatico o qualcuno che può scegliere una linea politica? Il gioco non deve imporre tutte le interpretazioni, ma deve sapere quale fantasia mette in primo piano.
17. Il tono è tragico, satirico o alterna i due? Un riferimento tonale coerente aiuta scrittura, arte e marketing.

### Priorità 4 — Produzione e commercializzazione

18. Qual è il budget/tempo realistico per creare arte, animazioni, audio e testi per ogni specie e job?
19. La prima release è una campagna completa breve oppure una versione in accesso anticipato da ampliare?
20. Quali lingue e funzionalità di accessibilità sono previste per la prima release?
21. La futura eventualità multiplayer è soltanto una possibilità di prodotto o influenza davvero il design? Per ora è più sano trattarla come possibilità remota, senza spendere complessità per supportarla.

## 7. Piano di validazione consigliato

### Prototipo A — “È divertente guardare e preparare una battaglia?”

- Una singola arena, tre job, una specie alternativa e un roster più ampio della squadra schierata.
- Mostrare formazione e comportamento prima dell'avvio.
- Permettere pausa e velocità aumentata; testare una sola abilità attiva opzionale.
- Usare incontri con almeno due composizioni nemiche leggibili.

**Domande di test:** il giocatore sa spiegare perché ha vinto o perso? Cambierebbe la squadra dopo aver visto il risultato? Preferisce intervenire o pianificare prima?

### Prototipo B — “Le scelte di mappa cambiano la run?”

- Una mini-campagna di 6–8 nodi, con due rami e un boss.
- Un nodo villaggio con due approcci e una ricompensa di assimilazione.
- Due configurazioni di ricompensa/percorso, anche predefinite.

**Domande di test:** perché il tester ha scelto quel ramo? La scelta ha cambiato la composizione o solo le risorse? Vuole provare il ramo alternativo?

### Prototipo C — “Il ciclo completo regge?”

- Una campagna breve dal reclutamento iniziale all'obiettivo finale.
- Almeno una scelta che produce una conseguenza visibile più avanti.
- Una sconfitta recuperabile o una condizione di fine run chiaramente comunicata.
- Una seconda partita con una ricompensa o un itinerario alternativo.

**Domande di test:** il tester ricomincia spontaneamente? Quale strategia vuole provare? In quale momento ha perso interesse o ha accelerato per finire?

### Metriche di prototipo

Raccogliere dati semplici, senza confondere “misurabile” con “utile”:

- completamento di una campagna e numero di nodi visitati;
- composizioni scelte e cambiamenti di formazione;
- vittorie/sconfitte per incontro e composizione;
- durata degli scontri e percentuale di tempo accelerato;
- scelte di percorso e motivazione dichiarata;
- percentuale di tester che desidera avviare una seconda campagna e quale variazione vuole provare.

Le soglie numeriche vanno concordate dopo aver scelto il pubblico del test e la durata prevista della campagna; fissarle prima di avere un prototipo rischierebbe di produrre obiettivi arbitrari.

## 8. Raccomandazioni operative finali

1. Definire in una pagina le regole provvisorie di composizione, assimilazione, intervento in battaglia e vittoria della campagna.
2. Prototipare prima **un autobattler con decisioni**, non la mappa completa né la lore.
3. Testare rapidamente le dimensioni della squadra: tre unità può essere un buon MVP, ma va confrontato con una squadra leggermente più ampia.
4. Costruire poi una mappa corta, prevalentemente authored, con due scelte di percorso che producano conseguenze reali.
5. Rinviare progressione meta, ulteriori specie, risorse aggiuntive, monetizzazione definitiva e ogni sviluppo multiplayer fino alla verifica del ciclo base.
6. Usare playtest per cambiare regole; non assumere che più unità, più nodi o più contenuti risolvano una mancanza di profondità.

### Conclusione

**Goblin Warlord merita un prototipo.** La sua idea più forte è che ogni vittoria cambi ciò che l'orda può diventare, mentre il giocatore decide quale strada di conquista seguire. La sua idea più fragile è l'autobattler: deve garantire preparazione leggibile, contromisure e agency senza trasformarsi in microgestione. Se il primo test dimostra che composizione, mappa e assimilazione si influenzano a vicenda, il progetto avrà una base solida per crescere; se non lo dimostra, è meglio correggere il loop prima di espandere ambientazioni e contenuti.
