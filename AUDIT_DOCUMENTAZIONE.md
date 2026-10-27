# Goblin Warlord — Fase A: audit della documentazione

Data: 23 ottobre 2026. Stato: audit completato; in attesa del feedback dell'autore prima delle fasi di progettazione approfondita.

Questo documento ricostruisce lo stato del progetto, distingue decisioni e ipotesi, evidenzia i conflitti e raccomanda una prima selezione di sei classi. Non è il GDD definitivo, non approva automaticamente le nuove ipotesi e non avvia l'implementazione. Nessun sistema è dichiarato bilanciato: non sono disponibili risultati di playtest.

## 1. Fonti, metodo e significato degli stati

### 1.1 Materiali esaminati

| ID | Fonte | Funzione e limiti |
|---|---|---|
| S1 | [PIANO_PROGETTO.md](./PIANO_PROGETTO.md) | Sintesi corrente della direzione del progetto; dichiara di recepire le risposte alla terza valutazione. Contiene anche proposte tecniche e parametri da provare. |
| S2 | [CLASSI_E_ABILITA.md](./CLASSI_E_ABILITA.md) | Catalogo di 28 kit proposti: nomi, tre azioni, passiva e tre tratti per classe. Non equivale a 28 classi approvate o pronte per lo sviluppo. |
| S3 | [VALUTAZIONE_DESIGN.md](./VALUTAZIONE_DESIGN.md) | Prima analisi e risposte dell'autore nella sezione finale «Risposta alle domande», righe 278–324. |
| S4 | [VALUTAZIONE_DESIGN_2.md](./VALUTAZIONE_DESIGN_2.md) | Seconda analisi e risposte dell'autore nella sezione «Risposte», righe 345–405. |
| S5 | [VALUTAZIONE_DESIGN_3.md](./VALUTAZIONE_DESIGN_3.md) | Terza analisi, con risposte inserite nella sezione 6, righe 163–197. Documenta il cambio esplicito verso il combattimento a turni. |
| S6 | [VALUTAZIONE_DESIGN_4.md](./VALUTAZIONE_DESIGN_4.md) | Valutazione del sistema a turni e quaderno D01–D26. Tutte le risposte sono ancora «Da compilare»; i suggerimenti non sono decisioni dell'autore. |
| S7 | Allegato «MASTER PROMPT — GOBLIN WARLORD ROGUELIKE», file `Pasted text.txt` fornito in questa conversazione | Nuovo incarico, principi, requisiti delle fasi successive e ipotesi da valutare. La sezione «PRIMO COMPITO» limita il lavoro attuale alla Fase A. |

Nel workspace sono presenti questi sei documenti Markdown e un `.gitignore` per Godot. Non risultano file di progetto Godot, scene, script, asset, tabelle numeriche o report di test. Le discussioni disponibili sono quelle riportate nei documenti e nella conversazione: non si presume l'esistenza di altri materiali non forniti.

I richiami a Slay the Spire, Darkest Dungeon 1/2, Fate/Grand Order e D&D sono riferimenti dichiarati dall'autore, non specifiche importate dai rispettivi giochi. Questo audit riguarda il materiale disponibile: non attribuisce a quei riferimenti regole non documentate nel progetto.

### 1.2 Classificazione

- **Confermato:** direzione esplicitamente adottata nel piano corrente o istruzione diretta del nuovo incarico. È una conferma documentale, non prova di bilanciamento né approvazione separata di ogni dettaglio del piano.
- **Proposto:** ipotesi già presente, esempio o kit provvisorio; non viene promosso a regola definitiva.
- **Nuova proposta:** raccomandazione elaborata in questo audit.
- **Da validare:** punto che richiede una decisione dell'autore o una prova. Si distingue fra **approvazione di design** e **playtest**: una prova non può decidere da sola il tono o l'intenzione creativa.

Queste etichette possono convivere: la presenza di una funzione può essere confermata, mentre valori e funzionamento restano da validare. Quando una risposta storica è interrogativa ma il piano la presenta come requisito, il passaggio viene segnalato.

### 1.3 Criterio per i conflitti

Non viene scelta automaticamente la frase del file più recente. Si cercano una decisione esplicita e il relativo recepimento. Esempio: il combattimento a turni prevale sull'autobattler puro perché S5 registra «Facciamo un cambio rotta» e S1 recepisce quella decisione. Al contrario, quattro unità in S7 sono presentate come «Ipotesi iniziale»: richiedono un confronto con il limite corrente di cinque, non una sostituzione silenziosa.

## 2. Sintesi strutturata del gioco

### 2.1 Visione ricostruita

**Goblin Warlord è attualmente un roguelite tattico dark fantasy, single-player offline, in 2D laterale, nel quale un signore della guerra guida un'orda di individui goblin attraverso una mappa a nodi fino alla capitale.** La campagna completa prevista comprende tre atti, ciascuno concluso da un boss. Le vittorie forniscono risorse e conoscenze legate ai nemici affrontati; tali conoscenze ampliano le possibilità di creare e sviluppare la squadra.

Ogni goblin combina **classe**, che ne definisce il ruolo, e **origine/specie materna**, che conferisce una passiva ereditata. Il nuovo brief chiama questi goblin **Progenie**: è una denominazione introdotta dall'autore in S7, non un termine già presente nel glossario di S1.

Il giocatore prepara la squadra e decide azioni e bersagli nel combattimento manuale. Può anche delegare all'automazione, che segue priorità o personalità delle unità. Le perdite e il danno persistente rendono importante la gestione della campagna; gli sblocchi fra campagne ampliano le opzioni disponibili al nuovo tentativo.

### 2.2 Fantasia, pubblico e tono

| Aspetto | Stato ricostruito |
|---|---|
| Fantasia centrale | Essere il comandante di un'orda goblin spietata che cresce attraverso la conquista. |
| Obiettivo | Marcia fino alla capitale e vittoria sul boss finale; nessuna via diplomatica alternativa. |
| Pubblico | Adulto, interessato a dark fantasy, strategia accessibile e campagne ripetibili. |
| Tono | Prevalentemente tragico, con umorismo dovuto alla stupidità dei goblin soprattutto negli eventi. |
| Rappresentazione | Niente sangue esplicito; cattura, rapporti e riproduzione restano impliciti/fuori campo. |
| Formato | PC come piattaforma iniziale proposta; Godot 4 come tecnologia prevista; testi italiani e inglesi. |
| Modello commerciale | Premium a prezzo unico nel piano; primo atto come Accesso Anticipato, atti successivi subordinati a risorse e finanziamento. Prezzo non fissato. |

Fonti: S1 §§1–3, 6–9; risposte finali di S3; S7 §§2–3.

### 2.3 Ciclo attuale

