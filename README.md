# FiPay
:-) Counterparty based epayment

FiPay:

Il cliente scarica l’applicazione, fino a quando non si registra e non e’ approvato (aml kyc), l’applicazione e’ bloccata.

Una volta sbloccata puoi iniziare a comprare token spendibili, per comprare token fai un bonifico all’iban che ti viene comunicato dall’app (o si puo implementare qualsiasi altro metodo di pagamento). Se mandi 10 euro ricevi 10 euro_token un gettone counterparty (sistema basato sulla blockchain bitcoin quindi sicurissimo) che conserva il cambio 1:1 con euro. Tutti le persone che hanno un app sbloccata(si sono registrati) potranno ricevere questi token.

Chi vuole convertire i propri token in euro fa una richiesta al nostro server dove comunica l’iban sul quale vuole ricevere il pagamento (o qualsiasi altro sistema), se l’iban e’ nel nostro archivio di iban validi (AML KYC) il server da il via libera a quel punto il cliente bruciera’ i propri token (li inviera’ ad un indirizzo di cui nessuno conosce il privat key) e il server eseguira’ un bonifico verso il cliente per un totale di euro pari al numero di token bruciati meno l’uno %.

Le applicazioni dei venditori avranno un sistema che ogni x euro eseguono un ordine di ritiro automatico.

VANTAGGI:
Sicurezza: ogni scambio avviene nello stesso modo in cui avviene una transazione bitcoin il sistema di pagamento piu sicuro al modo.

Facilita’ di gestione: la societa’ deve solo pensare ad autenticare i clienti per essere compliance con AML KYC, tutta la parte realativa a lo scambio effettivo dei token tra i clienti e’  eseguita dalla blockchain.

Interoperabilita’: dato che il sistema utilizza la blockchain e il protocollo standard di
trasfertimento e’ molto semplice integrare altre applicazioni o altri sistemi di
pagamento.

	Scalabilita’: la gestione dei pagamenti tra clienti (la parte che richiede piu’ risorse) e’
	completamente distribuita e viene eseguita dai nodi del network.

	Costi contenuti: le fee su una transazioni bitcoin sono bassissime (siamo sui 2 cent di
	euro) per pagamenti inferiori all’euro dove due cent iniziano ad essere tanti si puo’ 
	fare una promessa di pagamento non molto sicura, ma per pagamenti piccoli il gioco
	vale la candela.

	Facilmente auditabile: tutte le applicazioni basate su blockchain si basano su un
	protocollo pubblica ed estremamente auditabile.


SVANTAGGI:
	Altamente innovativo: ancora poche societa’ utilizzano un sistema di questo tipo.


Parti:

Cold wallet: sistema multichiave per la gestione(creazione) dei token.

Hot wallet: servizio di rete con una quantita’ di token appena sufficiente per soddisfare il 
flusso di nuove sottoscrizioni e depositi.

Client: applicazione per mobile, client counterparty costumizzato con logo e regole della 
	societa’, che permette una gestione completamente trasparente per il cliente dei
	propri token (al cliente sembrera’ sempre di usare euro e non token)

Database utenti: servizio di rete che permette di regitrare e gestire gli utenti, archivia e
	rende disponibili i dati degli utenti: nome indirizzo, …, iban1, iban2, ...

Collegamento con il conto: servizio di rete che attarverso le api della banca gestisce i bonifici 
in entrata ed in uscita. (dice quando sono arrivati i soldi e crea i bonifici quando viene
richiesto dal client se l’iban e’ nel db utenti e il client ha bruciato i suoi token)
