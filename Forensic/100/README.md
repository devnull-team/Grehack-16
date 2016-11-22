# FORENSIC - 100
## 100 pts

Le challenge porte sur Windows 98.
Une archive contenant deux fichiers est fournie :
* Une vidéo d’une conférence de Microsoft
* Une image d’un BSOD 


On commence par vérifier le type de fichiers avec __file__ :

```sh
$ file win98.*
win98.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, comment: "", baseline, precision 8, 640x512, frames 3
win98.mp4: ISO Media, MP4 v2 [ISO 14496-14]
```

Puis on fait un __exiftool__ sur le fichier jpg pour avoir plus d’informations :

```sh
$ exiftool win98.jpg
…
Warning : Skipped unknown 856 byte header
… 

```
Cette ligne signifie que des données non attendues se situent dans le fichier. Il suffit de les extraire avec __foremost__.

```sh
$ foremost win98.jpg
Processing: win98.jpg
|*|

```
On obtient alors dans le dossier output associé deux sous-dossiers :
* jpg
	- BSOD réduit
	- Image d’une Clé  
* pdf
	- Un pdf 

Le PDF nous donne une clé qui n’est pas le flag. Mettons là de côté ! 
**Im_Not_th3_fl4g_Bu7_th3_k3Y_(O o)**

OK. Analysons un peu cette image de clé… 
Un petit passage sur Google Images va nous permettre d’en savoir un peu plus.
On utilise la fonction glisser déposer de Google Images.

On se rend alors compte qu’il s’agit du logo de l’application TrueCrypt. 
Cette dernière permet de créer des partitions cryptées et montables en système de fichiers.
On lance alors la machine virtuelle Windows et on télécharge cette application.

On se doute alors que la partition doit être cachée dans le seul fichier ne nous ayant pas encore servi, la vidéo !


Après avoir renseigné le fichier à décrypter, on double-clique sur un des
lecteurs et on écrit la clé :

![truecrypt_1](/Forensic/100/Images/truecrypt_1.png )

On clic droit sur le lecteur -> Open.
Un fichier texte apparait… and FLAG !

**GH16{Polyglotte_and_Windows98_Is_Fun}**


