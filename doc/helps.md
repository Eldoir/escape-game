# Les indices

Dans votre `Scenario`, dans la méthode `load()`, vous pouvez par exemple utiliser :
```javascript
this.addHelp(new Help('99', "Test"))
```
Ce qui permettra aux joueurs d'obtenir l'indice *Test* en entrant le code **99**.

Il est possible d'ajouter plusieurs niveaux d'indices :
```javascript
this.addHelp(
    new Help('99', "Test")
        .addHelp("Ceci est le\n deuxième indice")
        .addHelp("Et voici la solution")
)
```

La dernière "Help" ajoutée sera toujours affichée comme la solution :
![Multiple](./helps_1.jpg)

L'indice courant est affiché en vert, et la solution est toujours affichée en rouge.
Utiliser des indices, ou la solution, est comptabilisé en fin de partie (comme sur la vraie application Unlock).
Il n'y a *a priori* pas de limite au nombre d'indices pour une carte donnée, mais les scénarios officiels d'Unlock se limitent à 3 maximum.