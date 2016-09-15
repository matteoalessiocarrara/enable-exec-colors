# Enable Exec Colors

Ci sono degli eseguibili, come grep, ls ecc, che supportano l'opzione --color 
per abilitare i colori in output. Tuttavia l'opzione deve essere specificata ogni 
volta, ed è noioso. Per questo si usano gli alias. Ma anche creare un alias 
per tutti i programmi è noioso. Quindi ho automatizzato la procedura.

Gli script sono due: **exec_color_firstrun** crea gli alias per tutti gli eseguibili 
nel sistema, mentre **exec_color_alias** solo per un eseguibile. Se l'opzione 
-- color non è supportata, non crea nessun alias.  
La prima volta andrà eseguito **exec_color_firstrun**, mentre in seguito, potrà 
essere chiamato solo **exec_color_alias** per ogni nuovo programma installato 
(vedere gli hooks del proprio package manager).

Gli alias mostrati in output potrebbero essere ridirezionati in un file, come 
~/.exec_colors, da includere poi nel proprio ~/.bashrc o simili con `source ~/.exec_colors`.


## Aggiornamenti

È possibile iscriversi al canale [telegram](https://telegram.me/matteoalessiocarrara) 
od alla comoda pagina [facebook](https://www.facebook.com/matteoalessiocarrara).

