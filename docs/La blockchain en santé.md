# La blockchain en santé
*Quelle place pour la blockchain dans notre système de soin actuel ?*

La blockchain a fait grand bruit dans les années 2010. Avec l'arrivée du Bitcoin, le public a découvert cette technologie. Quinze ans plus tard, les crypto-monnaies se sont largement démocratisées, tout le monde sait globalement ce que c'est et de nouvelles blockchain apparaissent régulièrement.
Mais au-delà du monde financier et notamment dans la santé, difficile de citer des applications connues.

La technologie étaient pleines de promesse lors de son explosion en 2010, qu'en est-il aujourd'hui, et notamment dans le domaine de la santé ?

## Différencier la blockchain de la crypto-monnaie
Quand quelqu'un dit blockchain, on pense tout de suite au Bitcoin, comme si c'est deux mots se valaient. Pourtant la différence est de taille.

La blockchain est une technologie de stockage d'informations. Les caractéristiques principales de la blockchain sont : 
- la décentralisation : chaque utilisateur de la blockchain dispose d'une copie complète de l'historique de la blockchain, et lors de l'ajout de nouvelles informations, les utilisateurs sont mises en concurrence pour choisir qui ajoutera un nouveau bloc à son historique et le partagera aux autres utilisateurs, de sorte que l'historique soit à tout moment le même parmi tous les participants,
- l'évolutivité : come décrit dans le chapitre précédent, de nouvelles informations son ajoutées régulièrement.

*Je vois toujours pas exactement la différence claire entre blockchain et bitcoin là !*
J'y arrive ne soyez pas impatient comme ça 🙂 La blockchain est la technologie, la cryptomonnaie un usage. Pour faire un parallèle : la blockchain c'est une Nintendo DS, le bitcoin un jeu de DS. Il existe pleins de jeux de DS différents, donc pleins d'usages différents de cette DS. C'est pour cette raison que différentes cryptomonnaies existent.

**Aparté sur le bitcoin**
Le bitcoin est une monnaie tout comme l'euro ou le dollar, mais dont la génération et la gestion répond à ses propres codes. Tout comme une pièce de 1 euro ne vaut que ce que nous avons choisi collectivement de lui donner comme valeur, c'est pareil pour le bitcoin. Comme c'est une monnaie, sa valeur par rapport à d'autres monnaies fluctue, comme 1 euro vaut parfois 0,7 dollar, parfois 1,3 dollar, un bitcoin peut valoir 22 mille € comme 10 mille €.

*La blockchain est juste une base de données en fait ?* 
Oui, la blockchain finalement c'est une énorme base de données. Pour le Bitcoin, la base de données fait environ 700 Go à ce jour, et l'"information" stockée est les échanges réalisés entre les participants.

D'autres crypto-monnaies stockent par exemple des échanges de monnaies mais aussi des images (c'est ce qu'on appelle les Non fungible token ou NFT).
Cette utilisation de la blockchain est très intéressante car elle ouvre des opportunités inédites pour partager sans risque de falsification des documents ! 

## Quelle place de la blockchain en santé ?

En santé, une utilisation intelligente de la blockchain pourrait donner lieu à plusieurs avantages : 
- Confidentialité : la blockchain pourrait permettre que le patient choisisse qui a accès à son dossier médical, 
- Traçabilité : suivre les personnes ayant accédé au dossier médical d'un patient, tracer les lots et les actions de production de médicaments.

