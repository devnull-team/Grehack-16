# FORENSIC - 400
## 400 pts

Le challenge se présente sous la forme d’une image de la mémoire flash d’un disque.
Le but est de retrouver le nom de la ville dans laquelle habite un homme.

Pour commencer, on passe un coup de _file_ pour voir ce que le fichier contient :
```sh
$ file 1479518451.48_dump.img  
1479518451.48_dump.img: data
```


Tout de suite, on pense à utiliser Volatility, un outil bien utile dans ce genre de situation (cad en présence de fichiers img). Et c’est ce que nous avons fait. Sans succès.

Nous nous sommes alors attelés à regarder directement la sortie de __string__. Et c’est soudainement devenu très intérressant.

![string](/Forensic/400/Images/strings_sortie.png )

Comme on peut le constater, diverses requêtes sont faites vers des pages internet. Ce qui implique des téléchargements et donc du contenu mis en cache.
Pour extraire tout ça, on utilise l’outil __foremost__  qui va récupérer les fichiers qu’il pourra trouver dans l’image.

Sans grand étonnement, il y en a un paquet... !

![foremost](/Forensic/400/Images/foremost.png )

On regarde un peu partout, au hasard, puis soudain, il est là, beau comme un concert de Rammstein, le flag ! **GH16{Krautergersheim_18}**

![image_dossier](/Forensic/400/Images/images_forensic.png )

![flag](/Forensic/400/Images/flag.jpg )