1. Scegliere il signore della guerra e le opzioni iniziali della rosa.
2. Leggere tipo, difficoltà e possibili indizi dei nodi raggiungibili; scegliere il percorso.
3. Preparare membri, equipaggiamento e formazione prima dello scontro.
4. Scegliere azioni e bersagli a turni oppure delegare all'automazione.
5. Ottenere bottino e progresso collegato ai nemici affrontati.
6. Gestire salute persistente, provviste, tesoro e opportunità di creazione/sviluppo.
7. Affrontare il boss dell'atto e proseguire, oppure perdere il tentativo.
8. Conservare gli sblocchi previsti, ricominciare con nuove possibilità; gli individui non sopravvivono alla sconfitta.

### 2.4 Identità distintiva e verifica necessaria

Il collegamento più promettente è **percorso → avversari → conoscenze → combinazioni classe/origine → nuove scelte tattiche**. È una valutazione di design, non un risultato sperimentale. Nessun documento dimostra ancora che lo sblocco arrivi abbastanza presto da incidere sulla stessa campagna o che le origini modifichino davvero il modo di giocare.

## 3. Inventario delle meccaniche

### 3.1 Direzioni già confermate

| Sistema | Quanto risulta adottato | Cosa resta aperto | Fonti |
|---|---|---|---|
| Campagna | Un'unica marcia ramificata, tre atti previsti, capitale come obiettivo finale | Lunghezza, curva e contenuti concreti | S1 §§1, 4, 5.5; S3 risposte |
| Combattimento | A turni, manuale come riferimento, automazione opzionale | Ordine delle attivazioni, azioni universali, durata del round | S5 §6 risposte 1–4; S1 §5.2 |
| Squadra e riserve | Nel piano: massimo cinque attivi e cinque riserve; cambi prima degli scontri | Revisione a quattro proposta in S7; conferma del cap riserve | S1 §§5.1, 7; S4 risposta 1 |
| Identità delle unità | Individui con nome, classe fissa, origine, salute e crescita durante la campagna | Generazione degli attributi e recupero dei nuovi membri | S1 §§5.1–5.3 |
| Azioni di classe | Attacco base sempre disponibile, abilità ordinaria e suprema | Kit esecutivi, tempi e revisione verso carica della suprema | S1 §5.2; S2 regole comuni; S7 §4.4 |
| Targeting | Manuale fra bersagli validi; mischia di base contro prima linea, distanza verso tutte le unità salvo restrizioni | Geometria, gerarchia provocazioni/protezioni, eccezioni | S5 risposta 4; S1 §5.2 |
| Informazioni in battaglia | Bersaglio nemico e stima del danno nel manuale; previsione non calcolata in automatico | Affidabilità con casualità e cambi di bersaglio | S5 risposta 12; S1 §§5.2, 11 |
| Automazione | Priorità legate alla personalità; possibilità di includere/escludere le supreme | Regole operative, intervento manuale e configurazione | S5 risposte 1, 4; S1 §5.2 |
| Eredità | Origine materna separata dalla classe; passiva riutilizzabile su più classi | Specie effettive, effetti e limiti | S5 risposta 11; S1 §5.1 |
| Conoscenze | Progressione collegata a tipo e difficoltà dei nemici; creazione attraverso nodi dedicati | Unità diretta o sblocco, soglie, costi e persistenza dei conteggi | S3 risposte; S4 risposta 6; S5 risposta 9 |
| Salute e recupero | Danni persistenti, provviste che curano nel viaggio, riposi con recupero aggiuntivo; nessun sistema separato di gravità delle ferite nelle risposte | Quantità, priorità, riserve e consumo automatico | S4 risposta 10; S5 risposta 13; S1 §§5.3–5.4 |
| Morte | Caduti persi per la campagna; nessuna resurrezione in combattimento; possibile eccezione tramite evento, con beneficio alternativo senza caduti | Costo e limiti dell'evento, oggetti del caduto | S5 risposte 3, 6; S1 §5.2 |
| Fine del tentativo | Sconfitta di tutti gli attivi: le riserve fuggono e la campagna termina | Comunicazione e casi simultanei | S5 risposta 7; S1 §5.3 |
| Cura e scudo | La sovracura diventa scudo; Chierico con suprema di protezione di squadra | Limite, accumulo, scadenza e persistenza degli scudi | S5 risposta 3; S1 §5.2; S2 indicazioni finali |
| Equipaggiamento | Tre slot base: arma, armatura, speciale; si accetta la sostituzione solo con rarità superiore; il drop può essere rifiutato | Trasferimento, inventario, oggetti sostituiti e recupero alla morte | S4 risposta 7; S1 §5.4 |
| Valute di campagna | Provviste per recuperare salute; tesoro per mercanti/eventi; influenza esclusa dal perimetro corrente | Prezzi, entrate e spese | S1 §5.4 |
| Congedo | Mandare una riserva «a caccia» la rimuove definitivamente in cambio di tesoro | Momento, compenso e spiegazione narrativa | S5 risposta 9; S1 §5.3 |
| Mappa | Tipi e difficoltà visibili, dettagli nascosti, possibili icone-indizio, eventi «?» | Distribuzione reale, varietà fra campagne, profondità delle informazioni | S4 risposta 5; S5 risposta 8; S1 §5.5 |
| Incontri | Composizioni progettate e verificate singolarmente; niente ripetizioni dello stesso incontro nella campagna | Criterio preciso di unicità e quantità sostenibile | S4 risposta 15; S5 risposta 14; S1 §5.5 |
| Vincoli della mappa | Nel piano: almeno due mercanti, cinque élite, cinque riposi sull'intero grafo dell'atto; tesoro/razzia circa a metà di ogni percorso | Numero di nodi realmente visitati e bilancio di ogni rotta | S4 risposta 14; S1 §§5.5, 7 |
| Razzie | Nodi senza battaglia, provviste e cura leggera; al massimo una ricompensa rara di linea materna per atto | Probabilità e valore rispetto alle battaglie | S4 risposta 11; S1 §5.5 |
| Boss | Una meccanica riconoscibile e anticipata; più composizioni devono poterla affrontare | Primo boss, pattern e controlli ammessi | S1 §§5.5, 12 |
| Meta-progressione | Sblocchi di opzioni fra tentativi; tratti tramite uso della classe/abilità e vittorie con signori della guerra; niente individui conservati dopo la sconfitta | Tabella sblocchi, limiti di potenza e anti-ripetizione artificiosa | S4 risposte 13, 17; S5 risposta 15; S1 §5.3 |
| Produzione | Placeholder e asset gratuiti prima della validazione; primo atto come prima release prevista | Budget, tempi, team e contenuto minimo | S3 risposte 18–20; S1 §§7–9 |

**Precisazione sui numeri di squadra:** il limite di cinque attivi è una decisione esplicita storica. I cinque di panchina nascono invece come «altri 5?» in S4 e sono diventati un requisito nel piano. Il piano è coerente internamente su 5+5, ma l'origine interrogativa delle riserve merita una conferma, soprattutto se si passa a quattro attivi.

