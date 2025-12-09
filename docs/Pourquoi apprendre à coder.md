---
Start_date: 2025-03-07
End_date: 
---
## Plan
Pourquoi apprendre à coder est encore très utile aujourd'hui et dans notre vie ? 
A l'heure où l'IA peut tout faire, apprendre a coder ne semble plus servir a rien. On parle de plus en plus de vibe coding comme de LA solution qui nous permettra de tout développer sans jamais apprendre à coder, mais est-ce une solution vraiment pérenne ? (Si vous ne savez pas ce que c'est le vibe coding, je vous renvoie vers mon article sur le sujet [[Vibe Coding la dernière couche d'abstraction en programmation]], qui devrait vous indiquer mon camp sur la question qui nous occupe 😉).

### *Coder* : une boule a facettes
Avant de se demander pourquoi c'est important de code, que veut dire 'coder' finalement ?
Pas de bonne définition sans [Larousse](https://www.larousse.fr/dictionnaires/francais/coder/16889), je suis donc aller y voir la définition : 
1. Procéder au codage d'un message ; encoder.
2. Appliquer un code à des données ; écrire un programme pour ordinateur.

Dans la droite ligne de la définition 2 *écrire un programme pour ordinateur*, ce que j'entends par 'coder', c'est créer un script répétable et partageable. Pas de notion de finalité (web, logiciel, jeux vidéo) ni de technologie (Svelte pour le web, C++, java, python, Cobol, ... ). 

### Le premier pas : le terminal !
Il est possible de coder sans rien installer sur son ordinateur en utilisant le shell de son ordinateur. Le shell, c'est déjà du code ! Le shell de l'ordinateur, accessible via le terminal donc avec une interface en ligne de commande (CLI), est une 'langue' dédiée permettant d'interagir avec son ordinateur et de créer des scripts répétables et partageables (dans la limite des OS je suis d'accord, mais partageable quand même). Quand on parle de 'code', on entends souvent des langages de programmation type Python, C++, Java, ... Tout comme le python a besoin qu'on apprenne à 'parler' le python pour l'utiliser avec la possibilité de créer des scripts, le shell de notre ordinateur nécessite d'apprendre une langue et permet de créer des scripts (pour enfoncer un peu plus le clou que le shell, c'est déjà un langage de programmation 🙂). Sous windows, plusieurs shells sont disponibles : cmd avec des scripts .bat, powershell et .ps1.
Pour en savoir plus sur le shell windows et le CLI, apprendre ce que c'est et commencer à l'utiliser, j'ai fait 2 articles : [[1_Ma Créa 🎨/1_Créa blog 🎨/1_Idées/Apprivoisez votre terminal - article]] et [[Votre premier voyage de classe au pays du CLI - blog]].

Coder ne se limite bien sûr pas au terminal. On peut coder des applications smartphone avec [[Flutter]], faire des analyses en 'code graphique' (en clic-bouton) avec [[KNIME]] ou des flux de travail IA avec [[n8n]]. Tout ça permet de générer des scripts répétables et partageables.

Finalement coder, c'est créer une 'recette de cuisine' (un script) et l'utiliser au travers de l'outil associé pour créer de nouvelles choses (logiciels, site web, ...). Et pour faire ça, c'est pas le choix d'outils qui manque ! 

### Pourquoi investir du temps à apprendre à coder ?
**Donner corps à vos idées**
Nous avons tous des bonnes idées en informatique, des choses que nous aimerions mettre en place. Coder nous permet de rendre concret nos idées.
Vous voulez développer un site web basique ? Un peu de HTML et CSS et vous pouvez vous lancer avec des sites déjà plutôt joli : https://www.csszengarden.com/ ou https://a-k-apart.com/gallery/. 
Vous voulez réaliser une analyse de données financières par exemple ? Un peu de python et vous pouvez réaliser vos analyses, faire vos propres calculs et réaliser vos propres visualisations de données.
Je suis d'avis que tout ce que l'homme peut imaginer dans l'univers digital est techniquement faisable avec du code informatique. Certains projets demanderont juste plus de temps que d'autres. 

Donc lancez vous dans le code, vos idées vous remercierons ! 

