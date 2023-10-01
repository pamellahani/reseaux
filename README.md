# reseaux
INFO 3 Jeu du Pendu - Sockets - in C 

Cahier des charges de l’application du jeu du pendu 

Le protocole applicatif de l’application d’un jeu du pendu, en utilisant des sockets TCP : 

Le client se connecte au serveur en spécifiant l'adresse IP et le port utilisé par le serveur ainsi que l’adresse ip du client qu’il veut utiliser.
Le client envoie une requête de connexion au serveur en s’identifiant par une adresse IP et en indiquant le port du serveur.
Le serveur envoie une réponse de connexion au client pour confirmer l'identification.
Le client envoie une requête de sélection de niveau de jeu au serveur, contenant le nombre maximal d'essais autorisés.
Le serveur envoie une réponse de confirmation au client pour indiquer que le niveau a bien été choisi.
Le serveur sélectionne un mot mystère au hasard. 
Le serveur envoie lui annonce le nombre de lettres du mot mystère ainsi que le nombre d'essais.

Le client envoie successivement des propositions de caractères au serveur, jusqu'à ce que le mot mystère soit trouvé ou que le nombre maximal d'essais soit atteint : 
À chaque proposition de caractère, le serveur vérifie si le caractère proposé est présent dans le mot mystère : 
Si le caractère proposé est présent dans le mot mystère, le serveur envoie au client une chaîne représentant l'état de découverte du mot mystère, avec le(s) caractère(s) trouvé(s) affiché(s) à leur position respective, et le nombre d'essais restants.
Sinon, le serveur envoie au client la même chaîne que précédemment, mais avec un essai en moins.
Si le mot mystère est trouvé avant d'avoir atteint le nombre maximal d'essais autorisés, le serveur envoie un message de félicitations au client.
Sinon, le serveur envoie un message d'échec au client et le programme demande de recommencer avec un nouveau mot mystère: 
SI le client répond oui, le serveur sélectionne un nouveau mot mystère et envoie le nombre de lettres au serveur. 
Sinon, déconnexion. 

Les dialogues entre le client et le serveur se terminent par une requête de déconnexion du client, suivie d'une réponse de déconnexion du serveur.
Le niveau de facilité correspond en fait au nombre d’essais ajouté au nombre de caractères dans le mot. Celui-ci est donné en paramètre par le client. Le niveau 0 correspond alors au niveau le plus dur.

Un automate résumant cela a été réalisé sous le nom : “automatePendu.png”
