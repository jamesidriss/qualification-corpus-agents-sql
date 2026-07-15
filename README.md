# Qualification préalable d’un corpus d’évaluation pour des agents d’intelligence artificielle produisant des requêtes SQL

## Conception et mise à l’épreuve d’un protocole local francophone de reconstruction, de traçabilité et de couverture relationnelle

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21367687.svg)](https://doi.org/10.5281/zenodo.21367687)

**Auteur :** James Ripoll
**Statut :** recherche indépendante
**Type de publication :** mémoire de recherche appliquée
**Date :** juillet 2026
**Langue :** français
**DOI :** [10.5281/zenodo.21367687](https://doi.org/10.5281/zenodo.21367687)

## Accès au mémoire

* [Consulter la version officielle sur Zenodo](https://zenodo.org/records/21367687)
* [Consulter le mémoire au format PDF sur GitHub](./Memoire_James_Ripoll_Qualification_Corpus_Agents_SQL_2026.pdf)

## Présentation

Ce dépôt accompagne un mémoire de recherche appliquée indépendant consacré aux conditions qui doivent être réunies avant de mesurer l’exactitude d’un agent d’intelligence artificielle chargé de répondre, en français, à une question d’analyse de données en produisant une requête SQL.

Le point de départ de la recherche est qu’une base SQLite peut être lisible, techniquement valide et interrogée sans erreur tout en ne contenant pas les informations relationnelles nécessaires à une comparaison interprétable entre la sortie d’un agent et une requête SQL de référence.

L’objectif principal n’est donc pas de classer des agents ou des modèles d’intelligence artificielle, mais de qualifier l’environnement de données qui permettrait, ou non, de produire un tel classement de manière défendable.

## Question de recherche

Dans quelles conditions un protocole local d’évaluation d’agents d’analyse SQL en français peut-il produire une mesure d’exactitude interprétable lorsque les bases sont reconstruites à partir de ressources disponibles, d’échantillons JSON limités et de schémas parfois dissociés de leurs clés sources ?

## Périmètre de l’étude

L’étude porte exclusivement sur un environnement local reconstruit à partir de fichiers, de scripts, de configurations et d’échantillons identifiés.

L’inventaire local comprend :

* 547 questions françaises ;
* 123 tâches associées à des bases SQLite disponibles ;
* 29 bases distinctes ;
* une sélection pilote de 20 tâches ;
* des échantillons locaux généralement limités à cinq lignes par table.

Ces éléments ne sont pas présentés comme des statistiques officielles relatives aux distributions académiques d’origine.

Le mémoire n’évalue pas les versions officielles de Spider, MultiSpider, Spider 2.0 ou Spider 2.0-Lite et ne conclut pas à leur défaillance.

## Méthode proposée

Le mémoire propose un protocole de qualification préalable organisé autour de plusieurs dimensions :

1. la provenance et la traçabilité des ressources ;
2. la validité technique des bases SQLite ;
3. la conservation des valeurs pendant la reconstruction ;
4. la correspondance entre les clés sources et les colonnes cibles ;
5. la présence des relations nécessaires à la résolution des tâches ;
6. l’interprétabilité des requêtes SQL de référence ;
7. la rejouabilité des opérations de reconstruction ;
8. la décision explicite d’autoriser ou de refuser le calcul d’un score.

Une grille de viabilité attribue à chaque tâche l’un des statuts suivants :

* **Vert** : toutes les conditions nécessaires à une mesure interprétable sont positivement établies ;
* **Ambre** : la tâche est techniquement exploitable, mais une preuve nécessaire à la mesure manque ou demeure insuffisante ;
* **Rouge** : un défaut critique démontré empêche la reconstruction ou l’interprétation minimale de la tâche.

## Principaux résultats

L’audit initial des 20 tâches pilotes produit les statuts suivants :

* 13 tâches Ambre ;
* 7 tâches Rouges ;
* aucune tâche Verte.

L’étude de cas `local023` identifie un mécanisme précis de dégradation : certains fichiers JSON français utilisent des clés traduites alors que le schéma et la procédure d’insertion attendent des noms de colonnes anglais.

Une correspondance explicite, limitée et versionnée permet de restaurer les valeurs perdues et de réduire les divergences observées de 7 à 0 pour cette étude de cas.

L’intervention contrôlée est ensuite étendue au périmètre étudié. Après correction documentée :

* 358 divergences critiques sont ramenées à zéro ;
* les 20 tâches sont classées Ambre ;
* aucune tâche ne conserve le statut Rouge ;
* aucune tâche n’atteint le statut Vert.

L’absence de tâche Verte est principalement liée à l’absence de certaines relations nécessaires dans les échantillons sources ou à l’insuffisance des preuves relationnelles disponibles.

## Conclusion principale

La décision méthodologique finale consiste à ne pas calculer de score d’exactitude des agents dans l’environnement local étudié.

Cette absence de classement ne constitue pas une absence de résultat. Elle représente une décision scientifique fondée sur des critères annoncés, des preuves documentées et une analyse des limites du support expérimental.

Le résultat principal du travail est donc une procédure de qualification, de correction contrôlée et de décision hors mesure, plutôt qu’un classement de performances.

## Contributions

Le mémoire apporte notamment :

* un protocole de qualification des données avant l’évaluation des agents ;
* une grille de décision Vert, Ambre et Rouge ;
* une analyse des pertes de valeurs liées aux correspondances de colonnes ;
* une méthode de contrôle de la couverture relationnelle ;
* une approche de reproductibilité fondée sur des empreintes logiques ;
* une formalisation de la décision de ne pas mesurer lorsque les conditions nécessaires ne sont pas établies.

## Contenu du dépôt

| Fichier                                                         | Description                                  |
| --------------------------------------------------------------- | -------------------------------------------- |
| `Memoire_James_Ripoll_Qualification_Corpus_Agents_SQL_2026.pdf` | Version publiée du mémoire                   |
| `README.md`                                                     | Présentation générale du travail             |
| `CITATION.cff`                                                  | Informations de citation lisibles par GitHub |

## Citation recommandée

Ripoll, James. *Qualification préalable d’un corpus d’évaluation pour des agents d’intelligence artificielle produisant des requêtes SQL : conception et mise à l’épreuve d’un protocole local francophone de reconstruction, de traçabilité et de couverture relationnelle*. Mémoire de recherche appliquée indépendant, 2026. https://doi.org/10.5281/zenodo.21367687

## Avertissement sur la portée

Ce dépôt ne constitue pas :

* un benchmark officiel ;
* une reproduction officielle de Spider ou de MultiSpider ;
* une évaluation officielle de Spider 2.0 ou Spider 2.0-Lite ;
* un classement général de modèles ou d’agents d’intelligence artificielle ;
* une preuve de défaillance des corpus académiques d’origine.

Les conclusions portent exclusivement sur l’environnement local reconstruit, les transformations, les échantillons et les artefacts effectivement étudiés.

## Données et éléments tiers

Les bases de données, fichiers JSON, schémas, marques, logiciels, publications et ressources appartenant à des tiers restent soumis à leurs licences et droits respectifs.

Leur présence ou leur mention dans le mémoire n’implique pas un droit de redistribution dans ce dépôt.

## Droits d’auteur

© 2026 James Ripoll. Tous droits réservés.

La consultation publique de ce dépôt n’autorise pas la reproduction, la redistribution, la modification ou l’exploitation du mémoire sans autorisation préalable de l’auteur.

Les données, logiciels, marques, publications et ressources appartenant à des tiers restent soumis à leurs propres licences et droits.
