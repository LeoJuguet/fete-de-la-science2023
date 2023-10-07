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
sur le micro:bit en glissant l'instruction ``||basic:show leds||``(montrer LEDs)
dans le blocks ``||basic:on start||``(au démarrage)
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
Insère un bloque ``||input:onGesture||``(Lorsque) et affiche un point du
côté où la carte penche. Pour cela utilise un test sur
 ``||gesture:TilRight||``(incliner à droite) ou ``||gesture:TilLeft||``(incliner à gauche).

```blocks
input.onGesture(Gesture.TilRight, function() {
	basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
})
input.onGesture(Gesture.TilLeft, function(){
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
})
```

## Ca marche pas ? @showdialog
C'est etrange pour le moment ca ne marche pas bien.
Le programme effectue une itération puis s'arrête.

Pour remedier à ce problème utilisons des boucles !

Une boucle est simplement un bloque qui se répète tant qu'une condition
est vrai.
Essayons !

## Boucles
Mets le programme que tu viens de coder dans une boucle ``||loops:while true||``(tant que).
Puis test
```blocks
while(true){
input.onGesture(Gesture.TilRight, function() {
	basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
})
input.onGesture(Gesture.TilLeft, function(){
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
})
}
```


## Variables @showdialog
Maintenant, que l'on sait de quel côté penche la carte, 
on veut se souvenir de la position de la balle.

Pour cela, utilisons des variables !
Une variable est comme un coffre, c'est un endroit où 
l'on sauvegarde des valeurs.
## Variables

Essaye de créer une variable position. Dans la section variable.

## Initialisation de la variable.
Au tout départ, on ne connaît pas la valeur de la variable. 
Il faut donc luis assigner une valeur. 
Disons que la balle est au centre, et que sa position est donc 0.
```blocks
let position = 0;
while(true){
input.onGesture(Gesture.TilRight, function() {
	basic.showLeds(`
        . . . . .
        . . . . .
        . . . . #
        . . . . .
        . . . . .
        `)
})
input.onGesture(Gesture.TilLeft, function(){
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
})
}
```

## Mise à jour de la variable
Pour le moment, la variable est toujours à 0. 
Dans la comparaison que tu as précédemment faite, 
mets à jour la variable, ajoute 1 si la carte penche à droite, 
et enlève 1 si la carte penche à gauche.

```blocks
let position = 0;
while(true){
input.onGesture(Gesture.TilRight, function() {
	position = position + 1
})
input.onGesture(Gesture.TilLeft, function(){
    position = position - 1
})

}
```

## Position visuel de la balle
Pour le moment, on a fait des choses, 
mais on ne voit toujours pas de balle bouger sur le microbit. 
Rajoute des conditions pour afficher une balle à la bonne position à 
l'aide de conditions et de la variable. (tu peux t'aider de l'indice.)


```blocks
let position = 0;
while(true){
input.onGesture(Gesture.TilRight, function() {
	position = position + 1
})
input.onGesture(Gesture.TilLeft, function(){
    position = position - 1
})

if(position == -2 ){
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . .
        . . . . .
        . . . . .
        `)
}else if (position == -1 ){
// Complète
}else if (position == 0 ){
// Complète
}else if (position == 1){
// Complète
}else if (position == 2){
// Complète
}
}
```



## Fin

Félicitations, tu as créé ton premier programme !
Pour aller plus loin, tu peux rajouter un son ou un message 
quand la balle sort de l'écran !

