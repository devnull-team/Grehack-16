# SAPERLIPOPETTE
## 100 pts

__Flag non vérifié par la team Securimag, ouvrez une issue si ce n’est pas le bon flag__

Le challenge consiste à analyser un fichier pcap contenant des trames SAP.
Le flag n’est pas au format GH16{…} ce qui "complique" un peu plus nos recherches.

Naturellement, le fichier étant un Pcap, on pense à l’analyser avec Wireshark.
Malheuresement, on se rend vite compte que les données sont encryptées.

Pour obtenir du texte lisible, on lance une machine virtuelle Windows et on ouvre le logiciel Cain et Abel.
On importe le pcap, puis on se rend dans la partie Sniffer. Il faut sélectioner SAP Dialog.


![cain_abel](/Network/100/Images/cain_abel.png )

Pour afficher le contenu déchiffré, il faut cliquer droit sur une ligne, puis sur "View".

Les recherches commencent donc dans le fichier texte. À coup de Ctrl-F on cherche les expressions potentiellement correctes (ex : flag, grehack, chartreuse :3).
Au bout de quelques temps n’ayant rien trouvé de concluant dans le premier fichier, on passe au deuxième.

Et soudain...

![flag](/Network/100/Images/flag.png )

__flag is : obfuscation is not security__
