## Protocolli ad accesso multiplo  
Sono protocolli in cui vi e' competizione per le risorse, in soldoni, vi e' un unico canale condiviso da molti. I protocolli per assegnare l'uso di un canale multiaccesso appartengono a un sottostrato dello strato collegamento dati, chiamato **MAC** (*Medium Access Control* ). I sistemi a competizione sono utili quando il traffico sulla rete e' irregolare ( praticamente sempre ), se ad esempio utilizzassimo FDM (o TDM) per la trasmissione sullo stesso canale di piu' utenti, presupponendo di aver diviso lo spettro in N regioni, nel caso ci fossero meno di N utenti a trasmettere stiamo sprecando banda, nel caso ci fosser piu' di N utenti a trasmettere allora parte di essi non sarebbero in grado di trasmettere.  
**Premesse**:  
1. Modello della stazione => vi sono N stazioni indipendenti, quando una stazione ha generato un frame, essa non fa nulla fino a che il frame e' stato spedito con successo.  
1. Presupposto del canale => Un solo canale viene utilizzato per tutte le trasmissioni.  
1. Presupposto della collisione => se due frame si sovrappingono ( anche parzialmente ) entrambi i fram sono distrutti.  
1. Tempo continuo => non vi e' un orologio centralizzato che scandisce i tempi per la trasmissione, chiunque puo' rasmettere appena ha frae da inviare.  
   Tempo diviso in slot=> vi e' un orologio centralizzato che scandisce i tempi ( la suddivisione in slot ) per la trasmissione, la trasmissione di un frame coincide con l'inizio dell'intervallo  
1. carrier sensitive => Una stazione  puo' verificare se il canale e' in uso oppure no.  
   non carrier sensitive => Una stazione non puo' cvapire se il canale e' in uso oppure no.  
## Aloha  puro  
L'idea di fondo è: quando una stazione ha qualcosa da trasmettere, trasmette, senza preoccuparsi delle conseguenze (quindi senza ascoltare il canale prima di trasmettere). Una stazione può accorgersi ascoltando il canale se la comunicazione è andata a buon fine. Se il pacchetto collide, la stazione rimane in attesa per un tempo casuale prima di trasmettere.  
**Qual è la probabilità che ci sia qualcun altro nella linea che strasmettere, compromettendo quindi entrambi i paccheti trasmessi?**    
Presupponiamo che vengano generati N frame per tempo di frame (tempo di trasmissione di un frame (s/c)). Se N>1 si stanno generando una quantità di frame che il canale non è in grado di gestire, data la troppa frequenza con cui vengono generati, assumiamo quindi 0<N<1.  
Le stazioni dovranno ristrasmettere i frame che hanno colliso, suponiamo una probabilità di k tentativi per tempo di frame, con una media di G frame per tempo di frame.  
La probabilità che k frame siano generati in un periodo di tempo t è: 