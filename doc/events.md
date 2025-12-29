# Les événements

Les événements ("events") ont pour nomenclature : `escape-game.` + `eventCode`.
Ci-dessous, la liste des `eventCode` utilisables.

## Events utilisables

### Général
* `start`
* `play`
* `pause`
* `penalty`
* `end`
* `close`

### Code
* `code.bad`
* `code.good`
* `code.unknown`

### Help
* `help.good`
* `help.unknown`

### Machine
* `machine.start`
* `machine.wrong`
* `machine.bad`
* `machine.good`
* `machine.unknown`

## Détails d'un event

L'event est un [CustomEvent](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent) standard, qui possède un champ `detail` avec les champs suivants :
* **eventCode** *(str)* : voir liste ci-dessus
* **stepCode** *(str | null)* : non-nul lorsque l'`eventCode` vaut `code.*`, `help.*` ou `machine.*`.
* **stepValue** *(str | null)* : non-nul lorsque l'`eventCode` vaut `machine.wrong`, `machine.bad` ou `machine.good`.
* **actions** *(Actions)* : contient l'ensemble des informations du jeu. (TODO: ajouter description des Actions).

## Écouter un event

Vous pouvez simplement utiliser quelque chose comme :
```javascript
window.addEventListener(
  'escape-game.start', // eventCode
  (e) => {
    console.log(e.detail);
  }
);
```
À placer dans le `setInitCallback` de la méthode `load()` de votre `Scenario`.
Voir []() pour un exemple concret.
