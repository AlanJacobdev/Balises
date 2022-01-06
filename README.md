


# Projet Balises et Satellites

## Constitution du groupe 

 - Lucas TANNÉ
 - Alan JACOB

## Correction du bogue

#### Problème

Le problème constaté lors de l'éxécution du programme initial concernait la synchronisation d'une balise avec un satellite.

La balise effectuait un deplacement, durant lequel elle recoltait diverses données, lorsque la mémoire de cette balise était pleine, elle remontait à la surface pour se synchroniser avec le premier satellite qu'elle croisait. 

Au lieu de vider sa mémoire à la synchronisation pour ensuite retourner recolter des données sur son deplacement interrompu dû à sa mémoire pleine, elle vidait sa mémoire dès qu'elle était remplie, avant de remonter pour se synchroniser, sauf que les données recommençait à se collecter durant la remontée et l'attente du satellite.

Donc, si jamais la remontée était grande et/ou l'attente était longue, dès qu'un satellite passait, sa mémoire était possiblement de nouveau pleine, et ainsi, elle sauvegardait son dernier mouvement, la remontée pour se synchroniser. Elle restait ainsi bloquer à la surface.

#### Correctif

Le vidage de mémoire se fait désormais lors de la synchronisation et la collecte des données ne s'effectue plus lors de la montée et la descente de la balise, et reprends lors de son déplacement normal.

Un boolean permet de verifier si on est en phase de synchronisation ou non.

## Ajout et amélioration
