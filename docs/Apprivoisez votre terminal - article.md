# Apprivoisez votre terminal
*A la découverte du CLI #1*

## L'interface graphique
Tout le monde connait l'Interface graphique des ordinateurs, c'est le mode d'interaction classique avec son ordinateur, smartphone, tablette. On utilise la majorité du temps la souris pour cliquer sur les icônes de son bureau, de son explorateur de fichiers ou de son explorateur d'application. 
Pourtant, un autre mode d'interaction existe, et il est très puissant :  le CLI (command line interface ou interface en ligne de commande) ! L'intéraction se fait via le terminal de l'ordinateur (vous savez, la fenêtre à écriture blanche sur fond noir aussi froide qu'une porte de prison en Sibérie qui vous fait penser à un virus informatique dès que vous la voyez ?). 

## Le CLI
Pourquoi le CLI quand on a le graphique ? Le CLI comporte plusieurs avantages du fait que ce soit du pur texte : 
-> possibilité de construire des nouvelles actions en combinant des actions qui existent déjà puis d'enregistrer cette nouvelle action,
-> possibilité de chaîner des actions : envoyer les résultats obtenus par un premier traitement dans une 2e commande,
-> possibilité d'exporter les scripts dans des fichier pour les répéter -> reproductibilité de la manipulation.

L'interface graphique n'a pas de fonctionnalités équivalentes, le clic souris nécessite un input humain fort avec un risque d'erreur important. Ces 3 fonctionnalités sont la base minimale à la création de logiciels : un logiciel est un ensemble d'actions simples organisées selon un plan où l'action 1 passe son résultat à l'action 2, plan enregistré dans un ensemble de scripts informatiques. A chaque fois que l'utilisateur ouvre le logiciel, le logiciel s'ouvre et répond toujours de la même façon aux requêtes de l'utilisateur (reproductibilité). Ceci explique pourquoi quand vous téléchargez un nouveau logiciel, vous vous retrouvez avec des pleins de fichiers en plus : ce sont les scripts, chacun réalisant une ou plusieurs actions spécifiques, ainsi que l'ensemble des éléments annexes : images (de logo du logiciel par exemple), scripts pour rendre compatible le logiciel avec votre ordinateur spécifiquement. 

## CLI & graphique : 2 interface d'un même système
CLI ne veut pas dire interagir directement avec l'ordinateur. Le CLI et l'interface graphique sont deux moyens différent de demander à l'ordinateur de réaliser tel ou tel action, qui mettra en place les actions nécessaires à la réalisation de l'action demandés (ouverture de tel ou tel logiciel, calcul mathématique, appeler tel ou tel API).
Exemple : Lancer le logiciel Python : 
- Cliquer sur Python -> ouvre python,
- taper 'python' dans le terminal -> ouvre python.
L'un comme l'autre, c'est deux façons de faire faire exécuter des tâches similaires à l'ordinateur.

C'est pas parce que le CLI n'est pas joli qu'il faut l'exclure, pas de discrimination envers tous les shells de France s'il vous plait 😊 Le CLI a par exemple pour but de gérer des serveurs à distance. Dans ce genre de pratique, une interface graphique est contre-productive : elle prend de la place sur le serveur, qui a alors moins d'espace alloué à faire tourner le site web où l'application qu'on y met. Puis si le CLI s'adresse a un public 'averti' initialement, des gens qui se sont intéressé à manipuler un ordinateur dans ses premières heures puis aux développeurs, il n'en reste pas moins un outil à la disposition de tous, et même un outil qu'il faut à mon avis savoir utiliser tellement il est riche ! Chaque entreprise ou développeur fait le choix de la façon dont son logiciel intéragira avec l'utilisateur définissant ainsi si le logiciel sera plutôt CLI ou plutôt graphique. Par exemple pour un navigateur web, on imagine difficilement une intéraction type CLI, même si des solutions existent. A l'inverse, un bloc-note a une interface très orienté CLI : à l'exception d'enregistrer (et encore on peut le faire avec les raccourcis clavier), absolument rien ne nécessite absolument la souris, même la navigation dans le document se fait avec le clavier.

## Apprivoiser son shell avec wttr.in 
*Disclaimer : code fonctionnel sur cmd (Invite de commandes) Windows.*
Pourquoi pas PowerShell alors que c'est aussi Windows ? PowerShell est fait pour les ordinateurs récents, qui parle un language plus récent. Techniquement, c'est un shell unix-like pour Windows. Le CMD est un langage destiné aux ordinateurs Windows plus anciens, c'est shell DOS. Ce sont donc 2 langages différents l'un de l'autre, donc pas les mêmes commandes. Même si votre ordinateur comprend les 2 languages, mon exemple ne porte que le language du CMD.

Vous voulez connaitre la météo, comment vous faites ?
1. Ouvrir météo France :
-> Besoin d'ouvrir le navigateur, ouvrir météo france.
-> Défaut : besoin de plusieurs actions + temps de chargement (et beaucoup de pub !)
2. Installer une application Windows :
-> Trouver une application dans le store et qui ne présente aucun risque de sécurité (ça peut paraitre évident mais pas si facile, beaucoup d'applications abusent pour vendre vos données par la suite).

Solution miracle : votre bon vieux terminal ! (Nom du programme : *Invite de commandes*)
12 caractères à taper : `curl wttr.in`
-> Affichage coloré
-> Besoin d'aucune installation ni d'aucun espace mémoire.
Vous cherchez un ville spécifique ? Facile: `curl wttr.in/paris` pour paris, `curl wttr.in/las vegas` pour Las Vegas !
L'outil est génial, car il donne la possibilité de connaitre la phase de la lune : `curl wttr.in/moon` !

Pour les plus geek d'entre vous, possible d'obtenir un JSON : `curl -s wttr.in/Amsterdam?format=j1>weather.json`
Voici la doc' pour aller plus loin dans l'outil : https://wttr.in/:help .

**Suivre ses investissements cryptos**
Le créateur du logiciel `wttr.in` a pensé aux cryptophiles en herbe, et a aussi créé de quoi suivre vos cryptos : `rate.sx` ! 
Même fonctionnement : 
```bash
curl rate.sx # Tableau générale
curl rate.sx/BTS # Courbe d'évolution spécifique pour le Bitcoin
```

## Conclusion
Je profite de cet article pour mettre en lumière le créateur des outils `wttr.in` et `rate.sx`, qui maintien ces projets qui vous réconcilieront peut-être avec votre terminal : https://github.com/chubin.
A vous de jouer et d'apprendre a utiliser votre terminal pour tirer pleinement profiter de votre ordinateur 🙂
