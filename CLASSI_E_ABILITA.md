# Goblin Warlord — Classi, abilità e tratti

> Proposta di design per le 30 classi richieste. I nomi e gli effetti sono originali e provvisori: vanno bilanciati con il prototipo dell'autobattler prima di diventare contenuti definitivi.

## Regole comuni di lettura

- **Attacco base:** azione automatica ripetuta al ritmo del personaggio.
- **Abilità spam:** potere automatico con cooldown breve o medio.
- **Ultimate:** potere automatico con cooldown lungo; nessuna attivazione manuale durante la battaglia.
- **Passiva (tratto):** regola sempre attiva che definisce l'identità della classe.
- I bersagli delle abilità vengono scelti automaticamente secondo una priorità leggibile, per esempio alleato con meno HP, nemico più vicino o nemico marcato.
- I numeri non sono fissati in questa fase. Le differenze dovrebbero derivare soprattutto da bersagli, tempi, posizionamento e sinergie, non da moltiplicatori sempre più grandi.
- I tratti sbloccabili sono idee passive alternative o miglioramenti di comportamento. Non sono un albero di abilità già bilanciato.

## Classi Base

### Barbaro

- **Attacco base — Fendente furioso:** colpo ravvicinato; infligge più danno quando il Barbaro ha pochi HP.
- **Abilità spam — Rabbia:** entra in furia per alcuni secondi, aumentando danno e resistenza ai colpi ma riducendo la difesa.
- **Ultimate — Turbine selvaggio:** colpisce più nemici vicini in sequenza; i colpi successivi fanno meno danno.
- **Passiva — Furia crescente:** subire danni carica Rabbia; la carica decade lentamente fuori dal combattimento.
- **Tratti sbloccabili:** *Sangue caldo* (Rabbia si carica anche attaccando); *Ultimo respiro* (sotto una soglia critica di HP ottiene una breve protezione); *Assalto scomposto* (Turbine colpisce un bersaglio in più, ma riduce la difesa più a lungo).

### Bardo