### La blockchain pour la production pharmaceutique
La production de médicament recèle plusieurs challenges : 
- tracer les lots de produits et les actions réalisées, pour remonter la chaine de production en cas de problème,
- assurer la communicabilité de la traçabilité réalisée, pour pouvoir prouver que les actions menées sont les bonnes (si un fournisseur annonce un problème de lot, alors l'industriel doit prouver qu'il a mené les actions adéquates aux autorités et au public, au risque d'être attaqué en justice).

*Pourquoi comunicabilité et pas communication ?*
La communicabilité comprend ici 2 éléments : 
- la capacité technique à partager les informations attendues : ce n'est plus un problème aujourd'hui, tous les professionnels de France ont une adresse mail à minima,
- la capacité humaine à recevoir l'information : pour recevoir une information, une personne doit y attacher un minimum de confiance, sinon la personne refusera de recevoir cette information (exemple : les personnes antivaccins refusent toute information des autorités ou des entreprises aussi scientifique que soit l'information, car ces personnes n'y attachent aucune confiance). Le problème ici est donc : comment apporter une information suffisamment robuste pour les autorités et le grand public puissent y attacher suffisamment de confiance et accepte l'information ?

La blockchain revête un avantage majeur : l'inviolabilité des données. Une fois une donnée dans la blockchain, cette information ne pourra pas être modifiée. Elle pourra être mise à jour, corrigée dans un bloc futur, mais jamais supprimée ni modifiée. Et c'est justement cette avantage qui va permettre aux gens de se fier aux informations de production fourni par l'industriel, pour s'assurer que l'industriel aura bien mis en place les bonnes actions si besoin.

*Okay dans l'idée c'est beau, mais concrètement comme faire ?*
Chaque entreprise productrice de médicament met en place une blockchain dédiée, dans laquelle elle enregistre et les lots de produits utilisées et les actons réalisées.
Grâce à cette blockchain, l'industriel comme le public peut tracer de façon détaillée la création du médicament. La blockchain ne peut être nourrie que par l'industriel, et est ouverte en consultation au grand public.

### La blockchain pour la publication de document officiels

Dans la droite ligne de l'exemple précédent, une application très similaire peut être réalisée pour la publication de documents officiels (pas forcément dans le monde de la santé d'ailleurs).

Prenons quelques exemples en vie réelle : 
*Exemple 1* : en science, certains papiers sont retirés, autrement dit, ils sont démontré comme faux à postériori de leur publication, et sont donc retirés de la publication. Le problème est qu'à part en allant rechercher spécifiquement cet article sur le site de l'éditeur, il est très difficile de savoir si un article a été retiré ou pas. Hors les scientifiques traite de dizaines d'articles par semaine, donc impossible d'aller faire régulièrement le tour de tous les articles qu'ils ont lus et de vérifier s'ils sont toujours d'actualité.

La blockchain serait utilisée ici pour y inscrire les articles scientifiques, et ajouter toute modification éventuelle du papier par la suite (modification d'un paragraphe par l'auteur, retrait du papier, ... ). L'avantage de cette solution est de mettre à disposition une source unique d'information quand à l'état des articles scientifiques. Les scientifiques n'aurait plus besoin de vérifier si un article est toujours d'actualité où d'identifier les articles à retirer, ils pourraient disposer d'un logiciel qui les informe si un papier a été retiré, puis le logiciel retirerait l'article de la banque d'articles du scientifique.

*Exemple 2* : Comment s'assurer qu'un document administratif est bien officiel ? Qu'un document avec un sigle d'entreprise vient bien de cette entreprise et n'est pas un faux ?

La blockchain permet d'héberger des documents, ici les documents officiels. Les utilisateurs de la blockchain pourrait donc disposer de ces documents en sachant que ces documents sont absolument vrai. Techniquement, soit chaque entreprise disposerait de sa blockchain de publication avec un accès en lecture seulement pour le public, soit le gouvernement mettrait à disposition une blockchain regroupant l'ensemble des communications officiels des entreprises.
L'utilisateur aurait alors un logiciel pour suivre le ou les blockchains qu'il souhaite.

Ce 2e exemple se rapproche de l'idée des flux RSS. L'idée du flux RSS est géniale : assurer une information directement du publieur au lecteur de façon asynchrone. Cet exemple comprend exactement cette idée, et la complète par l'inviolabilité des informations permise par la blockchain.

### La blockchain pour l'accès au dossier des patients 

Les données de santé sont une denrée de plus en plus convoitées. Les recherches cliniques et sur données secondaires sont de plus en plus nombreuses, avec des budgets à la clé pour les entreprises intéressants.

