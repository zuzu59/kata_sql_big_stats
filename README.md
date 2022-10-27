# kata_sql_big_stats
Petit kata pour apprendre à faire des statistiques sur de très grandes tables, 5M records !

zf221027.1357

# Buts
Apprendre à sortir des statistiques d'une très grande table, du style plusieurs millions de records (ici 4.7M records).

Le but aussi c'est d'utiliser des outils tellement simples que l'on en a oublié leur existence.

Donc on va chercher l'efficience et non l'efficacité ici !

Quelle différence entre l'efficience et l'efficacité ?

Par exemple, il y a une mouche sur le mur du salon et que si on utilise un GROS canon pour la tuer, on va être super efficace, car on ne va pas la rater, mais cela aura coûter cher et surtout on aura détruit le salon. Si on prend un petit tape mouches, on sera moins efficace car on risque de rater la mouche, mais beaucoup plus efficient car on n'aura fait aucun dégât dans le salon !


# Problématiques
Au moment où on dépasse le million de lignes, il devient difficile de sortir des statistiques avec des outils simples style tableurs. On doit alors se diriger vers des outils de style base de données.


# Moyens
- Utilisation obligatoire d'une base de donnée.
- Tous les coups sont permis pour avoir le plus d'efficience possible.


## Critères dévaluation
C'est celui qui aura pris une solution 
- la plus efficience au niveau ressource informatique
- le moins de temps pour la mettre en place
- le temps d'exécution pour le calcul des résultats


## Documentation des résultats
La procédure pour arriver au résultat du CDC devra être documentée, ligne par ligne, dans un fichier en Markdown. On doit pourvoir en exécutant chaque lignes refaire le kata. 

S'il y a un script ou makefile, c'est un plus, mais pas nécéssaire


# CDC (Cahier Des Charges)
Soit une table de 4.7M record d'un enregistreurs d'un système de domotique. Une ligne d'enregistrement de l'état d'un appareil géré dans le système de domotique.

```
I_INDEX,C2,DEVICE,VALUE,C5,C6,C7,TIME,C9,C10,C11,C12,C13,C14,C15
195763718,NULL,sensor.sie_l3_power_gratuit_w,1,NULL,NULL,NULL,2022-10-22 01:02:54,NULL,NULL,1005598,0,01GFYKDPDCJQEABRTB26DH8WYT,NULL,NULL
195763719,NULL,sensor.sie_l3_energy_gratuit_wh,330471.64,NULL,NULL,NULL,2022-10-22 01:02:54,NULL,NULL,1005643,0,01GFYKDPETKFGMX8BESSNT02C0,NULL,NULL
195763720,NULL,sensor.ow_th_ext_sud_uptime,202787,NULL,NULL,NULL,2022-10-22 01:02:55,NULL,NULL,887486,0,01GFYKDQZ7T6YZDT38PR5274PP,NULL,NULL
195763721,NULL,sensor.th3_uptime,61598,NULL,NULL,NULL,2022-10-22 01:02:56,NULL,NULL,1451146,0,01GFYKDRE6AB6HMD6D0RM32ENY,NULL,NULL
195763722,NULL,sensor.energy_meter_1_a0,2.07,NULL,NULL,NULL,2022-10-22 01:02:56,NULL,NULL,995390,0,01GFYKDRY2456A6BAC48Y3PRD2,NULL,NULL
195763723,NULL,sensor.l3_lumieres_1er_ssol_courant_consomme,1.98,NULL,NULL,NULL,2022-10-22 01:02:56,NULL,NULL,997937,0,01GFYKDRY2456A6BAC48Y3PRD2,NULL,NULL
195763724,NULL,sensor.l3_lumieres_1er_ssol_eval_power_consomme,465,NULL,NULL,NULL,2022-10-22 01:02:56,NULL,NULL,1005628,0,01GFYKDRY2456A6BAC48Y3PRD2,NULL,NULL
195763725,NULL,sensor.th11_bat_capacity,47,NULL,NULL,NULL,2022-10-22 01:02:57,NULL,NULL,1527712,0,01GFYKDSWWDX2QZVWD6HP2GH4K,NULL,NULL
195763726,NULL,sensor.th2_humidite,88.6,NULL,NULL,NULL,2022-10-22 01:02:58,NULL,NULL,1451117,0,01GFYKDTAC05PM2P76GZNX2ZBZ,NULL,NULL
```

**Remarque**

*Il y a des colonnes qui ne sont pas utilisables dans ce kata !*

Par exemple si on a une sonde de température qui enregistre la température toute les minutes, on va avoir une ligne avec chaque fois, le nom de l'appareil, sa valeur et la date de la mesure.

On peut avoir un autre appareil, qui va faire une mesures toutes les 2 secondes et un autre toutes les 15 minutes. Avec à chaque fois une ligne dans la table.

**Le challenge ici est:**

## Combien d'appareils différents dans la DB
Donc de compter le nombre d'appareils différents qui se trouve dans la DB.


## Hit parade des appareils
Sortir le hit parade des 20 appareils qui ont le plus de records dans la DB


## Hit parade des jours de records
Sortir le hit parade des jours qui ont le plus de records dans la DB


# Données pour le kata
Les données sont trop grosses pour se trouver dans le dépôt GIT, elles se trouvent donc ici:

https://drive.google.com/file/d/1GfPo476QDDcbwAL3x4aUvrO9pQOY1TlX/view?usp=sharing