- **Attacco base — Nota tagliente:** onda sonora a distanza che danneggia e applica una breve dissonanza.
- **Abilità spam — Ritornello:** suona una frase che potenzia temporaneamente l'attacco dell'alleato che ha agito più di recente.
- **Ultimate — Ballata dell'orda:** concede a tutto il party velocità d'attacco e resistenza agli effetti per una breve durata.
- **Passiva — Tempo condiviso:** quando un alleato usa un'abilità, il Bardo accumula ritmo; a soglia, il prossimo Ritornello è più efficace.
- **Tratti sbloccabili:** *Eco* (Ritornello raggiunge un secondo alleato); *Accordo minore* (Nota tagliente indebolisce anche l'attacco del bersaglio); *Finale improvvisato* (Ballata prolunga la propria durata se un alleato è in difficoltà).

### Chierico

- **Attacco base — Fiamma sacra:** proiettile luminoso a distanza, con priorità ai nemici che stanno attaccando un alleato ferito.
- **Abilità spam — Cura:** ripristina HP all'alleato con meno salute percentuale.
- **Ultimate — Rianimazione:** riporta in battaglia un alleato sconfitto con una parte degli HP; cooldown molto lungo.
- **Passiva — Voto di custodia:** la prima volta che un alleato scende sotto una soglia di HP, riceve una piccola barriera.
- **Tratti sbloccabili:** *Mano ferma* (Cura rimuove un effetto negativo semplice); *Ultima preghiera* (Rianimazione concede anche una barriera breve); *Luce riflessa* (una parte della Cura guarisce anche il Chierico).

### Druido

- **Attacco base — Spina viva:** lancia una spina vegetale; il bersaglio subisce danni nel tempo.
- **Abilità spam — Radici avvolgenti:** immobilizza brevemente il nemico più avanzato e ne riduce la velocità d'attacco.
- **Ultimate — Eclissi di rovi:** copre l'arena di rampicanti che danneggiano e rallentano i nemici; i nemici sconfitti sotto l'effetto fanno germogliare una piccola cura per il party.
- **Passiva — Ciclo naturale:** quando un nemico affetto da danno nel tempo viene sconfitto, il Druido recupera una piccola quantità di HP.
- **Tratti sbloccabili:** *Semi erranti* (Spina viva può diffondere il danno a un secondo nemico); *Corteccia quieta* (il Druido riceve meno danni mentre non è bersaglio); *Germoglio resiliente* (Eclissi di rovi cura di più se il party è ferito).

### Guerriero

- **Attacco base — Colpo d'arma:** attacco ravvicinato stabile contro il nemico più vicino.
- **Abilità spam — Provocazione:** attira per breve tempo gli attacchi nemici sul Guerriero.
- **Ultimate — Muro di scudi:** protegge il Guerriero e gli alleati in prima linea, riducendo i danni ricevuti per una durata breve.
- **Passiva — Guardia disciplinata:** il Guerriero riduce una parte del danno diretto agli alleati adiacenti.
- **Tratti sbloccabili:** *Scudo alto* (la Guardia protegge anche un alleato in seconda linea, con efficacia ridotta); *Risposta addestrata* (dopo aver bloccato un colpo, il prossimo attacco base è potenziato); *Linea salda* (Muro di scudi migliora se il party mantiene la formazione).

### Ladro

- **Attacco base — Stoccata:** colpisce il nemico con meno HP fra quelli raggiungibili; infligge danno bonus se il bersaglio è già ferito.
- **Abilità spam — Veleno rapido:** applica un veleno a danno progressivo al bersaglio più vulnerabile.
- **Ultimate — Colpo alle spalle:** teletrasporto breve dietro il nemico più ferito e attacco ad alto danno, ignorando parte della difesa.
- **Passiva — Opportunista:** ottiene un bonus temporaneo quando un alleato colpisce un nemico già ferito.
- **Tratti sbloccabili:** *Veleno persistente* (il veleno dura più a lungo); *Fuga calcolata* (la prima volta che scende a pochi HP, schiva un attacco); *Bottino sporco* (Colpo alle spalle aumenta la probabilità di trovare tesoro dopo l'incontro).

### Mago

- **Attacco base — Dardo arcano:** proiettile magico affidabile contro il nemico più vicino.
- **Abilità spam — Scheggia elementale:** lancia automaticamente l'elemento più adatto fra fuoco (danno nel tempo), gelo (rallenta) e fulmine (colpisce un secondo bersaglio).
- **Ultimate — Cataclisma:** evoca una grande esplosione ad area al centro dei nemici.
- **Passiva — Studio preparatorio:** all'inizio della battaglia il Mago osserva la formazione nemica e potenzia il primo uso di Scheggia elementale contro la categoria più numerosa.
- **Tratti sbloccabili:** *Formula efficiente* (Scheggia elementale ha cooldown leggermente ridotto); *Contraccolpo arcano* (subire un colpo accelera il prossimo incantesimo); *Geometria perfetta* (Cataclisma infligge meno danno ma copre un'area più ampia).

### Monaco

- **Attacco base — Pugno ritmico:** sequenza di colpi rapidi; l'ultimo colpo interrompe brevemente il bersaglio.
- **Abilità spam — Passo leggero:** evita il prossimo attacco diretto e si riposiziona vicino a un nemico vulnerabile.
- **Ultimate — Mille colpi:** scarica una raffica sul nemico più pericoloso; ogni colpo successivo infligge meno danno.
- **Passiva — Disciplina del respiro:** alternare attacchi e Passo leggero accumula concentrazione, che aumenta la schivata.
- **Tratti sbloccabili:** *Palmo deviato* (la schivata riduce anche il danno del prossimo colpo); *Respiro profondo* (la concentrazione non si azzera del tutto se il Monaco viene colpito); *Punto di pressione* (l'ultimo colpo della raffica riduce la difesa).

### Paladino

- **Attacco base — Lama consacrata:** colpo ravvicinato che infligge danno sacro aggiuntivo ai nemici élite.
- **Abilità spam — Giuramento protettivo:** assegna una barriera all'alleato più esposto.
- **Ultimate — Giudizio solare:** danneggia i nemici e cura lievemente gli alleati; l'effetto è più forte se il party ha subito molti danni.
- **Passiva — Aura del giuramento:** gli alleati vicini al Paladino ricevono una piccola riduzione dei danni.
- **Tratti sbloccabili:** *Giuramento severo* (la barriera riflette una parte minima del danno); *Voto di misericordia* (Giudizio cura di più ma infligge meno danno); *Presenza radiosa* (l'aura raggiunge una posizione aggiuntiva).

### Ranger

- **Attacco base — Freccia precisa:** colpisce a distanza il nemico più lontano, con danno bonus se non è protetto dalla prima linea.
- **Abilità spam — Tiro segnato:** marca un bersaglio; gli attacchi degli alleati contro di lui sono più efficaci per breve tempo.
- **Ultimate — Pioggia di frecce:** bersaglia una zona e colpisce più nemici, con priorità ai marcati.
- **Passiva — Occhio del cacciatore:** il Ranger individua automaticamente nemici con debolezze o poca salute e ne aumenta la priorità.
- **Tratti sbloccabili:** *Frecce gemelle* (Tiro segnato danneggia anche un bersaglio vicino); *Passo del vento* (bonus se schierato in retroguardia); *Preda costante* (la marca dura più a lungo se l'alleato marcato sopravvive).

### Stregone

- **Attacco base — Scarica innata:** impulso magico spontaneo; ogni attacco può cambiare leggermente elemento.
- **Abilità spam — Fiammata erratica:** esplosione automatica su un bersaglio casuale fra i nemici, con un effetto secondario variabile ma leggibile.
- **Ultimate — Eruzione del sangue:** libera tutta la magia accumulata in un potente attacco ad area; lo Stregone perde temporaneamente difesa.
- **Passiva — Magia incanalata:** gli attacchi base accumulano energia; l'energia aumenta la potenza dell'ultimate ma si disperde se lo Stregone viene stordito.
- **Tratti sbloccabili:** *Sangue elementale* (l'elemento è determinato dalla specie del bersaglio); *Riflesso caotico* (Fiammata può rimbalzare su un altro nemico); *Riserva vitale* (l'ultimate consuma meno HP/difesa, ma carica più lentamente).

## Classi Avanzate

### Alchimista

- **Attacco base — Fiala corrosiva:** lancia un composto che riduce gradualmente la difesa del nemico.
- **Abilità spam — Miscela instabile:** applica automaticamente l'effetto più utile fra cura lieve al party, corrosione o rallentamento, in base allo stato dello scontro.
- **Ultimate — Grande reazione:** combina gli effetti già presenti sui nemici in un'esplosione; più effetti diversi sono attivi, più l'esplosione è efficace.
- **Passiva — Distillazione:** ogni effetto di stato applicato dall'Alchimista gli fornisce una carica di reagente.
- **Tratti sbloccabili:** *Fiala di riserva* (inizia ogni battaglia con una carica); *Catalizzatore* (Grande reazione consuma meno effetti ma colpisce più forte); *Rimedio amaro* (la cura lieve rimuove anche un danno nel tempo).

### Cavaliere

- **Attacco base — Affondo in sella:** carica il bersaglio più lontano e lo spinge verso la retroguardia.
- **Abilità spam — Sfida:** dichiara come rivale il nemico più resistente; entrambi infliggono più danno l'uno all'altro e il Cavaliere protegge gli alleati vicini dagli altri nemici.
- **Ultimate — Carica della lancia:** attraversa la linea nemica in un assalto che danneggia e disordina più bersagli.
- **Passiva — Impeto:** muoversi senza essere immobilizzato accumula slancio, che potenzia l'affondo successivo.
- **Tratti sbloccabili:** *Staffa salda* (meno vulnerabile dopo la carica); *Duello d'onore* (Sfida riduce anche l'attacco del rivale contro gli alleati); *Lancia penetrante* (la carica attraversa meglio le protezioni).

### Convocatore

- **Attacco base — Comando del vincolo:** invia il proprio spirito evocato ad attaccare il bersaglio selezionato automaticamente.
- **Abilità spam — Evocazione minore:** evoca un servitore temporaneo che assorbe un colpo o infligge danno modesto.
- **Ultimate — Manifestazione maggiore:** evoca una creatura potente per un tempo limitato; assume automaticamente il ruolo più necessario fra protezione e attacco.
- **Passiva — Patto condiviso:** una parte dei danni subiti dal Convocatore viene trasferita al servitore presente, fino alla sua scomparsa.
- **Tratti sbloccabili:** *Vincolo stabile* (il servitore dura più a lungo); *Doppio sigillo* (Evocazione minore può creare un secondo servitore fragile); *Offerta d'essenza* (la Manifestazione è più forte se il Convocatore è ferito).

### Fattucchiere

- **Attacco base — Dardo del malocchio:** maledice il nemico con meno debuff, causando danno lieve e rendendolo più vulnerabile.
- **Abilità spam — Sventura:** trasferisce un effetto positivo dal nemico più potenziato a un alleato casuale.
- **Ultimate — Patto infranto:** esplode tutte le maledizioni attive sui nemici e le converte in danni.
- **Passiva — Famiglio inquieto:** un famiglio sceglie automaticamente il bersaglio più maledetto e ne prolunga un debuff.
- **Tratti sbloccabili:** *Malocchio insistente* (il dardo si propaga se il bersaglio muore); *Debito oscuro* (Sventura cura lievemente il Fattucchiere); *Patto crudele* (Patto infranto infligge di più ma riduce la difesa del Fattucchiere).

### Inquisitore

- **Attacco base — Colpo inquisitorio:** attacco rapido che infligge danno bonus ai nemici che usano potenziamenti.
- **Abilità spam — Interrogatorio:** marchia il nemico più pericoloso e ne rivela le protezioni, riducendone temporaneamente la difesa.
- **Ultimate — Sentenza:** colpisce il bersaglio marchiato; se è già ferito o potenziato, interrompe anche la sua abilità in corso.
- **Passiva — Nessun segreto:** gli effetti di cura o protezione nemici sono meno efficaci finché l'Inquisitore è vivo.
- **Tratti sbloccabili:** *Domande serrate* (Interrogatorio riduce anche la velocità d'attacco); *Sentenza esemplare* (sconfiggere il marchiato potenzia il party); *Occhio alla menzogna* (priorità automatica ai nemici che curano).

### Magus

- **Attacco base — Lama incantata:** colpo ravvicinato seguito da una scintilla magica a distanza breve.
- **Abilità spam — Incanta lama:** il prossimo attacco base rilascia un effetto elementale scelto automaticamente in base alle resistenze nemiche.
- **Ultimate — Varco tagliente:** fendenti attraversano un varco e colpiscono in linea il nemico arretrato e quelli allineati.
- **Passiva — Spellstrike:** lanciare Incanta lama rende il Magus più resistente fino al colpo potenziato.
- **Tratti sbloccabili:** *Lama risonante* (l'effetto elementale si propaga a un vicino); *Parata arcana* (Spellstrike riduce il prossimo danno magico ricevuto); *Varco instabile* (Varco tagliente colpisce più bersagli ma con danno ridotto).

### Morfico

- **Attacco base — Arto adattivo:** attacca con l'arto più adatto alla distanza: artiglio in mischia o spina a distanza.
- **Abilità spam — Mutazione reattiva:** cambia forma automaticamente in base alla minaccia prevalente: corazza contro danni fisici, membrane contro magia o artigli contro nemici protetti.
- **Ultimate — Forma perfetta:** assume per breve tempo la forma che contrasta meglio il nemico più pericoloso, ottenendo un attacco e una difesa specializzati.
- **Passiva — Corpo mutevole:** la prima volta che subisce un tipo di danno, acquisisce una piccola resistenza temporanea a quel tipo.
- **Tratti sbloccabili:** *Adattamento rapido* (la resistenza si attiva prima); *Forma ibrida* (mantiene parte del beneficio della forma precedente); *Riflesso predatorio* (Arto adattivo dà priorità ai nemici contro cui è più efficace).

### Oracolo

- **Attacco base — Presagio:** infligge danno magico al nemico che, secondo una previsione, agirà per primo.
- **Abilità spam — Filo del fato:** concede a un alleato una probabilità di evitare il prossimo colpo e predice l'attacco nemico imminente.
- **Ultimate — Esito inevitabile:** marca il nemico più pericoloso; dopo un breve ritardo subisce danni in base agli attacchi ricevuti nel frattempo.
- **Passiva — Visione anticipata:** all'inizio dello scontro l'Oracolo individua la prima abilità nemica e ne riduce l'efficacia.
- **Tratti sbloccabili:** *Presagio favorevole* (Filo del fato aumenta anche la precisione); *Futuro condiviso* (la previsione protegge due alleati adiacenti); *Profezia compiuta* (Esito inevitabile accelera se il bersaglio è stato colpito da più alleati).

### Pistolero

- **Attacco base — Colpo di pistola:** sparo preciso a distanza; dopo alcuni colpi deve ricaricare automaticamente.
- **Abilità spam — Tiro di risposta:** spara al nemico che ha appena colpito un alleato, con priorità a chi sta attaccando la retroguardia.
- **Ultimate — Scarica a ventaglio:** svuota il caricatore contro più nemici in ordine di distanza.
- **Passiva — Mano veloce:** ogni colpo andato a segno riduce leggermente il tempo di ricarica; i colpi mancati non danno carica.
- **Tratti sbloccabili:** *Proiettile ricochet* (l'ultimo colpo rimbalza su un secondo nemico); *Ricarica tattica* (ricarica più rapidamente se un alleato è in pericolo); *Polvere nera* (Scarica a ventaglio lascia un breve debuff di precisione).

## Classi Alternative

### Antipaladino

- **Attacco base — Lama empia:** colpo ravvicinato che assorbe una piccola quantità di salute dal bersaglio.
- **Abilità spam — Aura di terrore:** indebolisce l'attacco dei nemici più vicini.
- **Ultimate — Anatema:** maledice il nemico più forte; una parte della cura e delle protezioni ricevute viene convertita in danno.
- **Passiva — Potere dal dolore:** recupera vigore quando un alleato o l'Antipaladino subisce danni.
- **Tratti sbloccabili:** *Aura famelica* (il terrore riduce anche la difesa); *Giuramento profano* (Lama empia guarisce di più se il bersaglio è maledetto); *Anatema persistente* (la maledizione rimane brevemente dopo la morte del bersaglio).

### Ninja

- **Attacco base — Kunai d'ombra:** lancia un kunai a distanza; se il bersaglio è già stato colpito, applica un taglio sanguinante astratto.
- **Abilità spam — Sostituzione:** evita il prossimo attacco diretto e lascia un'esca che attira per breve tempo un nemico.
- **Ultimate — Catena silenziosa:** colpisce in rapida successione i nemici più feriti, muovendosi fra le linee.
- **Passiva — Non visto:** il Ninja non è il bersaglio prioritario finché non usa la sua ultimate o resta l'unico combattente.
- **Tratti sbloccabili:** *Fumo residuo* (l'esca riduce anche la precisione); *Marchio segreto* (Kunai rende il bersaglio vulnerabile agli attacchi alleati); *Catena perfetta* (ogni eliminazione accelera il colpo successivo).

### Samurai

- **Attacco base — Iai:** attende un breve istante e colpisce con un fendente preciso; il danno aumenta se non è stato interrotto.
- **Abilità spam — Guardia del duello:** assume una guardia che riduce il prossimo danno e contrattacca automaticamente.
- **Ultimate — Taglio del crepuscolo:** un fendente ad altissima precisione contro il nemico più pericoloso, ignorando parte della difesa.
- **Passiva — Risolutezza:** non perde la propria azione quando viene colpito durante la preparazione di un attacco.
- **Tratti sbloccabili:** *Pazienza* (Iai infligge più danno se il bersaglio è marcato); *Contrattacco netto* (Guardia del duello può stordire); *Ultimo onore* (a pochi HP, il Samurai non può essere interrotto).

## Classi Ibride

### Arcanista

- **Attacco base — Dardo modulato:** attacco magico che alterna automaticamente modalità d'attacco e di supporto.
- **Abilità spam — Riserva arcana:** accumula energia quando il party subisce o infligge magia; la spende per potenziare il prossimo incantesimo alleato.
- **Ultimate — Formula suprema:** rilascia tutta la riserva in un effetto adattivo: danno ad area se i nemici prevalgono, barriera se il party è in pericolo.
- **Passiva — Equilibrio delle formule:** l'Arcanista guadagna riserva usando effetti diversi, ma non ripetendo sempre lo stesso.
- **Tratti sbloccabili:** *Riserva capiente* (aumenta il massimo accumulabile); *Formula di rimbalzo* (il potenziamento arcano passa a un secondo alleato); *Sintassi perfetta* (Formula suprema costa meno energia se il party è bilanciato).

### Brawler

- **Attacco base — Gancio brutale:** colpo ravvicinato che spinge il nemico e può interromperne l'attacco.
- **Abilità spam — Presa e lancio:** afferra il nemico più vicino e lo scaraventa contro un altro bersaglio, se presente.
- **Ultimate — Rissa totale:** attacca ripetutamente i nemici vicini; ogni colpo cambia bersaglio e applica un breve sbilanciamento.
- **Passiva — Rissa di strada:** infliggere o ricevere colpi ravvicinati aumenta temporaneamente la resistenza agli stordimenti.
- **Tratti sbloccabili:** *Muro umano* (il nemico lanciato urta anche la prima linea); *Gomiti alti* (Gancio interrompe più facilmente); *Rissa contagiosa* (Rissa totale dà un breve bonus agli alleati adiacenti).

### Cacciatore

- **Attacco base — Dardo da caccia:** colpisce il nemico più lontano e applica un segno di tracciamento.
- **Abilità spam — Trappola preparata:** piazza automaticamente una trappola sul percorso del nemico più avanzato; lo rallenta o lo immobilizza quando la raggiunge.
- **Ultimate — Preda abbattuta:** il Cacciatore e il suo compagno animale concentrano gli attacchi sul bersaglio tracciato; se il bersaglio cade, passano al successivo.
- **Passiva — Compagno fedele:** un animale ferma o disturba il primo nemico che raggiunge la retroguardia.
- **Tratti sbloccabili:** *Trappola dentata* (la trappola infligge anche danno); *Fiuto infallibile* (il segno dura più a lungo); *Compagno guardiano* (l'animale protegge un alleato ferito invece di inseguire).

### Scaldo

- **Attacco base — Corno di guerra:** attacco sonoro che danneggia i nemici e rafforza lievemente il prossimo attacco alleato.
- **Abilità spam — Ritmo di battaglia:** ogni alleato che attacca durante il ritmo accumula impeto; al termine, gli impeti diventano danno bonus sul prossimo colpo.
- **Ultimate — Saga dell'ultima carica:** gli alleati avanzano e attaccano in sequenza; chi è in prima linea protegge chi deve ancora agire.
- **Passiva — Gloria condivisa:** quando un alleato sconfigge un nemico, lo Scaldo accumula gloria che potenzia il prossimo Ritmo di battaglia.
- **Tratti sbloccabili:** *Coro d'acciaio* (Ritmo aumenta anche la difesa); *Saga più lunga* (l'ultimate dà un piccolo bonus anche dopo la sequenza); *Eroe celebrato* (Gloria si accumula anche quando un alleato sopravvive a un colpo letale grazie a una barriera).

### Sciamano

- **Attacco base — Spirito guida:** invia uno spirito contro un nemico; il tipo di spirito cambia fra fuoco, acqua e vento.
- **Abilità spam — Totem ancestrale:** evoca un totem temporaneo che cura, protegge o danneggia in base al bisogno più urgente del party.
- **Ultimate — Assemblea degli spiriti:** tutti gli spiriti disponibili si manifestano insieme, curando gli alleati e colpendo i nemici secondo la loro affinità.
- **Passiva — Legame spirituale:** gli effetti dello Sciamano cambiano con il totem attivo; alleati vicini ricevono una parte dell'effetto spirituale.
- **Tratti sbloccabili:** *Spirito persistente* (Totem dura più a lungo); *Affinità scelta* (il tipo di spirito reagisce alla specie nemica); *Voce degli antenati* (Assemblea rianima un alleato con pochissimi HP, ma ha cooldown maggiore).

## Indicazioni per prototipazione e bilanciamento

### Classi consigliate per il primo prototipo

Per validare ruoli, targeting, cooldown e posizionamento senza produrre subito trenta set completi:

1. **Guerriero:** difesa e controllo della prima linea.
2. **Barbaro:** danno da mischia e rischio legato alla difesa.
3. **Chierico:** cura e rianimazione automatica.
4. **Stregone:** danno magico ad area e gestione di una risorsa.
5. **Bardo** oppure **Ranger:** supporto di squadra o pressione sulla retroguardia, a seconda della varietà che manca ai test.

Le altre classi sono una libreria di design per futuri sblocchi e atti; non sono una promessa che debbano essere tutte implementate per l'Accesso Anticipato.

### Regole di tuning da provare

- Le abilità frequenti devono creare la rotazione riconoscibile della classe; le ultimate dovrebbero accadere poche volte in uno scontro normale.
- La Resurrection del Chierico e la resurrezione eventuale dello Sciamano vanno testate con molta cautela: la seconda opzione può essere rimossa o trasformata in protezione se annulla il costo delle sconfitte.
- Controllo, stordimenti, provocazione, trappole e immobilizzazioni devono avere durate brevi e rendimenti decrescenti contro i boss.
- Cura, scudi e mitigazione devono competere con il danno: evitare composizioni che rendono il party praticamente immortale.
- Le classi che evocano, hanno famigli o creano totem devono avere un limite di entità attive e feedback visivo chiaro, così la battaglia resta leggibile.
- Le posizioni di classe devono offrire vantaggi e compromessi, non diventare requisiti obbligatori per usare un job.
