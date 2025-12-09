---
Start_date: 2025-04-22
End_date: 2025-05-07
tags:
  - projet/format/article
  - projet/etat/done
  - projet/plateforme/sybstack
notes liées: "[[Scoop]]"
---
**Objectif initial** : 
**Critères de réussites du projets** : 
**Points d'incertitude** : 

## Scoop : un gestionnaire de logiciel Windows très utile !
*Qu'est-ce qu'un gestionnaire de package, et pourquoi nous devrions tous utiliser un gestionnaire de package ?*

*Note : Cette article traite de l'importance d'avoir un gestionnaire de package et des avantages d'en avoir un. Scoop est un gestionnaire de package Windows. Sur Linux, les gestionnaires de package sont intégrés aux distros, donc lisez l'article pour les idées et demandez à Google quel est le gestionnaire de package de votre distro si vous ne l'avez pas encore identifié (même si je doute que vous soyez sous Linux et que vous n'utilisiez pas déjà votre gestionnaire de package 😉). Pour Mac, LE gestionnaire de package est brew, et les arguments généraux pour installer et utiliser brew reste exactement les mêmes que pour Scoop (les 2 solutions varieront évidement quant aux fonctionnalités spécifiques).*

*Disclaimer : je n'ai aucune sponsorisation pour cet article, par aucun des logiciels cités ni aucune autre personne commerciale, morale ou physique.*