### 3.2 Ipotesi già presenti, senza specifica definitiva

| Elemento proposto | Evidenza | Perché non è ancora una regola pronta |
|---|---|---|
| Cooldown ordinari 1–2 turni e supreme 3–5 o più | S5 risposta 2; S1 §5.2 | Valori indicativi; manca il momento di decremento e S7 apre la carica |
| Soglie 5/10/15/20 nemici | S5 risposta 9; S1 §§5.1, 14 | Non sono mappate a ricompense; non è decisa la persistenza |
| Sei attributi: Forza, Destrezza, Costituzione, Intelligenza, Saggezza, Carisma | S5 risposta 11; S1 §§5.1–5.2 | L'elenco è adottato nel piano; formule, impieghi distinti e curve non esistono |
| Rigenerazione, slot speciale extra, doppia arma, suprema più frequente | S5 risposta 11; S1 §5.1 | Esempi di passive senza specie assegnata né valore/limite |
| Artefatti del signore della guerra | S5 risposta 10; S1 §§4, 7 | Presenza adottata nel piano; effetti di danno, soglie e ritrovamento sono alternative, non bonus tutti cumulativi |
| Bonus di vicinanza e preferenze di posizione | S4 risposta 3; S1 §§5.2, 7 | Non sono stabiliti geometria e compromessi; il prototipo li richiede ma la roadmap li subordina alle regole base |
| Tratti, talenti e set | S1 §§5.3–5.4 | Distinzione e limiti incompleti; set esplicitamente successivi alla verifica degli oggetti singoli |
| Albo degli eroi | «Volendo» in S4 risposta 17; incluso nell'Accesso Anticipato in S1 | Intento commemorativo chiaro, contenuto e priorità non validati |
| Cure da 5 HP, riposo da 10 HP a tutti, razzia +5 provviste | S4 risposta 10; S1 §5.4 | Parametri storici esemplificativi, non economia bilanciata |
| Architettura con Resource e separazione dati/scene | S1 §10 | Pianificazione tecnica proposta; nessuna implementazione presente |

### 3.3 Nuovo brief: obblighi e ipotesi non sono equivalenti

| Elemento in S7 | Stato corretto per questo audit |
|---|---|
| Svolgere ora solo Fase A e attendere feedback | **Confermato — istruzione operativa.** Nessun GDD completo, codice o combat approfondito in questa fase. |
| Almeno sei classi esistenti completamente progettate per demo e MVP | **Confermato — nuovo requisito delle fasi successive.** Ora si produce la raccomandazione, non le sei specifiche complete. |
| Distinzione prototipo / demo / MVP | **Confermato — nuovo requisito documentale.** Il contenuto esatto va ancora progettato. |
| Warlord significativo con ruolo attivo da progettare | **Confermato — nuovo obiettivo.** Non sono confermati ordini, frequenza o resource model specifici. |
| Complessità emergente, classi autonome, sinergie ampie, scope contenuto | **Confermato — criteri di progettazione del nuovo incarico.** La loro realizzazione resta da dimostrare. |
| Nome Progenie | **Confermato — lessico introdotto dall'autore.** Da integrare con rosa/squadra/panchina, che indicano insiemi diversi. |
| Quattro attivi, quattro posizioni e signore della guerra esterno | **Proposto — ipotesi iniziale esplicita.** Conflitto da risolvere con il 5+5 corrente. |
| Attivazioni alternate | **Proposto — direzione preferita.** Il confronto con altre due strutture è richiesto per la progettazione successiva. |
| Nessun vincolo alla posizione del lanciatore, ma bersagli limitati per posizione | **Proposto — direzione preferita.** Non è ancora una specifica della formazione. |
| Suprema con carica | **Proposto — nuova direzione da progettare e validare.** Non coincide con il cooldown attuale e non ha generazione/costi definiti. |
| Autorità | **Proposto — risorsa di comando da valutare.** Non è né automaticamente ammessa né esclusa dal vecchio rifiuto dell'influenza. |
| Tre stadi evolutivi | **Proposto e condizionale.** Il brief chiede di verificarne compatibilità e conferma, non di fingere che esistano già. |
| Durate 30–90 s / 2–3 min / 3–5 min | **Proposto — obiettivi indicativi da playtestare**, non prestazioni già raggiunte. |
| Esplorazione come nodo, Breeding Grounds con più servizi | **Proposto — estensione dei nodi esistenti.** La creazione è già presente; gli altri servizi e il nodo esplorazione autonomo non lo sono. |
| Generazione procedurale | **Da valutare**, non un obbligo di introdurla. Va conciliata con gli incontri progettati singolarmente e il limite alla complessità della mappa. |

### 3.4 Confini da conservare

Il piano esclude dal perimetro corrente multiplayer e networking, combattimento action/platforming, mondo aperto, diplomazia come via di vittoria, gestione esplorabile della base, dialoghi doppiati e cinematiche. Esclude inoltre la rappresentazione esplicita della riproduzione e la produzione artistica costosa prima della validazione. S7 non riapre questi sistemi e chiede di non introdurre un deckbuilder senza una decisione motivata. L'eventuale confronto con altri giochi non costituisce autorizzazione a importarli.

## 4. Inventario di classi, origini e altri contenuti

### 4.1 Le 28 classi con un kit nel catalogo

Tutte le righe seguenti hanno stato **Proposto** per il kit. I nomi esistono nei documenti; numeri, costi e risoluzione degli effetti non sono specificati. Le categorie sono quelle di S2 e non dimostrano potenza superiore o prerequisiti di sblocco.