Une question se pose donc : comment mettre à disposition des professionnels de santé les données des patients à l'occasion d'un rendez-vous médical ou d'une hospitalisation ou à l'occasion d'un essai clinique, tout en gardant le patient au centre du dispositif, en lui donnant la possibilité de partager ses données uniquement s'il le souhaite et à qui il le souhaite ?

La blockchain peut répondre à cette problématique. En stockant sur la blockchain les données médicales, les choix du patient quant à quelle donnée est accessible à qui, et quelle personne a accédé aux informations de quelle personne, le patient pourra choisir à qui il donne accès à ses informations, puis l'accès ne serait ouvert qu'aux personnes habilités, avec une traçabilité des accès pour vérifier que le dossier n'est pas consulté à outrance par des professionnels de santé par exemple (cas des fuites de données de personnalités connus). 

## Les inconvénients de la blockchain

La taille du bitcoin tourne à ce jour autour autour de 700 Go, et par design ne peut que progresser. Dans le cadre du bitcoin, un nouveau bloc est intégré en moyenne toutes les 10 minutes, pour une taille moyenne entre 1 et 2 Mo. Dans le cas d'une blockchain de dossiers médicaux, la taille des blocs seraient beaucoup plus importantes, même en imaginant une durée entre les blocs beaucoup plus importante, la taille totale de la blockchain sera vite très importante avec une taille de bloc toujours croissante avec le vieillissement de la population. Comme chaque utilisateur de la blockchain doit héberger l'ensemble de la blockchain, la taille totale de mémoire utilisée pour la blockchain tout node confondu serait colossale.
Une autre problématique très liée est le modèle économique de cette blockchain. Comment inciter les personnes (morales ou physiques) qui auront la charge d'implémenter les dossiers dans la blockchain à le faire ? Dans le cas du bitcoin, cette incitation est réalisée de la façon suivante : lorsqu'une personne réalise une transaction en bitcoin, cette personne définit un second montant qui rétribuera le node gagnant de la mise en concurrence. Ainsi les gens ont intérêt à participer à cette mise en concurrence car ils peuvent gagner de l'argent. Dans le cas de la blockchain pour les dossiers médicaux, une solution serait de verser un montant pour chaque nouveau noeud créé, au même titre qu'un remboursement d'acte. 

La blockchain pose aussi un problème écologique : cette dernière nécessite de grandes quantités d'énergie pour refroidir les serveurs qui stockent la chaine et concourent pour un nouveau bloc. 

## Conclusion 
Si les cryptomonnaies vous intéresse à titre de curiosité, je vous recommande le site Coin base *(je n'ai aucune affiliation et ne gagne pas 1 centime à vous en parler, je trouve juste le site bien fait)*. C'est un site qui vend une solution pour investir dans les cryptomonnaies si j'ai bien compris, mais il propose surtout beaucoup de pages explicatives sur la blockchain et son fonctionnement et le Bitcoin. C'est un bon point de départ sur le sujet.
Si les cours des cryptos vous intéresse, je vous suggère mon Votre premier voyage de classe au pays du CLI, vous apprendrez comme consulter les cours des crypto-monnaie et du bitcoin depuis votre ordinateur sans rien installer, et vous apprendrez aussi a connaître un peu mieux votre CLI, vous allez adorer 🙂 Pour investir, comptez pas sur moi je m'y suis pas encore mis, a vous de tracer votre chemin.

Mise en place intelligemment, la blockchain pourrait permettre de répondre à plusieurs soucis de notre système de santé. Trois cas d'usages se dessinent un peu plus distinctement que les autres, et seraient de bons points de départ pour implémenter cette belle technologie qu'est la blockchain dans l'univers de la santé. Mais une implémentation pleinement pérenne nécessite de résoudre certains problèmes : la consommation électrique de la technologie, quoique déjà en cours de résolution avec les recherches sur La fusion nucléaire (j'ai fait un article à ce sujet, je parle justement de ce point bien spécifique !) et l'impact environnemental.


