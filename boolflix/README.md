Creare un layout base con una searchbar (una input e un button) in cui possiamo scrivere completamente o parzialmente il nome di un film. Possiamo, cliccando il  bottone, cercare sull’API tutti i film che contengono ciò che ha scritto l’utente.
Vogliamo dopo la risposta dell’API visualizzare a schermo i seguenti valori per ogni film trovato: 
Titolo
Titolo Originale
Lingua
Voto
-------------------------------------------------------------------------------------------------------------------------------

1 importo l'api usando axios
2 poi creo un Ul nel main con un input text e button
3 uso l'emit per inviare l'input di ricerca =
4 stampo i risultati trovati

-------------------------------------------------------------------------------------------------------------------------------

Trasformiamo la stringa statica della lingua in una vera e propria bandiera della nazione corrispondente, gestendo il caso in cui non abbiamo la bandiera della nazione ritornata dall’API (le flag non ci sono in FontAwesome) [per ogni film].

Allarghiamo poi la ricerca anche alle serie tv. Con la stessa azione di ricerca dovremo prendere sia i film che corrispondono alla query, sia le serie tv, stando attenti ad avere alla fine dei valori simili (le serie e i film hanno campi nel JSON di risposta diversi, simili ma non sempre identici)


1 importo l'api per le serie tv
2 collego l'opzione search anche per l'api delle serie tv
3 stampo a schermo
4 creo un array con delle bandiere di alcune nazioni e una globale
5 tramite dei v-if stampo le bandiere corrispendenti alle nazioni