| Categoria | Classe | Identità esistente / nucleo del kit | Dipendenza o ambiguità da risolvere |
|---|---|---|---|
| Base | Barbaro | Danno ravvicinato, Rabbia e Turbine selvaggio; rischio a bassa salute | Carica della Rabbia e cooldown; resistenza e difesa da distinguere |
| Base | Bardo | Ritornello e Ballata dell'orda; supporto agli attacchi alleati | «Velocità d'attacco» da tradurre nei turni |
| Base | Chierico | Fiamma sacra, Cura, Barriera del coro | Scudi, sovracura e rischio di cura obbligatoria |
| Base | Druido | Spina viva, Radici avvolgenti, Eclissi di rovi | Utilità dell'immobilizzazione con posizioni fisse; velocità d'attacco |
| Base | Guerriero | Colpo d'arma, Provocazione, Muro di scudi | Geometria della protezione e precedenza del taunt |
| Base | Ladro | Stoccata, Veleno rapido, Colpo alle spalle | Accesso alle retrovie e significato dello spostamento |
| Base | Mago | Dardo arcano, Scheggia elementale, Cataclisma | Chi sceglie l'elemento e come si determina l'area |
| Base | Monaco | Pugno ritmico, Passo leggero, Mille colpi | Interruzioni, schivata e riposizionamento |
| Base | Paladino | Lama consacrata, Giuramento protettivo, Giudizio solare | «Più esposto», aura e scala di danno/cura |
| Base | Ranger | Freccia precisa, Tiro segnato, Pioggia di frecce | Marca generica, passiva automatica e protezione della prima linea |
| Base | Stregone | Scarica innata, Fiammata erratica, Eruzione del sangue | Casualità, energia aggiuntiva e costo della suprema |
| Avanzata | Alchimista | Fiala corrosiva, Miscela instabile, Grande reazione | Scelta degli effetti; uso delle cariche di reagente |
| Avanzata | Cavaliere | Affondo in sella, Sfida, Carica della lancia | Movimento, slancio e costi di rappresentazione |
| Avanzata | Convocatore | Comando del vincolo, Evocazione minore, Manifestazione maggiore | Esistenza iniziale dello spirito, slot e azioni delle evocazioni |
| Avanzata | Fattucchiere | Dardo del malocchio, Sventura, Patto infranto | Famiglio, effetti trasferibili e cumulo delle maledizioni |
| Avanzata | Inquisitore | Colpo inquisitorio, Interrogatorio, Sentenza | Interruzione di abilità «in corso» e velocità d'attacco |
| Avanzata | Magus | Lama incantata, Incanta lama, Varco tagliente | Linee, portata e timing dell'attacco potenziato |
| Avanzata | Morfico | Arto adattivo, Mutazione reattiva, Forma perfetta | Scelta delle forme e costo di varianti visive |
| Avanzata | Oracolo | Presagio, Filo del fato, Esito inevitabile | Valore aggiunto rispetto alla previsione già universale |
| Avanzata | Pistolero | Colpo di pistola, Tiro di risposta, Scarica a ventaglio | Caricatore e ricarica rispetto all'attacco sempre disponibile |
| Alternativa | Antipaladino | Lama empia, Aura di terrore, Anatema | Definizione di vigore e conversione di cure/protezioni |
| Alternativa | Ninja | Kunai d'ombra, Sostituzione, Catena silenziosa | Priorità di Non visto, esca e targeting obbligatorio |
| Alternativa | Samurai | Iai, Guardia del duello, Taglio del crepuscolo | Preparazione e immunità alle interruzioni non ancora formalizzate |
| Ibrida | Arcanista | Dardo modulato, Riserva arcana, Formula suprema | Doppia fonte della riserva e scelta danno/barriera |
| Ibrida | Brawler | Gancio brutale, Presa e lancio, Rissa totale | Spinte, collisioni e interruzioni |
| Ibrida | Cacciatore | Dardo da caccia, Trappola preparata, Preda abbattuta | Percorso delle trappole e ruolo del compagno animale |
| Ibrida | Scaldo | Corno di guerra, Ritmo di battaglia, Saga dell'ultima carica | Attacchi extra, sequenze e cariche di impeto/gloria |
| Ibrida | Sciamano | Spirito guida, Totem ancestrale, Assemblea degli spiriti | Totem, affinità e selezione automatica del bisogno |

Conteggio verificato: **11 base + 9 avanzate + 3 alternative + 5 ibride = 28**. Nel catalogo ogni classe ha anche una passiva e tre idee di tratti; non sono alberi completi di sviluppo né varianti evolutive per stadio.

### 4.2 Nomi storici da non perdere

S4, risposta 4, cita anche **Necromante, Psionico, Evocatore ed Elementalista**, senza svilupparne un kit. Vanno conservati come concetti menzionati, non presentati come classi già progettate.

**Evocatore** potrebbe essere un nome precedente di **Convocatore**, ma l'equivalenza non è documentata: non si contano automaticamente due kit diversi e non si cancella il nome storico. Gli altri tre nomi non hanno una scheda nel catalogo corrente. Questa distinzione evita sia di dimenticare idee originali sia di gonfiare il roster disponibile.

### 4.3 Specie materne: cosa esiste davvero

**Non esiste ancora un catalogo di specie materne nominate, con statistiche e passive assegnate.** Il goblin è la base dell'orda e della rosa iniziale; questo non dimostra che sia già stata progettata una specifica voce «madre goblin» con un proprio tratto.

| Elemento documentato | Stato | Quanto manca |
|---|---|---|
| Goblin come unità di base | Confermato | Statistiche di base e rapporto preciso fra specie del figlio e origine materna |
| Origine materna come passiva indipendente dalla classe | Confermato come struttura | Nomi, disponibilità, svantaggi eventuali e identità delle origini |
| Bonus a un attributo | Proposto | Attributo, quantità, specie e rilevanza per più classi |
| Rigenerazione ogni turno | Proposto | Valore, momento, limiti e rapporto con logoramento/provviste |
| Slot speciale aggiuntivo | Proposto | Specie, regole dell'inventario e valore rispetto alle altre origini |
| Due armi | Proposto | Specie e comportamento: statistiche, attacchi, animazioni e slot |
| Un turno in meno alla suprema | Proposto | Limite minimo; eventuale conversione se si adotta la carica |
| Linea materna rara da razzia | Confermato come possibilità, massimo una per atto | Catalogo, probabilità e disponibilità effettiva |

Nessuna origine alternativa riceve un nome inventato in questa fase. Non è quindi ancora possibile valutare «ogni razza» individualmente o scegliere fra razze già definite per la demo: manca il materiale necessario. È invece già possibile progettare in seguito un piccolo insieme coerente con questa struttura.

### 4.4 Contenuti e pianificazione presenti, senza catalogo esecutivo

- **Signori della guerra:** almeno tre nel piano, orientati a mischia, distanza e magia; nessun nome proprio, kit di ordini o artefatto numerico completo. La risposta storica «guerriero, mago, ladro» è esemplificativa, non tre personaggi già caratterizzati.
- **Nemici:** famiglie e comportamenti sono menzionati; non esiste il roster richiesto dal nuovo incarico con sei archetipi completi, due élite e un boss.
- **Eventi e tesori:** esistono tipi, funzioni e temi; mancano cataloghi di dieci eventi con scelte e dieci ricompense strategiche concrete.
- **Progressione:** esistono livelli e tratti come direzione; non esistono soglie XP, livello massimo, percorsi di evoluzione o bilancio numerico della campagna.
- **UI:** sono elencate schermate e informazioni da mostrare; mancano flussi verificati, layout e testi di errore del targeting.
- **Tecnica:** esiste una proposta di cartelle, scene e responsabilità in S1 §10; non risultano implementazione, scelta di versione Godot oltre alla famiglia 4.x o verifiche tecniche.

## 5. Evoluzione delle decisioni e conflitti da esplicitare

