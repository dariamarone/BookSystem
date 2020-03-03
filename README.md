
# Book Recommendation System
## Il sovraccarico informativo danneggia l’attenzione

Tutti noi abbiamo la percezione di essere esposti ad un sovraccarico informativo crescente, con il quale ci viene chiesto di accettare senza indagini tutto ciò che ci viene offerto. L’uso di filtri è necessario per controllare la quantità (sempre crescente) e la qualità (sempre più scadente) dell’informazione al quale siamo esposti; il loro compito è quindi quello di permettere alle persone di concentrarsi solo sulle cose a cui le persone sono interessate.

Un sistema di raccomandazione permette di filtrare i contenuti più “interessanti” e creare raccomandazioni personalizzate specifiche per l’utente così da ridurre l’information overload e guidare l’utente stesso nelle sue scelte.

I sistemi di raccomandazione trovano applicazione in diversi settori, ma il loro scopo è unico: aiutare le persone a effettuare scelte basandosi su diversi aspetti. Dato un utente, questi aspetti possono essere ad esempio la propria cronologia, ovvero gli acquisti o i voti positivi e negativi già dati, o le preferenze di persone simili.
Viene utilizzato per diversi prodotti, come libri, musica, film, video, notizie e social media.

Per costruire un sistema in grado di predire i voti degli utenti e in grado di generare raccomandazioni è prima di tutto necessario scegliere il dominio di interesse. In questo caso sono stati scelti ,come prodotti da raccomandare, i libri contenuti in un data set comprensivo anche degli utenti che hanno espresso i ratings e i ratings stessi.

Il data set è composto da circa 54 000 utenti che hanno espresso un voto su un totale di 10 000 libri. I dati sono delle triplette book-user-rating in cui la prima colonna corrisponde agli identificatori dei libri, la seconda agli id degli utenti infine l’ultima corrisponde ai rating.

Dopo aver caricato il data set, i dati devono essere divisi in training set per l’addestramento e test set per la verifica.
Per creare il sistema di raccomandazione è stata costruita una rete neurale fully-connected con tre strati nascosti di cui il primo utilizzato per normalizzare i dati e quindi rendere la loro media vicina allo zero e la deviazione standard vicina all’uno. Gli ultimo due strati nascosti sono strati completamente connessi con funzione di attivazione RELU.
L’accuracy del sistema sui dati di test è dell’ 80% dopo un addestramento di 10 epoche. 

Gli embeddings possono essere utilizzati per visualizzare le relazioni tra libri diversi, i dati però devono essere prima ridotti di dimensionalità  e per farlo sono state applicate due tecniche separatamente: PCA(Principal Component Analysis) e TSNE( t-distributed stochastic neighbor embedding).

Partendo da 10 000 dimensioni, una per ogni libro, i dati sono stati mappati in 5 dimensioni usando la rappresentazione degli embeddings, successivamente ridotte a 2 utilizzando le due tecniche sopra citate.

A questo punto è facile fare raccomandazioni utilizzando il modello appena costruito. Basta inserire un utente e tutti i libri, quindi selezionare i libri con le valutazioni più alte previste per quel determinato utente.Il sistema raccomanderà all’utente i libri “migliori” cercando tra quelli con i ratings predetti più elevati. In questo modo vengono visualizzati solo i libri simili a quelli che lui stesso ha apprezzato in passato.

I risultati raggiunti sono facili da osservare e confrontare, oltre a consigliare come rinnovare e arricchire il bagaglio culturale delle persone.
 
  
                                                                                  
