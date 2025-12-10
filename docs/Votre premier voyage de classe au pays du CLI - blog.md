# Votre premier voyage de classe au pays du CLI - blog
*A la découverte du CLI #2*

Vous avez sûrement déjà entendu parler du terminal d'un ordinateur, mais si vous savez cette petite fenêtre noire moche que tous les hackers utilisent dans les films ? Le terminal et par extension le CLI *(command line interface)* a super mauvaise presse, et pourtant c'est un endroit génial avec pleins de belles choses à découvrir, presque un nouveau pays avec ses us et coutumes, ses traditions. 
Pour vous accoutumer à ce superbe pays, je vous propose donc de partir avec moi en voyage de classe dans ce fabuleux pays !

*Note technique : Je suis sous windows, donc j'utiliserai le terminal et les raccourcis de windows. Pour les linuxiens et autres unixiens : je vous sais, vous avez déjà fait quelques voyages dans ce pays, vous saurez vous en sortir. Pour les Mac-eux, vous vous infligez un handicap dès le départ, c'est courageux 😉 Je rigole bien sûr, le terminal des Mac est très bien et n'a rien à envier aux autres. Une recherche web par ci par là et vous trouverez les alternatives rapidement (pour les raccourcis claviers, essayez à minima de remplacer Win par Commande et Cmd par Terminal).*

*J'ai déjà abordé certains éléments dans mon article du 25 mai : [Apprivoisez votre terminal](https://penseecomplexe.substack.com/p/apprivoisez-votre-terminal). La pédagogie c'est la répétition, je profite donc de cet article pour faire de la pédagogie 😉*

## Un voyage de classe, ça se prépare ! Valise, train, c'est parti !

Bienvenue à ce merveilleux voyage de classe ! Pour cette aventure, je serai votre animateur et guide de voyage ! Vous allez voir on va passer de super moments.

Comme tout nouveau pays, il faut s'y rendre. On est des petits chanceux, ici même pas besoin d'avion, de bateau ou de voiture. Allumez votre ordinateur, connectez vous à votre session, et c'est bon, on y est ! 