### 5.1 Evoluzioni storiche riconoscibili

| Tema | Versione precedente | Evidenza del cambiamento | Lettura dell'audit |
|---|---|---|---|
| Controllo del combattimento | Preparazione e autobattaglia senza input, poi frequenze in secondi | S5 risposta 1 dichiara il cambio a turni; S1 lo recepisce | Il manuale a turni è corrente; l'automazione resta opzionale. I passaggi narrativi precedenti descrivono una versione superata. |
| Rianimazione | Resurrection del Chierico con 30% salute in S4 risposta 4 | S5 risposte 3 e 6 rifiutano la resurrezione in battaglia | Divieto corrente coerente con S1 e S2. Non è un conflitto residuo fra i due documenti principali. |
| Razzie | Parte degli eventi possibili in S3 | S4 risposta 11 sceglie nodi dedicati e limite di una linea rara per atto | La versione corrente è il nodo dedicato; non va reintrodotto automaticamente come evento indistinto. |
| Dimensione della rosa | Cinque complessivi nella prima formulazione di S3 | S4 risposta 1 chiarisce cinque schierati e propone cinque riserve | Il piano adotta 5+5; confermare la riserva, senza ripristinare il vecchio cap totale di cinque. |
| Importanza dell'ordine iniziale | Ordine della formazione come ordine delle abilità in S3 | S4 apre ritmo individuale; S5 passa alla scelta manuale | Non è più lecito usare la vecchia frase per imporre l'ordine delle azioni. La struttura dei turni resta aperta. |
| Prima selezione delle classi | S4 risposta 4 propone Guerriero, Barbaro, Chierico e Stregone | S5 risposta 16 sceglie Guerriero, Ranger, Stregone e Chierico per l'atto uno; S1 li adotta come quattro ruoli tutorial | Ranger prende il posto di Barbaro nella selezione corrente. Raccomandare ora Barbaro fra le sei classi significa aggiungerlo, non ripristinare silenziosamente il vecchio gruppo. |

Le introduzioni e varie raccomandazioni di S4 e S5 continuano a parlare di autobattaglie senza input: vanno lette insieme alle risposte successive inserite negli stessi file. S6 è già riferita al sistema manuale, ma non contiene nuove risposte dell'autore.

### 5.2 Conflitti e passaggi non approvati esplicitamente

| ID | Punto | Fonti e differenza | Effetto sul lavoro successivo |
|---|---|---|---|
| C01 | Cinque contro quattro attivi | S1 adotta cinque; S7 §4.1 propone quattro, e gli esercizi di squadra successivi usano quattro | Occorre una scelta esplicita. Sei classi di catalogo non significano sei unità schierate; il cap riserve non diventa automaticamente quattro. |
| C02 | Suprema a cooldown contro carica | S1/S5 parlano di 3–5 turni; S7 §4.4 orienta verso carica | Cambia ritmo, possibilità di aprire con la suprema, passive materne e accumuli dello Stregone. Non sommare cooldown e carica senza una ragione. |
| C03 | Collocazione e ruolo del Warlord | S1 definisce soprattutto rosa iniziale e artefatto; S7 chiede un ruolo attivo e ipotizza che resti esterno | Non è stabilito se occupi slot o possa morire. Il ruolo attivo è un obiettivo nuovo, i mezzi sono ancora da scegliere. |
| C04 | Autorità e influenza | Influenza esclusa in S1; Autorità proposta come comando tattico in S7 | Sono concetti diversi: la vecchia esclusione non vieta automaticamente il nuovo, ma serve un'utilità distinta rispetto ad azioni e supreme. |
| C05 | Stadi evolutivi | S1 ha livelli/tratti; S7 propone tre stadi solo se compatibili | Nessun sistema di stadi è già confermato. Vanno valutati differenza dai livelli, tempi della campagna, costi e rappresentazione. |
| C06 | Mappa progettata e casualità | S4 parla di battaglie/eventi casuali; S1 prevede mappa progettata e incontri authored; S7 chiede di valutare proceduralità | Distinguere topologia, assegnazione dei nodi, selezione degli incontri e composizione nemica. Quest'ultima non è prevista casuale nella direzione attuale. |
| C07 | Targeting del manuale e testo dei kit | Le regole comuni di S2 danno scelta; molte azioni indicano «più vicino», «più ferito» o simili | Separare vincolo, suggerimento e priorità automatica; la capacità non deve cambiare significato a seconda della lettura. |
| C08 | Kit storici e kit del catalogo | S4 risposta 4 propone Shield Bash, Doppio colpo, Fireball/Meditation; S2 usa Muro di scudi, Turbine, Fiammata/Eruzione | S1 recepisce i quattro ruoli e rimanda al catalogo, ma manca una motivazione esplicita per ogni sostituzione. Trattare le azioni di S2 come proposte correnti, conservando le alternative storiche. |
| C09 | Razza, specie, origine e Progenie | S1 fissa «specie materna», «classe», «campagna»; S7 usa anche razza, madre, run e Progenie | Conservare il concetto originale; chiarire quali termini sono sinonimi e quali indicano unità, origine o insieme. Breeding Grounds necessita anche di un nome italiano coerente. |
| C10 | Prototipo, demo, MVP e Accesso Anticipato | S1 distingue soprattutto prototipo e prima release dell'atto uno; S7 richiede tre fasi separate | Definire in seguito il rapporto fra MVP e primo atto pubblico. La demo diventa un deliverable di progettazione richiesto, senza assumere che coincida con l'intero atto. |
| C11 | Roguelike e roguelite | S1 usa roguelite con sblocchi persistenti; S7 usa anche roguelike | È una differenza di lessico. Non autorizza a eliminare la meta-progressione già prevista. |

### 5.3 Consolidamenti del piano da riconoscere come tali

I seguenti punti risultano adottati in S1, ma la loro provenienza non consente di presentarli tutti come approvazioni dirette e inequivocabili dell'autore:

- **Classe immutabile dell'individuo:** S1 la stabilisce; la frase storica «i goblin son costretti a certe classi» in S5 può riferirsi anche a un catalogo limitato, non necessariamente al divieto di riclassare. Il vincolo è documentato nel piano, con origine interpretativa da confermare se rilevante.
- **Sovracura universale:** S1 e S2 la applicano generalmente; la risposta S5 nasce nella discussione del Chierico. L'estensione a qualunque fonte di cura è quindi un consolidamento, non un ambito esplicitamente discusso nella risposta originaria.
- **Premium, assenza di grind obbligatorio e prima campagna vincibile senza sblocchi necessari:** sono direzioni o criteri del piano; le risposte storiche approvano Accesso Anticipato e nuove opzioni, ma non ratificano singolarmente tutti questi dettagli. Il nuovo brief rafforza l'accessibilità e l'autonomia delle classi senza fornire una validazione numerica della meta-progressione.
- **Albo degli eroi e cinque riserve:** idee inizialmente opzionali o interrogative, poi incluse nel piano. Non sono funzioni già realizzate.
- **Numero di classi del primo atto:** S5 risposta 16 elenca quattro nomi rispondendo allo scope dell'atto uno; S1 li tratta come tutorial/prototipo e ammette espansioni. Il requisito nuovo di almeno sei classi per demo/MVP deriva adesso da S7: è un aumento esplicito dell'ambito, non una decisione già contenuta nella risposta storica.

