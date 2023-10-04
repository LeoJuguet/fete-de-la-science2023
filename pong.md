# Pong

## Introduction @showhint
Aujourd'hui nous allons tenter de comprendre ce que signifie
coder un algorithme.
Pour cela faisons un Pong !


## Première instruction
Un programme n'est rien d'autres qu'une suite de petites instructions
```blocks
basic.showString(":)")
```


## Conditions

Maintenant on aimerais savoir de quel cote penche la carte.
Pour cela on a besoin de conditions.

```blocks
if (input.compassHeading() < 45) {
	basic.showString("Right")
}else if (input.compassHeading() > 45){
    basic.showString("Left")
}
```

## Variables

Maintenant que l'on sait de quel cote ca penche,
on veut se souvenir de la position de la balle.

Pour cela utilisons des variables !
Une variable c'est comme un coffre.

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


## Boucles
C'est bien on sait maintenant se souvenir de la position de la balle
Mais malheuresement le programme ne s'exécute qu'une seule fois :(

Mais l'on peut simplement résoudre ce problème en utilisant des boucles !



## Fin

Félicitation tu as créer ton premier programme !