En tant que guide, ma première tâche est de vous apprendre à trouver un autochtone. Plusieurs solutions : 
- la rapide : sur votre clavier, appuyez sur Win + R. Une petite fenêtre va s'ouvrir du nom de *Exécuter*. Tapez alors *cmd* puis appuyez sur *Entrée*
- la standard : cherchez dans vos applications *cmd* et ouvrez là (pour les fans de raccourcis clavier : Win + Q pour ouvrir une zone de recherche d'applications)
Une petite fenêtre a écriture blanche sur fond noir avec une barre verticale qui clignote vient de s'ouvrir et vous regarde fixement ? Promis c'est pas un animal sauvage, c'est un autochtone ! Vous avez trouvé un autochtone, c'est une première réussite non négligeable de votre voyage, bravo fier explorateur ! 

Courte histoire de cet autochtone, pour la raconter au copain quand vous rentrerez : le CMD, de son nom complet local *command* et de nom français *interpréteur de commande*, est le Shell de Windows. Avant l'arrivée des interfaces graphiques des ordinateurs, du temps des dinosaures préhistoriques (j'exagère, c'était les années 1970), les utilisateurs des ordinateurs utilisaient principalement le clavier pour interagir avec l'ordinateur : ils écrivaient une commande puis l'envoyaient à l'ordinateur qui exécutait la commande. Un peu comme aujourd'hui on double clique sur une application pour l'ouvrir, à l'époque on tapait le nom du logiciel puis l'ordinateur l'ouvrait. On faisait à peu près la même chose, mais au clavier ! C'est ça le CLI, c'est l'interaction avec l'ordinateur via des commandes qu'on envoie, qu'on oppose au GUI (Graphique User Interface) qui sont nos interfaces jolies et colorés qu'on connait.
Le CLI demeure encore aujourd'hui essentiel à bien des égard ! La gestion de serveur à distance par exemple : installer un GUI sur un serveur, ça prend de la mémoire et du processeur inutilement, donc on utilise le CLI pour interagir avec le serveur en laissant un maximum de mémoire et de processeur pour l'usage *serveur*. Pour les développeurs, le CLI permet de créer des scripts pour réaliser un ensemble de commandes d'un coup qui demanderait en GUI de faire plusieurs clics à différents endroits, c'est un gros gain d'automatisation.

## Le premier contact 👽
C'est l'HEURE, LE moment du premier contact avec cet autochtone si bizarre ! Et justement, nous allons faire vos premiers échanges avec cet autochtones !

Pour un premier contact, le mieux est de dire bonjour. Comment faire ? Tapez `echo 'Hello world!'`, et vous allez voir que l'autochtone va vous répondre *Hello world!*. 
En réalité, vous dites à votre ordinateur d'écrire (commande `echo` ) la chaîne de caractère 'hello world!'. Marche avec n'importe quoi d'autre, vous pouvez même lui faire faire la vache `echo 'Meuuuuuuuuuh!'`

Premier contact ✅ Mais faire faire le perroquet à l'autochtone va pas vous permettre d'aller très loin ... La ville est grande, et vous souhaitez en savoir un peu plus sur la ville (ici, la ville correspond au dossier dans lequel vous êtes actuellement, à l'ensemble des éléments inclut dans ce dossier, comme quand vous êtes dans votre explorateur de fichier graphique). Je vais donc vous apprendre à demander votre chemin (c'est normal en tant que guide 🙂) :
- `dir` : demande à l'autochtone de lister les fichiers et les dossiers dans le dossier courant (le dossier courant est le dossier où on est actuellement)
- `tree` : lister les fichiers, dossiers et sous-dossiers a partir du dossier courant
- `cd ..` : remonter au dossier parent (le dossier dans lequel est contenu le dossier courant)
- `cd ...dossier...` (remplacer ...dossier... par le nom du dossier que vous voulez ouvrir, comme dans l'interface graphique) : ouvrir le dossier souhaité.
Regardez avec attention ce qui se trouve avant la barre qui clignote, car quand vous aurez mémorisé les liens (l'enchaînement de dossier), vous pourrez vous y téléporter (c'est pas beau la puissance du CLI) ! 
Exemple : Avant la barre qui clignote, vous observer ça : `C:\Users\penseecomplexe\Documents`. Quel que soit votre localisation en ville, vous pouvez vous téléporter dans ce dossier en tapant : `cd C:\\Users\\penseecopplexe\\Documents` (ajouter *cd* au début et doubler les antislashs) et paf ! Vous vous êtes téléporté ! 

L'autochtone est pointilleux : une majuscule c'est une majuscule, un espace c'est un espace, si vous vous trompez il ne va pas savoir de quoi vous parlez ! 
Il se peut aussi que l'autochtone soit bavard, très bavard ! Vous avez une solution pour lui couper la parole (arrêter l'exécution d'un commande une fois lancée) : touches Ctrl + C et l'autochtone repasse en mode écoute, attendant votre prochaine commande.

En tant que guide, je trouve que j'ai déjà bien bossé, je fais une pause 🍹🏖️

Bon, je culpabilise déjà de vous laisser seul ... 
Let's go pour apprendre à parler l'autochtone ! Pour mieux échanger avec l'autochtone, il faut apprendre son langage, et justement, l'autochtone est toujours content de vous lister tous les mots qu'il connait !
Tapez `help` et vous aurez le dictionnaire autochtone local ! Vous obtenez alors un dico de l'ensemble des mots qui existe et une courte description. Pour en savoir plus sur 1 mot spécifique, tapez `help ...commande...` (remplacer ...commande... par la commande que vous souhaitez). Vous pouvez même noter tout ce que vous dit l'autochtone pour le réouvrir plus tard : `help > output.txt`, qui permet d'enregistrer ce que vous dit l'autochtone dans le fichier texte output.txt dans le dossier courant. Vous avez maintenant un petit dico à emporter partout, et si vous l'oubliez, il suffit de redemander à un autre autochtone.

Comme je suis un super guide, je vous est même prévu un petit aide mémoire :
```bash
echo 'Hello world!' # Afficher le texte hello world!

dir # Afficher le cotenu du dossier courant
tree # afficher les fichiers, dossiers et sous-dossiers du dossier courant
cd .. #Remonter dans le dossier parent
cd ...dossier... # Ouvrirle dossier cité : cd Document

help # Afficher l'ensemble des commande disponibles
help ....commande... # Affiche l'aide pour une commande spécifique : help cd
help > output.txt # Enregistrer la sortie dans le fichier texte output.txt dans le dossier courant : help cd > output.txt
```

## S'immiscer dans la vie locale
Vous connaissez un peu mieux la ville, ses quartiers, son plan. Mais la beauté d'un endroit ne se mesure par à son plan 2D, mais la richesse de sa vie locale ! C'est donc le moment d'explorer la vie locale, d'explorer des nouveaux endroits et de travailler votre autochtone.

Les autochtones savent tous quelle météo il fera pour les 2 prochaines semaine et ça partout ! Pour leur demander le temps, tapez `curl wttr.in`. Une ville en particulier ? Ils savent aussi : `curl wttr.in/Las vegas`. Ils savent même les phases de la lune : `curl wttr.in/moon`. Vous êtes plutôt crypto ? Les autochtones aussi : `curl rate.sx` ! Vous avez investi dans le bitcoin, les autochtones peuvent vous aider à suivre le marché : `curl rate.sx/BTC`. C'est dingue toutes les ressemblances que vous avez vous et l'autochtone 🙂 

Comme les autochtones sont les gens accueillants, ils vous autorisent à apporter votre propres modifications à leur espace : installer vos propres logiciels. Vous savez le faire via le store et la souris, mais c'est pas trop la culture du coin, ici c'est le CLI (et pas 'ici c'est Paris !' pour les rebelles du fond du bus !). Pas de soucis, avec Scoop, vous allez pouvoir faire tout ça ! Pour installer scoop, il va falloir Googler un peu (il faut bien faire une pause dans ce monde sans couleur et sans graphisme 🙂 je vous donne même le lien en tant que guide génial : https://scoop.sh/).
Une fois scoop installé, vous pouvez installer python `scoop install python` et lui faire dire bonjour : `python -c "print('Hello world, I'm python 🐍')"`. Vous pouvez même faire parler des vaches : 
```python
python # vous devrait voir '>>>' apparaitre, ça veut dire que vous parler à l'autochtone python, et pas un autochtone lambda. C'est un privilège ! 
pip install pipx
pipx install pycowsay # Installe des librairies nécessaires
cowsay "Meuuuuuuuuh!" # Faire parler la vache
```
Qui peut dire qu'on sait pas s'amuser chez les autochtones maintenant ? 🙂

Vous pouvez aussi suivre toute la ville d'un œil : `scoop install btop` puis `btop`. Votre petite fenêtre noire va se transformer en vrai tableau de bord de capitaine de toute l'activité sur votre ordinateur !
Pour quitter ce tableau bord, tapez sur Ctrl + C.

Vous pouvez installer et parler à des IA avec Ollama :
```bash
scoop install ollama # Invoque le super-autochtone : selon qui sait faire parler des IA ! 
ollama serve # Le super-autochtone rentre en trance, et pourra prendre possession d'autres autochtones pour vous parler. En réalité, cette commande lance un serveur sur lequel l'IA avec laquelle on voudra échanger tournera
```
Initiez une discussion avec un nouvel autochtone (ouvrez une nouvelle fenêtre cmd), et tapez `ollama install qwen3:0.6b`  pour installer cette IA, puis `qwen3` pour commencer à parler avec cette IA.
Une fois que vous avez fini de discuter, vous avez juste à partir (fermer les 2 fenêtres utilisées), et tout redeviendra normal, la vie reprendra son cours. 

J'ai consacré une article à Scoop, pour expliquer ce que c'est et les autres solutions sur le marché : [Scoop : un gestionnaire de logiciel Windows très utile !](https://penseecomplexe.substack.com/p/scoop-un-gestionnaire-de-logiciel). Si vous vous demandez pourquoi il faut installer scoop alors que vous avez déjà installé des logiciels via le store ou directement via un installeur, je vous conseille vivement cet article pour comprendre la nécessite d'avoir un bon logiciel de gestion de package.

## A vous de tracer votre route !
Vous voici arrivé au bout de mon apprentissage petit bambou, je n'ai plus rien à vous apprendre, je suis si fier de vous 🥹 
Vous avez les clés en main ! A vous maintenant d'être malin et d'assembler a votre guise tout ce que vous avez appris pour générer des actions soit simples (1 commande existante) soit complexe de plusieurs commandes. Grâce au quelques commandes citées, vous savez naviguez (et même vous téléporter !). Grâce a *help*, vous savez demander de l'aide si nécessaire. Grâce a *scoop*, vous pouvez même installer des nouvelles applications dans votre ville digitale !
Et puis vous êtes pas tout seul tout seul, vous avez quand même le droit de googler si besoin, voir même d'utiliser ChatGPT, je vous autorise pour cette fois 🙂

Bref, le CLI c'est la vie ! Et maintenant, a votre imagination de jouer !