Alcuni dettagli sono stati recepiti solo parzialmente: S4 specificava riposo senza consumo di provviste, mentre S1 non ne chiarisce l'ordine rispetto alla cura del viaggio; S3 descriveva le ricompense delle razzie come inferiori a quelle di una vera battaglia. Sono intenzioni da verificare nel bilancio dell'economia, senza trattare i vecchi valori numerici come definitivi.

La persistenza degli individui **dopo una vittoria** resta inoltre da chiarire: S4 dice «nessun goblin sopravvive alla partita», mentre S1 precisa soprattutto la sconfitta. Non va dedotto automaticamente un trasferimento dei vincitori alla campagna successiva.

### 5.4 Incoerenze puntuali del catalogo

- **Ranger, Preda costante:** prolunga la marca se sopravvive «l'alleato marcato», ma Tiro segnato marca un nemico. Il referente va corretto dopo aver confermato l'effetto desiderato (S2, Ranger).
- **Stregone, Riserva vitale:** parla di minore consumo di «salute/difesa»; Eruzione del sangue specifica soltanto una perdita temporanea di difesa. Il costo in salute non può essere dato per esistente (S2, Stregone).
- **Velocità d'attacco, interruzioni e preparazioni:** ricorrono in Bardo, Druido, Inquisitore, Monaco e Samurai, senza una struttura dei turni che le renda eseguibili.
- **Ranger e Oracolo:** priorità automatica e previsione potrebbero essere passive senza beneficio distinto nel manuale, dove il bersaglio è scelto e l'intento è già visibile.
- **Pistolero:** il caricatore può rendere indisponibile l'attacco base; manca una regola di ricarica compatibile con l'attacco base dichiarato sempre disponibile.
- **Convocazioni e compagni:** non sono definiti limiti, slot, azioni, bersagliabilità, morte e conteggio per le ricompense. La presenza di un famiglio nel testo non dimostra che sia una nuova unità sul campo.

Questi punti non impongono di eliminare le classi: indicano dove la proposta concettuale non è ancora una specifica implementabile.

## 6. Decisioni ancora aperte, ordinate per dipendenza

| Priorità | Decisione mancante | Perché viene prima | Rimando a S6 |
|---|---|---|---|
| Fondamentale | Quattro o cinque attivi, limite delle riserve, Warlord esterno o schierato | Determina campo, UI, economia delle azioni e costo dei contenuti | D03, D10, D21 |
| Fondamentale | Struttura del round, chi inizia, squadre asimmetriche, unità morte o controllate | Tutti i tempi e le previsioni dipendono da questa scelta | D02, D05 |
| Fondamentale | Geometria, avanzamento dopo la morte, cadaveri, scambi, unità grandi | Stabilisce portate, protezioni, aree e rischi di stallo | D03–D04; cadaveri e unità grandi aggiunti da S7 |
| Fondamentale | Attacco base, ordinaria, suprema; cooldown o carica; eventuali azioni universali | Serve un vocabolario comune per progettare le sei classi | D01, D05, D21 |
| Fondamentale | Attributi e formule: danno, mitigazione, cura, scudo, casualità | Senza queste basi i numeri delle classi non sono confrontabili | D07–D08 |
| Fondamentale | Intenti fissi o ricalcolati e precisione della previsione | Distingue errore del giocatore da informazione ingannevole | D06 |
| Fondamentale | Ruolo attivo e risorsa eventuale del signore della guerra | Deve sostenere le unità senza aggiungere un secondo sistema dominante | D10; estensione di S7 §4.5 |
| Prima del ciclo demo | Famiglie nemiche, soglie, ricompense e persistenza dei conteggi | Serve a collegare percorso e reclutamento prima del boss | D11–D12 |
| Prima del ciclo demo | Origini materne concrete e combinazioni disponibili | È un tratto distintivo del gioco, oggi senza contenuti specifici | D07, D12, D20 |
| Prima del ciclo demo | Livelli, XP, eventuali stadi e recupero dei nuovi reclutati | Evita che la recluta arrivi troppo debole o troppo tardi | D12, D16; stadi introdotti da S7 |
| Prima del ciclo demo | Morte, riserve, congedo e accesso al reclutamento | Deve esistere recupero da una perdita parziale senza annullarne il peso | D13 |
| Prima del ciclo demo | Economia di cure, provviste, tesoro e oggetti | Determina logoramento, acquisti e rotte praticabili | D08, D14–D15 |
| Prima del contenuto esteso | Durata della rotta, numero nodi, unicità e variazioni fra campagne | Il budget non può derivare solo dai minimi del grafo | D17–D18, D25 |
| Prima del contenuto esteso | Vocabolario limitato di stati e regole dei boss | Evita stati esclusivi e classi obbligatorie come contromisura | D04–D05, D19 |
| Prima del rilascio | Conclusione dell'atto uno, salvataggi, accessibilità, tutorial | Il primo atto deve sostenere il valore della release | D23–D24 |
| Prima delle prove | Metriche, pubblico dei tester e criteri di uscita | «Divertente» o «leggibile» da soli non permettono di decidere | D26 |

Non sono tutti dettagli di bilanciamento. La formula di danno e il timing di uno stato sono regole; il valore di danno e il numero di round di durata sono parametri. I primi richiedono una decisione coerente, i secondi una prima ipotesi da misurare.

## 7. Principali problemi di design

