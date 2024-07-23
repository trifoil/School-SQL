# Synthese

## Mot-clé ```SELECT```

* Selectionner l'ensemble des éléments d'une table :   
```SELECT``` * ```FROM``` table

* Regrouper par rapport à une colonne :     
```GROUP``` ```BY``` table.column

* Regrouper par rapport à plusieurs colonnes :          
```GROUP``` ```BY``` table.column1, table.column2       
groupe d'abord par élément de la column1 puis dans chaque groupe, groupe par les élements de la column2

* Ordonner par rappot à une colonne :     
```ORDER``` ```BY``` table.column



```FROM```
```WHERE```
```JOIN```
```HAVING```

## ```JOIN```

### Mot-clé ```INNER JOIN```

Selectionne tous les rows de chaque table tant que la condition est satisfaite.

Le row ne sera pas selectionné si il est absent d'au moins une des deux tables

### Mot-clé ```LEFT JOIN```

Selectionne tous les rows de la table de gauche ainsi que tous les rows de la table de droite qui ont un match avec la colonne selectionnée de la table de gauche

For the rows for which there is no matching row on the right side, the result-set will contain null. 

### Mot-clé ```RIGHT JOIN```

Selectionne tous les rows de la table de droite ainsi que tous les rows de la table de droite qui ont un match avec la colonne selectionnée de la table de gauche

For the rows for which there is no matching row on the left side, the result-set will contain null.

### Mot-clé ```INNER JOIN```

creates the result-set by combining results of both LEFT JOIN and RIGHT JOIN. The result-set will contain all the rows from both tables. For the rows for which there is no matching, the result-set will contain NULL values.
Full_Join


## Mot-clé ```HAVING``` vs ```WHERE```