**Pourquoi un gestionnaire de package ?**
Windows a un énorme défaut : mettre à jour les logiciels est super galère. Soit il faut un logiciel tierce mais dont l'efficacité n'est pas toujours évidente, soit on a de la chance et on peut mettre à jour via le Store, soit il faut carrément re-télécharger et ré-installer le logiciel sans être sûr qu'il n'y aura pas de conflits, de doublon d'installation ou de nettoyage de l'ancienne version par la nouvelle. Tout ceci cause un problème majeur : la sécurité du poste de travail ! La mise à jour des logiciels est d'ailleurs un pilier fondamentale de l'[[Hygiène digitale]].  
Exemple : l'attaque Wannacry de 2017, qui avait paralyser le monde entier alors que Microsoft avait publié le correctif, mais les gens ne l'installait pas (pour en apprendre plus sur cette histoire : [Wikipédia](https://fr.wikipedia.org/wiki/WannaCry) ou la super [vidéo](https://www.youtube.com/watch?v=1qNHnUyBzXU) de overflOw).

Pourtant, une autre solution existe, une solution gratuite pour les particuliers qui permet d'installer, de mettre à jour et de désinstaller des logiciels rapidement et facilement, ce sont les gestionnaires packages Windows !

**Scoop : LE gestionnaire de package Windows**
Plusieurs gestionnaires de packages sont disponibles sur internet, et disposent chacun de leurs spécificités propres. Certains petits projets existent tel que [RuckZuck](https://ruckzuck.tools/), [Windows Remix](https://www.windowsremix.com/), [WSCC](https://www.kls-soft.com/wscc/), [QuickInstaller](https://www.quickinstaller.net/). Ces projets ne sont quasiment jamais cité dans les articles web, et donc moins connu donc que les 4 solutions ci-dessous. 

Je vous présente ici les 4 plus courants et plus répandus : 
- [Ninite](https://ninite.com/) : idéal commencer avec un ordinateur neuf rapidement :
	- + : 
		- Installation facile et sans logiciels pub de plusieurs logiciels en même temps
		- Installation native du logiciel (utilise l'installeur du logiciel pour installer le logiciel)
	- - : Ne sert qu'à l'installation des logiciels, une fois installé Ninite ne permet pas de mettre à  jour ou de désinstaller des logiciels
- [Chocolatey](https://chocolatey.org/) : la référence ... un peu trop invasive
	- + : 
		- Enormément de logiciels dispos
		- Gestion CLI et graphique complète 
	- - : 
		- Demande de droits d'accès à l'ordi très importants ([page d'installation](https://chocolatey.org/install) : demande à configurer les stratégies d'exécution PowerShell à son plus bas niveau de sécurité)
		- Dangereux a supprimer de l'ordinateur (notez le nombre d'alertes sur la [page](https://community.chocolatey.org/courses/installation/uninstalling) pour désinstaller le logiciel)
		- Sécurité des packagés compliqués ([page dédiée](https://docs.chocolatey.org/en-us/information/security/)) et géré par Chocolatey
- [Scoop](https://scoop.sh/) :
	- + : 
		- Installation portable -> les logiciels installés et Scoop lui-même ne laissent pas de trace sur ordi après désinstallation. L'utilisation du logiciel devient ainsi beaucoup plus pérenne : nous pouvez essayer plusieurs navigateurs webs par exemple sans avoir peur de ralentir l'ordinateur
		- Demande de paramétrer les stratégies d'exécution de scripts PowerShell à un niveau de sécurité plus important que Chocolatey, c'est donc une couche en plus qui protégera votre ordinateur par la suite
		- Comme Ninite, installation du logiciel par l'installeur natif du logiciel. A contre pied de Chocolatey où la sécurité d'un package est géré par Chocolatey et donc qu'il faut leur faire confiance, Scoop utilise l'installeur natif du logiciel et permet d'identifier d'où Scoop extrait ses scripts de logiciel grâce à `scoop home <package>`,
		- Gestion complète par le CLI, le CLI retrouve donc ici son rôle de centre de contrôle et peut agir sur toute la durée de vie du logiciel (installation, update, désinstallation)
	- - : Certains logiciels type Docker (pour les codeurs) ou Filmora (pour le montage) ne sont pas disponibles
- [Winget](https://github.com/microsoft/winget-cli) :
	- + : Solution de Microsoft
	  NB : [winstall](https://winstall.app/) : surcouche graphique de WinGet, pour profiter des repos WinGet graphiquement.
	- - : 
		- Utilise 2 registres différents : les repos WinGet (disponible par Winstall) et les applications du store Windows
		- Sources des logiciels pas toujours évidente a identifier
		- Système d'ID de logiciel et de nom logiciel vite chiant à utiliser

NB : je parle souvent du CLI. J'ai prévu d'en faire une série d'articles, pour vous montrer que le CLI, c'est aussi facile que le bureau graphique, personne n'a pris le temps de vous montrer c'est tout ! De plus, faire de l'hygiène digitale sans maîtriser le CLI me semble difficile, car le CLI permet beaucoup de choses que le graphique ne permet pas.

Pour linux : si vous utilisez linux, vous connaissez déjà très probablement le concept de Scoop et utilisez la gestionnaire de packages de votre distro. Pour Mac : alternative Scoop = [brew](https://brew.sh/).

**Comment j'utilise Scoop ?**
Avec Scoop, j'ai installé :
- Brave : navigateur l'un des plus respectueux de notre vie privé ([petite vidéo](https://www.youtube.com/watch?v=5ImSqgvg9UU) pour les plus curieux)
- 7zip : LE 7zip que tout le monde a, mais en version portable et appelable depuis le CLI
- uv : pour les codeurs python, la dernière arme secrète de gestion des packages
- neovim : je voudrais me remettre à vim pour fluidifier l'édition de documents dans le terminal et éviter d'avoir à ouvrir une fenêtre à chaque foi
- [ollama](https://ollama.com/) : si l'IA vous intéresse même de loin, c'est LE logiciel indispensable. Grâce à scoop, l'installation est portable, donc je peux l'utiliser et échanger avec des modèles sans laisser de trace sur mon ordi
- zeal : c'est un logiciel de documentation informatique offline. je vous renvoie vers mon propre [article](https://medium.com/data-science-collective/mastering-python-docs-turn-the-official-documentation-into-your-secret-weapon-b682ba9d9530) pour en découvrir toute la portée
Quand j'oublie mes logiciels installés : `scoop list`. Quand j'oublie les commandes disponibles et les logiciels associés : `scoop shim list`.

Grâce à Scoop, je peux appeler mes logiciels depuis PowerShell (exemple : `brave` -> lance brave, `7zip`), mon bureau et ma barre inférieures sont donc beaucoup plus épuré sans perte d'efficacité, je mets maintenant juste une icône vers PowerShell. 

**Comment fonctionne Scoop ?**
Scoop est un script que vous installé sur votre ordinateur, doublé d'un repo GitHub entretenu par l'équipe de Scoop qui va lister les logiciel disponibles et les liens vers ces packages. 
Pour chaque logiciel, Scoop dispose d'un 'manuel' de logiciel : le nom, la version, le lien vers le repo qui stocke l'ensemble des scripts du logiciel, et le lien vers le script pour initier l'installation.
Vous pouvez retrouvez ces infos par 2 commandes : `scoop info <package>` -> informations du packages, et `scoop home <package>` -> ouvre la page web où sont stockés tous les scripts du logiciel demandé. Grâce à cette dernière commande, vous pouvez donc voir d'où viennent les fichiers du logiciel demandé.

Puis lorsque vous lancez l'installation, scoop télécharge les fichiers du logiciel, crée le dossier du logiciel dans l'arborescence de Scoop, puis lance l'installeur du logiciel (celui décrit dans le manuel). 

**Conclusion**
J'ai rapidement intégré Scoop à mon système pour facilité d'usage qui ne mord en rien sur sa sécurité et sa capacité à rendre au CLI toute son importante. J'espère par mon exposé vous avoir convaincu de l'essayer. Si vous l'avez essayé mais que vous ne souhaitez pas continuer avec Scoop, Scoop ne vous lâche pas et offre une désinstallation toujours aussi élégante qu'à son habitude (`scoop uninstall scoop`). Essayez le, même la désinstallation est super facile !