| Rischio | Causa concreta nel progetto | Conseguenza prevedibile | Raccomandazione preliminare dell'audit |
|---|---|---|---|
| Nucleo tattico ancora indeterminato | Manca la struttura comune di turni, posizioni e priorità | Ogni classe viene adattata con eccezioni diverse | Fissare un piccolo contratto di regole prima dei sei kit numerici |
| Troppe fonti della stessa progressione | Attributi, livelli, stadi eventuali, tratti, talenti, oggetti, set e origini | Scarsa leggibilità e costo combinatorio | Assegnare una funzione esclusiva a ogni livello di progressione; non adottare gli stadi per inerzia |
| Cura dominante e combattimenti prolungati apposta | Cure ricaricabili, danni persistenti, sovracura in scudo | Lasciare vivo un nemico debole può recuperare gratuitamente tutta la squadra | Verificare limiti e reset di cure/scudi prima di compensare aumentando i danni |
| Rotta scelta per accumulare conteggi | Soglie per nemico e sblocchi tramite uso di abilità | Premiare gruppi numerosi, evocazioni o azioni inutili | Definire unità conteggiabili, progresso per incontro e premi pertinenti alla difficoltà |
| Conoscenza senza opportunità d'uso | Soglia raggiunta ma nodo di creazione lontano, rosa piena o recluta arretrata | La ricompensa distintiva non cambia la partita in corso | Verificare un ciclo sblocco → creazione → impiego prima del boss |
| Perdita parziale che rende il tentativo irrecuperabile | Reclute deboli, riserve senza crescita/cura e reclutamento non accessibile | Il giocatore continua una campagna già compromessa | Valutare recupero dei nuovi membri e accesso ai nodi; preservare il peso della morte e il termine della campagna a squadra annientata |
| Possessività contro costruzione della squadra | Solo rarità superiori accettate, set e sinergie previsti | Oggetti di pari rarità utili diventano inutilizzabili; scelta iniziale punita | Simulare sequenze di drop, inventario e mercanti prima di espandere il bottino |
| Formazione poco significativa | Lanciatore libero e ranged su tutti i bersagli | Quattro/cinque posti diventano solo un ordine grafico | Dimostrare effetti di posizione comprensibili senza introdurre vincoli arbitrari |
| Specialisti senza bersaglio o senza funzione | Assassinio solo sulle retrovie, controllo basato sul movimento, priorità solo automatiche | Stallo o classe inutile in certi incontri/modalità | Prevedere strumenti di base affidabili e verificare casi di un solo superstite |
| Doppia modalità con comportamenti non leggibili | Manuale e personalità non hanno ancora una semantica unificata | Automazione percepita come stupida o manuale superfluo | Separare regole dell'abilità e policy di scelta; confrontare lo stesso incontro nelle due modalità |
| Ritmo incompatibile con gli obiettivi | Molte attivazioni, scelte e animazioni per ogni round | I 30–90 secondi degli scontri normali diventano irrealistici | Misurare tempo di decisione e presentazione separatamente; le durate sono target di S7, non garanzie |
| Contenuto progettato a mano troppo costoso | Unicità degli incontri, cinque élite sul grafo, molte varianti | Produzione e verifica superano il tempo disponibile | Definire cosa rende un incontro diverso e misurare il costo di una scheda completa |
| Rigiocabilità basata sulla sola sorpresa | Informazioni nascoste ma mappa/incontri memorizzabili | Le campagne successive hanno una rotta dominante | Provare la seconda partita; distinguere varietà strategica da segretezza |
| Incoerenza narrativa | Progenie creata durante una marcia, eventuali tre stadi, «caccia» con sparizione definitiva | Il lessico promette tempi o funzioni che il sistema non offre | Scrivere esempi di reclutamento, crescita e congedo coerenti con il tono già stabilito |

Le ultime colonne sono **Nuove proposte, da validare**, non contromisure già implementate. Il divieto di resurrezione non dimostra da solo che il Chierico sia facoltativo; il limite di squadra non impedisce da solo la crescita incontrollata della potenza.

## 8. Prima raccomandazione delle sei classi per demo/MVP

### 8.1 Selezione consigliata

**Nuova proposta:** conservare i quattro ruoli tutorial scelti dall'autore — **Guerriero, Ranger, Stregone, Chierico** — e aggiungere **Barbaro** e **Ladro**. Tutte e sei esistono nel catalogo e coprono i sei ruoli richiesti, senza imporre evocazioni, trasformazioni, munizioni o altre entità nel primo insieme.

Questa è una selezione da approvare per la progettazione. Non dimostra ancora equivalenza di potenza, autonomia di ogni classe o validità di ogni composizione. Le abilità nella tabella sono quelle del catalogo corrente, ancora proposte; non vengono fissati qui numeri o regole mancanti.

| Classe | Ruolo principale / secondario | Kit corrente da preservare come riferimento | Cosa verifica nella demo | Rischio da risolvere |
|---|---|---|---|---|
| **Guerriero** | Protettore / controllo del bersaglio | Colpo d'arma; Provocazione; Muro di scudi. Passiva: Guardia disciplinata. | Prima linea, protezione, provocazione e scelta fra difendere e infliggere danni | Taunt troppo totale o inefficace; adiacenza indefinita; confronto con Shield Bash storico |
| **Barbaro** | Danno fisico ravvicinato / attacchi multipli | Fendente furioso; Rabbia; Turbine selvaggio. Passiva: Furia crescente. | Rischio a bassa salute, pressione offensiva e differenza fra riduzione del danno e armatura | Dipendenza dalla cura, risorsa di Rabbia ridondante e confronto con Doppio colpo storico |
| **Ranger** | Danno a distanza / facilitazione del danno alleato | Freccia precisa; Tiro segnato; Pioggia di frecce. Passiva: Occhio del cacciatore. | Accesso ai bersagli arretrati e preparazione di un bersaglio per più classi | Marca da rendere generica, passiva utile in manuale e sovrapposizione con Ladro |
| **Chierico** | Guaritore / protezione | Fiamma sacra; Cura; Barriera del coro. Passiva: Voto di custodia. | Costo opportunità di curare anziché attaccare e rapporto scudi/logoramento | Cura obbligatoria, accumulo di scudi e vantaggio del prolungamento artificiale |
| **Stregone** | Magia e area / preparazione della suprema | Scarica innata; Fiammata erratica; Eruzione del sangue. Passiva: Magia incanalata. | Danno magico, area e scelta fra attaccare e preparare l'esplosione | Casualità leggibile, doppia carica se adottata per tutti, costo salute/difesa ambiguo |
| **Ladro** | Assassino / danno nel tempo | Stoccata; Veleno rapido; Colpo alle spalle. Passiva: Opportunista. | Scelta delle eliminazioni, vulnerabilità dei bersagli e accesso specializzato | Assassinio non deve diventare un comando morto contro un unico nemico in prima posizione |

### 8.2 Perché queste, e quali alternative conservare

- **Guerriero prima di Paladino:** è già tutorial e isola protezione/provocazione, senza aggiungere subito una seconda classe che combina cura, danno e aura.
- **Barbaro prima di Monaco o Brawler:** copre il danno ravvicinato con meno dipendenza da interruzioni e spostamenti non ancora definiti. L'accumulo di Rabbia resta comunque un problema da chiarire.
- **Ranger prima di Cacciatore o Pistolero:** è già tutorial e non richiede compagno animale, percorsi delle trappole o ricarica delle munizioni.
- **Chierico prima di Sciamano:** conserva il ruolo scelto e permette di misurare le cure senza introdurre totem e affinità.
- **Stregone prima di Mago:** rispetta la scelta esplicita dell'autore in S5. Il Mago è un'alternativa pertinente se si preferirà una magia più deterministica; sostituire lo Stregone ora sarebbe una modifica da motivare e approvare.
- **Ladro prima di Ninja:** testa l'assassino con veleno e opportunismo, senza dipendere da un'esca o dalla priorità speciale di Non visto. I movimenti del Colpo alle spalle vanno comunque adattati al modello scelto.

