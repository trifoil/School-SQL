
## EXERCICE 1 : villes de France

1) Obtenir la liste des 10 villes les plus peuplées en 2012 ;     
```
SELECT * FROM villes_france_free ORDER BY villes_france_free.ville_population_2012 DESC LIMIT 10; 
```

2) Obtenir la liste des 50 villes ayant la plus faible superficie ;          
```
SELECT * FROM villes_france_free ORDER BY villes_france_free.ville_surface ASC LIMIT 50; 
```

3) Obtenir la liste des départements d’outre-mer, c’est-à-dire ceux dont le numéro de
département commence par “97” ;      
```
SELECT * FROM villes_france_free WHERE LEFT(villes_france_free.ville_departement, 2) = "97"; 
```
4) Obtenir le nom des 10 villes les plus peuplées en 2012, ainsi que le nom du
département associé ;       
```
SELECT villes_france_free.ville_nom_simple, villes_france_free.ville_departement FROM villes_france_free ORDER BY villes_france_free.ville_population_2012 DESC LIMIT 10; 
```
5) Obtenir la liste du nom de chaque département, associé à son code et du nombre de
commune au sein de ces départements, en triant afin d’obtenir en priorité les
départements qui possèdent le plus de communes ;        

* Pour obtenir les départements classés dans l'ordre descendant de ceux qui contiennent le plus de villes, et le nombre de villes dasn chaque département, on peut utiliser :
```
SELECT villes_france_free.ville_departement, COUNT(villes_france_free.ville_departement) FROM villes_france_free GROUP BY villes_france_free.ville_departement ORDER BY COUNT(villes_france_free.ville_departement) DESC; 
```
* Avec jointure :
```
SELECT departement.departement_nom, departement.departement_code, COUNT(villes_france_free.ville_departement) FROM villes_france_free INNER JOIN departement ON departement.departement_code=villes_france_free.ville_departement GROUP BY villes_france_free.ville_departement ORDER BY COUNT(villes_france_free.ville_departement) DESC 
```

6) Obtenir la liste des 10 plus grands départements, en termes de superficie ;
```
SELECT departement.departement_nom, SUM(villes_france_free.ville_surface) FROM departement INNER JOIN villes_france_free ON departement.departement_id=villes_france_free.ville_departement GROUP BY departement_code ORDER BY SUM(villes_france_free.ville_surface) DESC

```
7) Compter le nombre de villes dont le nom commence par “Saint” ;
```
SELECT COUNT(villes_france_free.ville_nom) FROM villes_france_free WHERE LEFT(villes_france_free.ville_nom, 5)="Saint"
```
cad
```
SELECT COUNT(*) FROM villes_france_free WHERE LEFT(ville_nom, 5)="Saint"
```
ou
```
SELECT COUNT(*) FROM `villes_france_free` WHERE `ville_nom` LIKE 'saint%'
```

8) Obtenir la liste des villes qui ont un nom existant plusieurs fois, et trier afin d’obtenir
en premier celles dont le nom est le plus souvent utilisé par plusieurs communes ;
```
SELECT villes_france_free.ville_nom, COUNT(*) AS nb_villes 
FROM villes_france_free
GROUP BY villes_france_free.ville_nom
ORDER BY nb_villes DESC
```
9) Obtenir en une seule requête SQL la liste des villes dont la superficie est supérieure à
la superficie moyenne ;
```

```
10) Obtenir la liste des départements qui possèdent plus de 2 millions d’habitants ;
```

```
11) Remplacez les tirets par un espace vide, pour toutes les villes commençant par
“SAINT-” (dans la colonne qui contient les noms en majuscule) ;
```

```

## EXERCICE 2 : parc informatique

### Requête monotable et de groupement 

Ecrire les requêtes permettant d’extraire, à l’aide d’instructions SELECT,
les données suivantes :

1) Quel est le type de poste du poste ’p8’ ;
```

```
2) Quelles sont les noms des logiciels ’UNIX’ ;
```

```
3) Donnez les noms, l’adresses IP, les numéros de salle des postes de type ’UNIX’ ou
’PCWS’ ;
```

```
4) Même requête pour les postes du segment ’130.120.80’ triés par numéros de salles
décroissants ;
```

```
5) Donnez les numéros des logiciels installés sur le poste ’p6’ ;
```

```
6) Donnez les numéros des postes qui hébergent le logiciel ’log1’.
``` 

```
7) Donnez les noms et adresses IP complètes (ex : ’130.120.80.01’) des postes de type
’TX’ (utiliser la fonction de concaténation) ;
```
```
8) Donnez pour chaque poste, le nombre de logiciels installés sur celui-ci (en utilisant la
table Installer) ;
```
```
9) Donnez pour chaque salle, le nombre de postes dans celle-ci et classez-les par ordre
croissant de nombre de poste (à partir de la table Poste) ;
```
```
10) Donnez pour chaque logiciel, le nombre d’installations effectuées sur des postes
différents ;
```
```
11) Donnez la moyenne des prix des logiciels de type ’UNIX’ ;
```
```
12) Donnez la date la plus récente d’achat d’un logiciel 
```
```
13) Donnez les numéros des postes qui ont 2 logiciels installés ;
```
```

### Requête multitables et sous requêtes 

Pour les requêtes 4,5,6 et 7 essayer de les résoudre de 3 manières différentes
(produit cartésien, sous requêtes et avec le mot clé JOIN et ses dérivés)

1) 
```

```
2) 
```

```
3) 
```

```
4)
```

```
5)
```

```
6)
```

```
7)
```
```
8)
```
```

### Procédure stockée :
Ecrire le bloc MySQL qui affiche les détails de la dernière installation de logiciel
sous la forme suivante (les champs en gras sont à extraire) :
```
+------------------------------------------------+
| Resultat 1 exo 1                               |
+------------------------------------------------+
| Derniere installation en salle : numérodeSalle |
+------------------------------------------------+
+------------------------------------------------------------------------+
| Resultat 2 exo 1                                                       |
+------------------------------------------------------------------------+
| Poste : numéroPoste Logiciel : nomLogiciel en date du dateInstallation |
+------------------------------------------------------------------------+
```

```
```

## EXERCICE 3 : achat

C’est une base de données de vente, on a une table client, qui peut faire des
commandes qui se retrouvent dans la table commande. La table
commande_ligne fait le lient entre les produits et les commandes pour connaitre
la quantité et les prix.

1)
```

```
2)
```

```
3)
```

```
4)
```

```
5)
```

```
6)
```

```
7)
```
```
8)
```
```
9)
```
```
10)
```
```
11)
```
```
12)
```
```
13)
```
```