**Reproductibilité & automatisation** : 
Grâce à un script, pas besoin de repasser par le code pour refaire un ensemble d'actions déjà connues, juste besoin de relancer le script pour que la 'recette' qu'il contient soit réexécutée. Rien d'autre que le code ne permet de créer de nouvelles 'recettes' informatique partageable. Une autre solution pourrait être des macros : on enregistre des déplacements de souris et l'endroit où on clique, mais ce n'est absolument pas partageable : il faudrait que tout le monde ait le même bureau avec les mêmes icônes. Seul des scripts, contenant du code, permettent de créer nouvelles 'recettes' pas encore disponible. Cet ensemble de nouvelles 'recette' créera ensuite un nouveau service/logiciel.
Exemple : 
- avant Google maps, Google maps n'existait pas, donc Google a du passer par du code pour créer un nouveau service, impossible par la voie graphique,
- Facebook : Mark Zuckerberg n'a pas créé Facebook avec sa souris, il a écrit du code pour créer un service nouveau. Il est reparti de langages de programmation déjà existant et des fonctions disponibles (des scripts écrit par d'autre développeurs) pour créer son propre usage.

**Participer au développement du monde** : 
Les jeux vidéos, les logiciels, même les OS, ils ne sont finalement qu'un ensemble de scripts, certains d'orchestration, certains de réalisation d'actions, certains d'affichage (allumage, écran de chargement, ... ), qui se répètent quand on en a besoin. 
Les logiciels que nous avons aujourd'hui sont possible grâce aux développeurs d'hier. Chaque nouveau logiciel aujourd'hui est basé sur des scripts d'hier, et c'est en utilisant des scripts d'hier d'une façon nouvelle qu'on peut créer des logiciels plus puissant et plus complexe pour les usages d'aujourd'hui.
Exemple : imaginez un monde sans partage des packages python contenant les scripts nécessaires à son fonctionnement. Sans ces scripts, pas de python qui ne tiennent, donc pas d'analyse de données et pas d'IA non plus. Le premier pas semble microscopique en effet, mais les impacts sont réels.

Coder permet finalement de faire avancer d'un pas le monde actuel, d'un pas microscopique on est d'accord, mais d'un pas quand même.

**Une étape essentielle vers la souveraineté de ses données**
La souveraineté de ses données correspond au fait de posséder légalement ses données. Le pendant informatique de la souveraineté des données est d'utiliser des outils qui évite que nos données soient partagées absolument à tout le monde. Les fuites de données des entreprises sont de plus en plus fréquentes, certaines entreprises utilisent nos données pour entrainer leur IA; nos données valent de l'or. Soyons souverain de nos données, pour éviter de payer doublement nos outils technologiques (entrainement des IA sur nos données, puis nous payons pour avoir accès à cette même IA), pour garder notre vie privée vraiment privée. 

Les logiciels qui ne partage pas nos données sont bien souvent les logiciels open sources. Si vous n'avais jamais fait attention à cet univers spécifiquement, le monde de l'open source est un monde absolument génial d'innovations avec la mise a disposition d'outils absolument fabuleux par des développeurs motivés. Lorsqu'on utilise ces logiciels, savoir coder est très pratique : pour pouvoir utiliser les CLI de ces outils et pour savoir se débrouiller quand on rencontre des petits bugs. 
Pourquoi se tourner vers l'open source alors que les logiciels payants marchent bien ? Les outils open source sont au moins aussi puissant que les outils payant, mais aussi gratuit et bien souvent respectueux de la vie privée !

**Découvrir/approfondir la réflexion algorithmique**
L'ordinateur a une logique mathématique : objet + action = résultat. Et quand on code, il faut s'y plier : il faut organiser notre code en ensemble d'actions claires pour arriver à notre résultat. Il faut être capable de tracer une route entre l'état actuel et l'état visé, d'identifier les actions par lesquels on passera. 
Cette logique, nous en avons besoin dans notre vie de tous les jours : "pour atteindre mon objectif, je vais devoir faire ça en 1 pour obtenir ..., puis ça en 2 pour obtenir ..."* . Cette logique algorithmique développe notre capacité à se projeter dans le résultat et à créer un chemin mental vers ce résultat. C'est un des fondements du développement personnel : être capable de se projeter dans la vie qu'on souhaite et définir le chemin pour y arriver.

Finalement coder, c'est presque du développement personnel 🙂

