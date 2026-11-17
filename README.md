# contabilita-terzo-settore

Una skill per [Claude](https://claude.ai) che tiene e controlla i conti di una piccola associazione italiana: un gruppo informale, un gruppo ospitato da un'altra associazione, un'associazione di promozione sociale (APS) o un altro ente del Terzo settore che fa il rendiconto per cassa. È pensata per chi i conti li tiene da volontario, cioè un tesoriere, un presidente o un socio, e li vuole precisi e leggibili da tutti senza comprare un programma di contabilità.

Una skill è un file di istruzioni che Claude legge quando gli si chiede qualcosa su un certo argomento. Questa gli insegna un metodo per registrare i movimenti, le voci del rendiconto ministeriale e le regole che un ente del Terzo settore deve rispettare.

## Avvertenza: nessuna garanzia e nessuna responsabilità

Questa skill è un aiuto per tenere in ordine i conti. Non è una consulenza contabile, fiscale o legale e non sostituisce un commercialista o un centro di servizio per il volontariato.

L'hanno scritta dei volontari, che non sono commercialisti né avvocati, con l'aiuto di Claude. Le norme sono state lette sulle fonti ufficiali alla data indicata più sotto, ma possono essere state capite male, essere cambiate nel frattempo o non adattarsi al vostro caso; Claude, inoltre, può sbagliare un conto o una regola anche quando la skill è giusta.

Gli autori non garantiscono che la skill sia corretta, completa o aggiornata e, nei limiti consentiti dalla legge, non si assumono alcuna responsabilità per errori, omissioni, sanzioni, scadenze mancate, contributi persi o altri danni che derivino dal suo uso. Chi la usa lo fa a proprio rischio: prima di depositare un rendiconto, di promettere a un donatore un beneficio fiscale o di prendere una decisione che conta, verificate sulle fonti ufficiali e chiedete a un professionista.

## Che cosa fa

- **Registra.** Dalla foto di uno scontrino, da un messaggio o da un estratto prepara la riga pronta da copiare nel registro, con il conto da cui partono i soldi, quello a cui arrivano, la voce e il progetto, e segnala ciò che manca.
- **Controlla.** Passa il registro con dieci controlli: saldi contro contanti ed estratti, doppioni, numeri saltati, cassa sotto zero, spese senza documento o senza autorizzazione, rimborsi più alti degli anticipi, spese di un bando fuori periodo.
- **Riconcilia.** Confronta il registro con l'estratto della banca, di una piattaforma di donazioni o dell'ente che tiene i soldi per conto del gruppo, e spiega ogni differenza.
- **Riepiloga e rendiconta.** Scrive il riepilogo per i soci, calcola i «soldi liberi» (ciò che resta tolti i debiti, le spese approvate e i fondi vincolati) e prepara il rendiconto di un progetto finanziato, quello di una raccolta fondi occasionale sullo schema ministeriale e il rendiconto annuale per cassa (modello D o modello E).
- **Ricorda regole e scadenze** di un ente del Terzo settore: deposito al RUNTS (il Registro unico nazionale del Terzo settore), libri sociali, volontari, raccolte fondi, benefici fiscali per chi dona, soglie.

La skill non decide le spese e non scrive nel registro al posto del tesoriere, a meno che non glielo si chieda. Non tratta IVA, lavoro dipendente, dichiarazioni dei redditi, associazioni non iscritte al RUNTS e bilancio per competenza: per questi rimanda al commercialista.

## Come ragiona

**Ogni movimento va da un conto a un altro.** I conti sono di tre tipi: i contenitori dove stanno davvero i soldi (cassa, banca, piattaforme, soldi tenuti da un altro ente), i conti con le persone (ciò che l'ente deve ai soci che hanno anticipato una spesa) e «Fuori», cioè il resto del mondo. Scrivendo da dove partono i soldi e dove arrivano, un versamento in banca non viene scambiato per una spesa e un rimborso non viene contato due volte.

| Da | A | Che cos'è |
|---|---|---|
| Fuori | un contenitore | entrata |
| un contenitore | Fuori | uscita |
| un contenitore | un altro contenitore | spostamento |
| Da restituire ai soci | Fuori | spesa anticipata da un socio |
| un contenitore | Da restituire ai soci | rimborso al socio |

**Le categorie hanno i nomi del rendiconto ministeriale.** Ogni entrata e ogni uscita prende una voce del modello D (decreto del 5 marzo 2020), con un codice breve come `A.E4` per le erogazioni liberali o `A.U2` per i servizi, così che il rendiconto di fine anno diventa una somma. Un gruppo che oggi non ha obblighi tiene già i conti nella forma che gli servirà da APS.

**Si accende solo ciò che serve.** La skill distingue cinque fasi, dal gruppo informale all'ente che supera le soglie del rendiconto per cassa, e a ciascuna propone soltanto i suoi conti e i suoi adempimenti.

## Come si installa

**Nell'app o sul sito di Claude**, anche con il piano gratuito: scaricate [`contabilita-terzo-settore.zip`](contabilita-terzo-settore.zip), aprite le impostazioni di Claude alla voce delle skill (in inglese *Customize › Skills*), caricate il file e attivate la skill. Deve essere attiva l'esecuzione di codice (*code execution*). La skill resta privata nel vostro account. Queste indicazioni vengono dalla guida ufficiale di Claude letta il 16/11/2026, e i nomi dei menu possono cambiare.

**In Claude Code:** copiate la cartella `contabilita-terzo-settore/` in `~/.claude/skills/`.

## Come si usa

La prima volta la skill fa sei domande sull'ente (che cos'è, dove tiene i soldi, chi autorizza le spese, dove sta il registro, quali progetti ha, quando chiude l'anno) e scrive la **scheda contabile**, una pagina con i fatti del vostro ente. Salvatela accanto al registro e datela a Claude ogni volta, caricandola nella chat o tenendola in un progetto, perché le regole di legge stanno nella skill mentre i nomi dei vostri conti stanno lì.

Il registro è un foglio qualsiasi (Excel, Fogli Google, LibreOffice) con una riga per movimento. In [`esempi/`](esempi/) trovate una scheda compilata e un piccolo registro da cui partire.

Poi si chiede in italiano, per esempio:

- «Ti mando la foto di uno scontrino: preparami la riga per il registro.»
- «Controlla il registro e dimmi che cosa non torna.»
- «Confronta il registro con questo estratto conto.»
- «Quanti soldi liberi abbiamo?»
- «Prepara il rendiconto della cena di raccolta fondi.»
- «Prepara il rendiconto per cassa del 2027 da portare in assemblea.»

## Come è stata provata

La skill è stata provata su quattro casi inventati, i cui risultati attesi sono stati calcolati a parte, con un programma indipendente, prima di guardare le risposte. I casi stanno in [`contabilita-terzo-settore/evals/`](contabilita-terzo-settore/evals/), ciascuno con la richiesta, i file di ingresso e l'elenco dei punti da verificare.

| Caso | Che cosa mette alla prova | Punti verificati |
|---|---|---|
| `rendiconto-annuale-aps` | rendiconto per cassa di una APS con anticipi dei soci, un contributo vincolato, un bene durevole e una spesa solo approvata | 10 su 10 |
| `registrare-da-messaggio` | quattro righe ricavate dal messaggio frettoloso del tesoriere di un gruppo ospitato | 7 su 7 |
| `riconciliare-e-volantino` | differenza fra il registro e il riepilogo dell'ente ospitante, e una promessa sbagliata su un volantino | 7 su 7 |
| `controllare-registro-con-errori` | registro con quattordici errori nascosti, rendiconto di una raccolta fondi, rimborsi fissi ai volontari | 18 su 18 |

Nel quarto caso la stessa richiesta è stata data a Claude anche senza la skill, e il risultato è stato di 16 punti su 18. Gli è mancato lo schema ministeriale del rendiconto della raccolta, in cui i beni ricevuti in dono compaiono al valore di mercato, e sul bene durevole si è fermato a un dubbio, senza la soglia e senza l'elenco dei beni. In un controllo di questo tipo, quindi, Claude trova da solo quasi tutti gli errori, e la skill aggiunge soprattutto la forma che le norme richiedono.

Queste prove hanno limiti che è giusto conoscere. Ogni caso è girato una volta sola, con modelli Claude di fascia media e, per il secondo, piccola. Il confronto con i punti attesi è stato fatto a mano da chi ha scritto la skill. I primi tre casi sono girati sulla prima stesura e il quarto sulla seconda; le precisazioni aggiunte dopo ciascun giro non sono state riprovate, e il confronto senza skill esiste solo per il quarto caso. Quattro casi dicono che la skill funziona su questi esempi, non che sia priva di errori.

Chi ha Claude Code (dalla versione 2.1.269) può rifare le prove dalla cartella della skill con `claude plugin eval . --allow-tools Write,Edit,Bash --scaffold`. Sono esecuzioni vere del modello, quindi consumano il proprio piano.

## Norme e fonti

Le norme sono state lette il 16/11/2026 sul testo ufficiale:

- Codice del Terzo settore, decreto legislativo 117/2017, nel [testo vigente su Normattiva](https://www.normattiva.it/uri-res/N2Ls?urn:nir:stato:decreto.legislativo:2017-07-03;117!vig=);
- decreto del Ministro del Lavoro del 5 marzo 2020 con i modelli di bilancio e il modello D ([Gazzetta Ufficiale n. 102 del 18/04/2020](https://www.gazzettaufficiale.it/eli/id/2020/04/18/20A02158/sg));
- decreto del 18 febbraio 2026 sul modello E, attraverso la [circolare ministeriale n. 6 del 17/04/2026](https://lavoro.gov.it/notizie/pagine/codice-del-terzo-settore-chiarimenti-utilizzo-del-rendiconto);
- decreto del 19 maggio 2021, n. 107, sulle attività diverse ([Gazzetta Ufficiale](https://www.gazzettaufficiale.it/eli/id/2021/07/26/21G00115/sg));
- [linee guida sulla raccolta fondi](https://www.lavoro.gov.it/notizie/Documents/Linee-guida-raccolta-fondi-ETS.pdf), decreto del 9 giugno 2022.

Alcune regole vengono invece da guide e vanno ricontrollate prima di farci affidamento: la soglia di 516 € per i beni durevoli, la conservazione dei documenti per dieci anni, la pubblicazione dei contributi pubblici (legge 124/2017), le regole del 5 per mille, la quota associativa che non dà detrazione, il contenuto consigliato della ricevuta di donazione e la voce in cui mettere le commissioni di pagamento.

La skill chiede a Claude di ricontrollare soglie e termini quando è passato più di un anno dalla data di verifica o quando prepara un documento da depositare.

## Segnalare un errore

Se trovate una regola sbagliata o superata, aprite una segnalazione (*issue*) in questo repository indicando la norma e la fonte.

## Licenza

Licenza MIT: chiunque può usare, copiare e modificare la skill, che è fornita così com'è e senza garanzie. Il testo è in [LICENSE](LICENSE).

## In English

A Claude skill for the bookkeeping of small Italian non-profits (informal groups, APS and other *enti del Terzo settore* that report on a cash basis): "from → to" movements between accounts, categories mapped to the official *modello D*, checks, reconciliations, fund-raising and annual cash statements, RUNTS deadlines. The skill is written in Italian. It is provided as is, with no warranty, and is not accounting, tax or legal advice.
