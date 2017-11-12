---
title: Turbomacchina semplice
layout: post
---

# Turbomacchina semplice
Dal vocabolario Treccani, la voce [turbomacchina](http://www.treccani.it/vocabolario/turbomacchina/):

> **turbomàcchina** s. f. (comp. di turbo- e macchina). – Macchina motrice o operatrice a fluido, caratterizzata dalla presenza di una ruota mobile (ventola o girante) calettata sull’albero della turbina e munita alla periferia di pale che hanno la funzione di ricevere energia da un fluido motore (acqua, vapore o gas) per trasmetterla all’albero (turbomotrici: turbine idrauliche, a vapore o a gas), o anche quella di trasmettere energia a un fluido, utilizzando il lavoro meccanico che un motore fornisce all’albero della turbina (turbooperatrici: turbopompe, turboventilatori, turbosoffianti e turbocompressori).

> Immagine t.m. reale: pompa e turbina

Il fluido che scorre in una t.m. è un esempio di fluidodinamica interna: sono ben conosciute le condizioni di contorno dato che il sistema è chiuso.

La t.m., in questo caso eccessivamente semplificata, è composta da due elementi: il **girante**, parte rotante con asse di rotazione coincidente all'asse di simmetria; la **corona**, parte stazionaria che circonda il girante. Le pale non vengono incluse in questa semplificazione, ma la t.m. deve esserne provvista per mettere in movimento il fluido.

> Immagine t.m. in 3d | Immagine t.m. 3d sezionata | Immagine sezione

La t.m. presenta una simmetria di tipo assiale: ogni piano passante per l'asse di simmetria seziona la t.m., creando un profilo identico per ogni angolo. Questa simmetria cilindrica permette di modellare il *campo di moto fluido* in due sole dimensioni, in questo contesto definite come `z` (direzione assiale) ed `r` (direzione radiale). Integrando successivamente nella direzione angolare di simmetria ci si potrà ricondurre al campo di moto del fluido in un volume di controllo tridimensionale.

## Modellazione numerica del profilo della turbomacchina
Tutte le seguenti impostazioni sono scelte arbitrariamente per modellare in modo semplice il profilo.

Si utilizza uno dei semi-piani di simmetria, con ascisse di coordinata assiale `z` e ordinate di coordinata radiale `r`. Il profilo di sezione assomiglia ad un semplice condotto che devia il flusso verso l'alto: ciò accade se la turbomacchina è una pompa.
Per modellare numericamente il profilo servono i seguenti parametri:

|| Da inserire nell'algoritmo | Misurabile sperimentalmente |
|---|---|---|
| 1 | Raggio interno del girante | Diametro girante |
| 2 | Larghezza entrata | Diametro girante, diametro interno corona |
| 3 | Larghezza uscita | Distanza all'usicta tra girante e corona |
| 4 | Lunghezza campo fluido | Lunghezza girante, o lunghezza corona e distanza corona-girante |
| 5 | Distanza uscita dall'asse | Diametro esterno girante o diametro esterno corona |
| 6 | Raggio di curvatura girante | Direttamente |
| 7 | Raggio di curvatura corona | Direttamente |
| 8 | Distanza curvatura corona | Direttamente |

Noti i parametri, vengono individuate le coordinate dei punti immediate `A`, `B`, `C`, `D`, `F`, `G`. Successivamente va cercato il punto di tangenza `T` della curvatura della corona in modo da non avere spigoli all'interno del campo.

Si approssima il girante come composto da un cilindro allungato, una smussatura circolare con raggio di curvatura individuato, e un disco di spessore irrilevante e diametro misurabile. La corona viene vista come una cavità cilindrica che via via viene smussata e poi diventa una cavità conica.

Bidimensionalmente il contorno del profilo si costruisce dunque come segue:
* Entrata: retta verticale
* Uscita: retta orizzontale
* Girante: retta orizzontale, poi quarto di circonferenza, poi retta verticale
* Corona: retta orizzontale, poi frazione di circonferenza, poi retta inclinata

Ora che il dominio del campo di moto del fluido è determinato come una curva definita a tratti nel piano, al calcolatore si possono eseguire le discretizzazioni.
