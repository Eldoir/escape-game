# addResources()

Dans cette méthode, vous ne devriez appeler que 2 méthodes sur `this` :

## addResourceImage(code, filename, useDefault = false)
### code `str`
Un identifiant pour cette ressource, qui sert dans d'autres méthodes pour faire référence à cette ressource. Exemple : `bkg_main`.
### filename `str`
Le nom de fichier de la ressource, extension incluse. Exemple : `bkg_main.jpg`. 
* Ce fichier doit être placé dans le sous-dossier `image` de votre dossier de scénario.
* Une grande variété de formats sont supportés (tous ceux de la balise HTML [img](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img#supported_image_formats), en fait).
### useDefault `boolean` `false`
Si `true`, alors le jeu ira chercher ce fichier dans le scénario `_default` du dossier `scenario` au lieu de ce scénario.

## addResourceSound(code, filename, volume, useDefault = false)
### code `str`
Un identifiant pour cette ressource, qui sert dans d'autres méthodes pour faire référence à cette ressource. Exemple : `sound_good`.
### filename `str`
Le nom de fichier de la ressource, extension incluse. Exemple : `sound_good.mp3`.
* Ce fichier doit être placé dans le sous-dossier `sound` de votre dossier de scénario.
* Le jeu utilise [Howler.js](https://github.com/goldfire/howler.js) pour jouer des sons, ce qui signifie qu'une grande variété de formats audio sont supportés : `mp3`, `ogg`, `wav`, `aac`, `m4a`, `webm`, `flac`...
### volume `number`
Le volume sonore auquel jouer le son. Entre `0.0` et `1.0`. Exemple : `0.5`.
### useDefault `boolean` `false`
Si `true`, alors le jeu ira chercher ce fichier dans le scénario `_default` du dossier `scenario` au lieu de ce scénario.

## Exemple

Les méthodes ci-dessus renvoient `this`, ce qui signifie qu'on peut les chaîner. Un exemple basique serait donc :
```javascript
addResources() {
    this
        .addResourceImage('bkg_main', 'bkg_main.jpg')
        .addResourceSound('sound_good', 'sound_good.mp3', 0.8, true)
    ;
}
```

Dans cet exemple :
* on ajoute une ressource image, à laquelle on pourra plus tard faire référence sous le nom `bkg_main`. Le fichier chargé est `scenario/example/image/bkg_main.jpg` (si le scénario a pour nom `example`).
* on ajoute une ressource son, à laquelle on pourra plus tard faire référence sous le nom `sound_good`. Le fichier chargé est `scenario/_default/sound/sound_good.mp3`, car on a précisé `true` pour le paramètre `useDefault`. Le son sera joué à 80% du volume original du fichier.