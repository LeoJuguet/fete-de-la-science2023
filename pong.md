# Pong

```template
//
```

## Introduction @showdialog
Aujourd'hui nous allons tenter de comprendre ce que signifie
coder un algorithme.
Pour cela faisons un Pong ensemble !


## Première instruction
Un programme est une suite d'instruction. Une instruction
c'est une opération très simple. Essaye d'afficher un dessin
sur le microbit en glissant l'instruction ``||basic:show leds||``
dans le blocks ``||loops:on start||``
```blocks
 basic.showLeds(`
        . . . . .
        . # . # .
        . . . . .
        # . . . #
        . # # # .
        `)
```


## Conditions

Maintenant on aimerais savoir de quel côté penche la carte.
Pour cela on a besoin de conditions.

## Conditions
Insère un bloque ``||conditions:si||`` et affiche un point du
cotes où la carte penche. Pour cela utilise un test sur la valeur
de ``||input:compassHeading||``

```blocks
if (input.compassHeading() < 0) {
	basic.showString("Right")
}else if (input.compassHeading() > 0){
    basic.showString("Left")
}
```

## Ca marche pas ? @showdialog
C'est etrange pour le moment ca ne marche pas bien.
Le programme effectue une itération puis s'arrête.

Pour remedier à ce problème utilisons des boucles !

Une boucle est simplement un bloque qui se répète tant qu'une condition
est vrai.
Essayons !

## Boucles
Mets le programme que tu viens de coder dans une boucle tant que.

```blocks
while(true){
    if (input.compassHeading() < 45) {
	    basic.showString("Right")
    }else if (input.compassHeading() > 45){
        basic.showString("Left")
    }
}
```


## Variables @showdialog
Maintenant que l'on sait de quel cote ca penche,
on veut se souvenir de la position de la balle.

Pour cela utilisons des variables !
Une variable est comme un coffre, c'est un endroit où l'on 
sauvegarde des valeurs.

## Variables

Essaye de créer une variable position. Dans la section variable.

## Initialisation de la variable.
Au tout départ on ne connait pas la valeurs de la variable.
Il faut donc luis assigner une valeur. Disons que la balle est 
au centre, et que sa position est donc 0.
```blocks
let position = 0;
```

## Mise à jour de la variable
Bon, c'est bien beau, mais pour le moment la variable est toujours à 0.
Dans la comparaison que tu as précedement fait, mets à jour la variable.
avec un +1 si ca penche à droite et -1 si ca penche à gauche.

```blocks
let position = 0;
if (input.compassHeading() > 0) {
    position = position + 1
}else if (input.compassHeading() < 0){
    position = position - 1
}
```

## Position visuel de la balle
Pour le moment on a fait des choses, mais on ne voit toujours 
pas de balle sur le microbit.
Rajoute des conditions pour afficher une balle a la bonne position
à l'aide de conditions et de la variable.


```blocks
let position = 0;
if (input.compassHeading() > 0) {
    position = position + 1
}else if (input.compassHeading() < 0){
    position = position - 1
}
if(position == -2 ){
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
}else if (position == -1 ){
    basic.showLeds(`
        . . . . .
        . . . . .
        . # . . .
        . . . . .
        . . . . .
        `)
}else if (position == 0 ){
    basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
}else if (position == 1){
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . # .
        . . . . .
        . . . . .
        `)
}else if (position == 2){
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
}
```



## Fin

Félicitation tu as créer ton premier programme !