**Mieux connaitre la façon dont fonctionne son ordinateur** : 
Nous dépendons tous de l'informatique : ordinateur pro et perso, smartphone. Même si on ne travaille pas dans l'informatique, comprendre d'où vient un problème réseau, monitorer son ordinateur, automatiser une action répétée, ce sont des besoins que nous avons tous car nous utilisons tous les jours un ordinateur. Ce sont aussi des problèmes que nous ne pouvons adresser que par le code (et le premier qui me parle du diagnostiqueur réseau de Windows, je lui rigole au nez : qui a déjà compris quelque chose à ce truc qui tourne longtemps pour vous dire à la fin que tout va bien sans aucune explication de rien ?).

Un langage de programmation, c'est une langue pour parler à son ordinateur. C'est comme parler une langue étrangère, mais avec un ami avec qui on passe 8 heures au bureau et plus de temps encore dans sa bulle personnelle. Passeriez-vous 10 heures de votre journée avec la même personne parlant une langue étrangère sans jamais vous dire qu'il fallait apprendre les rudiments de son langage ?

L'ordinateur est un ami puissant, il peut : 
- Gérer vos fichiers et vous permettre d'accéder aux services en ligne (les impôts comme les boutiques en ligne),
- Vous donner accès au dernières innovations technologiques et dernières nouveautés (le dernier modèle d'OpenAI, la dernière vidéo de MrBeasts ou de Anyme).
C'est un ami avec ses forces et ses faiblesses : 
- L'ordinateur est un ami un peu bête : il lui faut des routines simples. Cela nous force à structurer nos idées de façon précise, à être au clair sur ce qu'on souhaite.
-  Coder nécessite de connaitre au moins un peu le fonctionnement d'un ordinateur ou d'un smartphone. Cette même connaissance est directement mise à contribution quand on a un problème avec ce dispositif, car on peut alors se débrouiller pour résoudre le problème.

**Monter la pente la 1 fois, en profiter tout le temps**
Les règles des langages de programmation sont souvent les mêmes au sein d'une même finalité (web, logiciel, ... ). Pas besoin de tout réapprendre de 0 si vous passez d'un framework à l'autre pour le développement web ou bien d'un logiciel à l'autre pour l'analyse de données, les grandes idées du langage sont souvent les mêmes car les communautés et les développeurs des différents logiciels baignent tous dans une même culture technique. 
Exemple : Typage statique/dynamique d'une variable : dans certains langages de programmation, le typage est dynamique : une même variable peut être un nombre puis devenir du texte. Dans d'autres langages, le typage est statique : si la variable est un nombre à sa création, elle restera un nombre tout le temps.
Le typage dynamique diminue la complexité du langage en offrant au développeur la possibilité de jouer librement avec les variables, mais cause plus souvent des problèmes (une fonction attend une variable de type nombre, elle reçoit la variable ne type texte). Le typage statique rend le langage plus exigeant car il ne faut pas se tromper sur le contenu de la variable quand on crée son script, mais supprime le problème potentiel de mauvais typage de la variable (si la variable est un nombre, elle restera nombre donc pas de problème de type). 
Maintenant, vous savez ce qu'est le typage dynamique et statique et vous pourrez l'appliquer à littéralement tous les langages de programmation que vous verrez par la suite. Appris 1 fois, réutilisable plein de fois 🙂

### Les fausses barrières les plus courantes
Quand on parle d'apprendre à coder, on retrouve souvent certaines barrières : 

**Il y a les IA, tout le monde vibe code maintenant !**
Grâce à l'IA, on peut maintenant demander en quelques phrases le programme qu'on souhaite, et l'IA fera le travail.
Mais coder, c'est pas juste écrire un code, c'est aussi comprendre et connaitre où mettre le code pour qu'il fonctionne (pour une appli smartphone, pour un site web), c'est comprendre les contraintes techniques de l'environnement de destination pour adapter le code (faut-il prévoir une base de données pour gérer les comptes utilisateurs ? Ai-je le choix de la nature de la base sur mon site ?). Pour des projets un peu poussé, on code rarement seul, il faut donc aussi pouvoir coopérer sur le code, en suivre les versions de travail, suivre ce qui est publié de ce qui est en cours de travail. On ne code pas tant pour l'amour du code que pour des humains à la fin. Donc concevoir son application, c'est aussi un travail humain que de se mettre à la place de l'utilisateur pour lui offrir une expérience riche et stimulante.

L'IA pourra sortir un code qui correspond à votre demande, mais elle ne saura pas se mettre à la place de l'utilisateur (elle saura au mieux faire une synthèse de la conception mainstream de votre catégorie d'application). L'IA ne maitrisera pas la destination de votre code car c'est vous qui le savez, pas elle. 
Et puis je passe tous les risques cyber de l'IA : OpenAI comme Deepseek utilisent tout ce que vous leur dites pour entrainer leur modèle, Deepseek qui peut partager vos informations au gouvernement chinois dans le cadre de la loi obligeant les entreprises chinoises à partager au gouvernement les données hébergées en Chine si le gouvernement chinois leur demande, le risque carrément de modèle frauduleux qui cache un malware.

**Ca prend du temps !**
Coder n'est pas inné. Comme il faut apprendre à l'école le français pour dialoguer avec d'autres gens, il faut apprendre une 'langue' pour parler avec son ordinateur. Par chance, certains langages sont bien moins complexes que le français, le cout réel de l'apprentissage d'un langage de programmation tient surtout à la complexité des projets que vous avez a en tête.
Exemple : 
- Identifier si notre ordinateur arrive bien à se connecter à internet : 1 commande sous Windows : `ping /t google.com`
- Créer un nouveau framework web : à minima 400 lignes de code (projet [Skeleton](http://getskeleton.com/))

Coder, ça fait apprendre pleins de choses super intéressantes, des concepts géniaux et découvrir des communautés de développeurs géniales d'idées. Même si le bout du chemin parait loin, le chemin est magnifique. Et puis c'est comme tout : ça prend du temps, il faut en faire un peu chaque jour. Si ça peut vous aider, je suis passé par là et je trouve fou que tout soit possible une fois qu'on se débrouille un peu !

**Okay okay, mais par où commencer ? Quel langage ?**
Je vous recommanderais le Python : c'est une langage qui peut servir à tout donc super pour commencer et pouvoir aller d'idée en idée sans avoir à ré-apprendre un langage chaque fois.
Quant à où commencer ? Il y a un océan de livres Python pour commencer, on peut commencer par de l'analyse de données comme par des jeux vidéos, à vous de voir ce qui va assez vous motiver assez pour vous permettre de pratiquer régulièrement ! 

Quelque chose que j'ai appris avec le temps : il n'y a jamais d'outil parfait pour faire quelque chose, il y a toujours plusieurs choix d'outil. Au lieu de chercher l'outil parfait, il faut mieux chercher l'outil le plus adapté à notre besoin.
Si la nuance semble fine, combien d'articles chaque année disent que Python c'est fini, et que l'outil parfait c'est Scala/Zig/Rust. La réalité, c'est que Python marche toujours très bien car tout le monde n'a pas besoin d'optimiser la performance de son application ou paralléliser ses traitements. Python répond le mieux au besoin donc les gens l'utilise. 
Beaucoup de gens font du python aussi parce que les ressources sur le sujet sont infini, donc les gens se forment à ça plutôt qu'au logiciel d'ultra-expert avec très peu de formation. J'intègre donc la capacité à se former au langage dans le besoin de la personne.

### Conclusion
Premièrement, coder c'est pas un ensemble homogène, plutôt un écosystème de langages et d'outils, chacun avec ses avantages et inconvénients. Chacun code à sa manière, dans son domaine, et fait au final avancer le groupe : le dev web qui crée un nouveau framework et qui le publie, le développeur linux qui crée une nouvelle feature de l'OS, un créateur de jeux vidéo qui utilise et publie le dernier moteur de jeux vidéo pour créer un jeu particulièrement développé ... 
Dans mon cas, j'ai mon article medium pour créer un portfolio. L'article contient une 'recette' utilisant des outils préexistants pour aider les gens a présenter leur travail pour en démocratiser l'usage. Cette article est déjà un script utilisable et partager pour créer son propre portfolio. 

Aujourd'hui, tout est programme (ensemble de script) : MineCraft est un programme, outlook est un programme, Linux est un programme. Rentrer dans ce monde, c'est pouvoir concrétiser ses idées numériques les plus folles et découvrir un univers de projets déjà réalisés et futurs absolument passionnant ! 

Alors venez, rejoignez le coté *codeur* de la force ;)
