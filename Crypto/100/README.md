# Sam Sepiol
## 100 pts

Le challenge se présente sous la forme d’une image au format png.
Il s’agit d’un menu de pizzeria sur lequel figure aux côtés des tarifs plusieurs inscriptions étrange.

![menu](/Crypto/100/Images/menu.png )

unirlbhznqrlbhepubvpr?

* 1.11 - 7.24 - 1.0 - 6.0 - 0123
* 6.29 - 9.5 - 9.26 - 5.26 - 048
* 1.0 - 2.3 - 5.0 - 2.22 - 9.15 - 5.2 - 1.7
* 8.20 - 1.5 - 0125


D’instinct, la première chaîne fait penser à du rot13. Ce qui donne une fois traduit : haveyoumadeyourchoice?

Néanmmoins, rien de très utile pour le moment.

Au niveau de la série de nombres, il semblait y avoir un rapport entre le premier des deux chiffres de chaque groupe, et le numéro des pizzas disponibles. Le second nombre devant sûrement indiquer un déplacement.

1. Les groupes sans le "." séparateur sont des représentations décimales de l’ASCII. 
2. La pizza 0 n’existant pas, la valeur récupérée était le premier chiffre du groupe.

À ce niveau là, on reconnaissait la forme du pattern.

Après plusieurs minutes de réflexion et de tests, nous avons trouvé la manière d’obtenir les bonnes lettres.

Il fallait pour cela partir du nom de la pizza visée, se déplacer de n lettres vers la droite et effectuer un ROT13. Puis répéter l’opération autant de fois que néccesaire. 

On obtenait alors le flag.






