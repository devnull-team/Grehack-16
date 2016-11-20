# DONTREMEMBERTHENAME
## 400 pts

Le challenge se présente sous la forme d’une image de la mémoire flash d’un disque.
Le but est de retrouver le nom de la ville d’un homme X.

![menu](/Forensic/400/Images/strings_sortie.png )


Pour commencer, on passe un coup de _file_ pour voir ce que le fichier contient :
*file 1479518451.48_dump.img*  1479518451.48_dump.img: data

Tout de suite, on pense à utiliser Volatility, un outil bien utile dans ce genre de situation. Et c’est ce que nous avons fait. Sans succès.

Nous nous sommes attelés à regarder la sortie de _string_ directement. Et c’est soudainement devenu très intérressant.

Comme on peut le constater, diverses requêtes sont faites vers des pages internet. Ce qui veut implique des téléchargements et donc du contenu mit en cache.
Pour extraire tout ça, on utilise l’outil _foremost_ qui va extraire les fichiers qu’il pourra trouver dans l’image.

Sans grand étonnement, il y en a un paquet... !

![menu](/Forensic/400/Images/foremost.png )

On regarde un peu partout, au hasard, puis soudain, il est là, beau comme un concert de Rammstein, le flag !

![menu](/Forensic/400/Images/images_forensic.png )

![menu](/Forensic/400/Images/flag.png )
