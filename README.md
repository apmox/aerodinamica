# Aerodinamica
Verranno qui raccolti i concetti utili nello studio e nella comprensione dell'Aerodinamica.
In particolare saranno affrontate le basi per la modellazione matematica, fisica e numerica di un fluido nel suo campo di moto.

## Esercitazioni numeriche
### Esercitazioni 1 e 2: Fluido passante per una turbomacchina
* _Definizione turbomacchina_
* _Campo fluido simmetrico assialmente_
* Modellazione profilo turbomacchina
* Leggi governanti il fluido

**Esercitazione 1**: Metodo delle differenze divise
* Discretizzazione campo fluido con rettangoli
    * Identificazione punti di contorno
    * Identificazione punti o *nodi* di interesse interni al campo
    * Identificazione nodi adiacenti ad ogni nodo
    * Identificazione parametri `$\lambda$` per i nodi vicini al contorno
    * Assegnazione funzione di corrente iniziale ad ogni nodo
* Implementazione leggi governanti con differenze divise parametrizzate
* Individuazione nodi con valore di funzione di corrente desiderato
* Interpolazione nodi con spline
* Visualizzazione campo fluido e curva con funzione di corrente del valore desiderato

**Esercitazione 2**: Metodo degli elementi finiti
* Discretizzazione campo fluido con quadrilateri
    * Modellazione curve mozzo e corona con parametrizzazione di ascissa curvilinea
    * Suddivisione in nodi delle curve
    * Suddivisione in nodi del campo interno a partire dai nodi nelle curve
* Determinazione quadrilateri
* Determinazione funzioni di forma

> Da studiare la teoria per questa parte

### Esercitazione 3: Funzione potenziale per campo di moto indisturbato

### Esercitazione 4: Funzione potenziale per campo di moto sorgente