Questa selezione conserva la continuità del progetto; non elimina le altre classi. Le sei coprono problemi di design diversi, ma il vero confronto numerico e la matrice delle sinergie appartengono alla Fase C richiesta dal prompt.

### 8.3 Indicazione preliminare sulle origini

**Nuova proposta, da validare:** per progettare la demo, partire da una base goblin e **due origini materne alternative**, cioè tre profili d'origine complessivi, senza assumere che «base goblin» sia già il nome di una specie materna. Con sei classi si ottengono fino a 18 combinazioni teoriche, senza doverle rendere tutte disponibili in ogni nodo o inventare 18 kit esclusivi.

Il criterio per scegliere le due alternative dovrebbe essere provare due comportamenti trasversali differenti con effetti riutilizzabili. Nomi, lore, valori e perfino il numero finale restano da approvare. Per il prototipo tecnico può bastare la base e una sola alternativa. Questo è un limite di lavoro raccomandato, non un inventario già esistente.

## 9. Cosa è pronto e cosa manca per il futuro GDD

| Area del GDD richiesto | Materiale riutilizzabile | Materiale ancora da produrre dopo il feedback |
|---|---|---|
| Visione, tono, pilastri e ciclo | Buona base in S1 e risposte storiche | Allineamento del lessico e dei nuovi criteri di S7 |
| Combattimento, formazione e turni | Scelta manuale, targeting generale e automazione | Contratto delle regole, casi asimmetrici, morte, stati, intenti, formule |
| Warlord | Partenze e artefatti come direzione | Posizione rispetto al campo, azioni attive ed eventuale comando |
| Classi e sinergie | 28 kit qualitativi e quattro ruoli esplicitamente scelti | Sei schede numeriche, matrice 6×6, sei squadre da quattro nell'ipotesi del brief, simulazioni normale/élite/boss |
| Origini e progenie | Struttura classe + passiva materna | Catalogo minimo, combinazioni disponibili e costi di acquisizione |
| Livelli e stadi | Livelli, tratti e talenti come concetti | XP, limite, curva, recupero reclute e decisione sull'eventuale evoluzione |
| Mappa e nodi | Tre atti, tipi di nodo, informazioni e minimi del grafo | Percorsi completi, numero tappe, servizi dei nodi ed eventuale varietà controllata |
| Nemici, élite e boss | Requisito di incontri distinti e meccaniche leggibili | Roster, statistiche, pattern, ricompense e boss completo |
| Economia ed eventi | Due risorse di campagna e possessività degli oggetti | Bilanci di percorso, prezzi, dieci eventi e dieci tesori strategici |
| UI/UX e accessibilità | Elenco schermate e requisiti informativi di base | Flussi, targeting bloccato, tooltip, apprendimento e recupero della partita |
| Prototipo, demo e MVP | Prototipo e primo atto in S1 | Tre perimetri distinti, dipendenze e criteri di completamento |
| Godot e persistenza | Struttura proposta data-driven | Contratti dei dati, responsabilità, salvataggi e casi verificabili; sempre senza codice finché non autorizzato |
| Bilanciamento e playtesting | Checklist qualitative | Metriche, valori iniziali confrontabili, prove limite e criteri misurabili |

La Fase A non comprende ancora questi deliverable. In particolare non vengono inventati adesso sei nemici completi, dieci eventi, dieci tesori, formule o simulazioni per far apparire concluso un GDD che richiede prima il feedback richiesto dall'autore.

## 10. Feedback utile per autorizzare la fase successiva

Le domande seguenti riguardano la direzione, non impongono di rispondere ora alle 26 schede di S6. Quando una scelta è delegata al designer, basta indicarlo; verrà proposta e motivata nella fase appropriata.

| ID | Feedback richiesto | Campo per la risposta |
|---|---|---|
| F01 | Approvi Guerriero, Barbaro, Ranger, Chierico, Stregone e Ladro come le sei classi da progettare per demo/MVP? | Approvo |
| F02 | Quattro attivi è la nuova direzione da adottare o un'ipotesi da confrontare con cinque? Quale limite delle riserve vuoi mantenere o affidare alla valutazione? | Voglio tenere 4 goblin in campo per non rendere troppo pesante e lento il turno di gameplay e mettere in difficoltà il giocatore. Mentre la riserva vogio tenerla da altri 3 massimo (anche se in questa prima fase saranno 2 dato le classi) |
| F03 | Il Warlord deve restare esterno alla formazione? Possiamo esplorare un suo ruolo attivo mantenendo non confermata la risorsa Autorità? | Il warlord resta all'esterno e grazie ad esso si ottengono passive ed è lui che comanda |
| F04 | Vuoi che la suprema a carica sostituisca il cooldown, oppure che la Fase B confronti le due soluzioni prima della scelta? | Si sostituzione |
| F05 | Gli stadi evolutivi sono una caratteristica desiderata o vanno inclusi soltanto se risultano distinti e utili rispetto a livelli e tratti? | caratteristica desiderata che potrebbe sbloccare / aggiungere nuove abilità e possiblità che tuttavia non devono essere sviluppate adesso ma tenute in considerazione |
| F06 | Esistono nomi/lore di specie materne non presenti nei file? In assenza di altri materiali, possiamo proporre il piccolo catalogo indicato in §8.3 senza attribuirgli uno stato già confermato? | Non sono ancora state fatte tutte le specie materne, puoi prendere ispirazione dalle razze più comuni fantasy e di Dungeon and dragons da giocatore, quelli civilizzati e umanoidi per generarne |
| F07 | I kit storici alternativi — Shield Bash, Doppio colpo, Fireball/Meditation — vanno mantenuti come candidati, oppure preferisci usare come base esclusiva quelli di S2? | Quelli nuovi |
| F08 | Confermi che la prima release pubblica rimane l'atto uno in Accesso Anticipato e che la demo deve essere progettata come fase distinta? | Confermo |

### Conclusione della Fase A

La visione è sufficientemente ricostruita per passare a una proposta di design, ma non è ancora una specifica implementabile. Il patrimonio reale è una direzione creativa abbastanza stabile, molte risposte esplicite, quattro ruoli iniziali confermati e 28 kit qualitativi. Le lacune maggiori sono il contratto del combattimento, le origini concrete e il collegamento numerico fra incontri, sviluppo e reclutamento.

**Punto di arresto richiesto:** attendere il feedback dell'autore sull'audit prima di procedere alla progettazione approfondita del combattimento e delle sei classi. Nessuna implementazione avviata; i documenti originali restano invariati.
