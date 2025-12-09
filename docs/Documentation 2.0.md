---
Start_date: 2025-05-02
End_date:
tags:
  - projet/format/article
  - projet/plateforme/medium
Status:
notes liées: "[[Master the Python's documentation to make it an ally - article]]"
---
**Idée générale (1-2 phrases)**

**Angle/accroche** : 

**Braindump** :
titre : **Towards Python package documentation 2.0?**
*What could be the future of package documentation?*
*Proposal for specifications for multi-layer documentation*

J'ai rédigé un précédent article pour faire l'état des lieux du fonctionnement de la documentation de packages python, du docstring à la publication : [[Master the Python's documentation to make it an ally - article]].

Problèmes rencontrés : 
1. **Uniformisation** : Pas d'uniformisation des documentations. Début de standardisation grâce à l'utilisation d'un même outil (Sphinx), mais chaque site choisit son format.
2. **Disponibilité** : Très peu de documentations disponible hors ligne (cf. https://kapeli.com/dash donc par extension [[Zeal]] : pas tensorflow, pas langchain, pas PyTorch)
3. **Structure single layer intrapackage** : documentation actuelle des packages = 1 à 2 couches d'informations, déconnectés l'une de l'autre. Exemple : 
	- Polars : documentation 1 couche = fonction seulement
	- Pandas : documentation 2 couches : *API reference* (appelé fonction) et *User guide*. Chaque niveau fait référence aux mêmes fonctions, mais aucun moyen de naviguer directement de l'API reference aux scripts (exemple : fonction cliquable au sein du script pour atteindre la documentation de la fonction dans API référence, et aucune liste cliquable de de scripts utilisant la fonction dans la partie API reference)
4. **Structure interpackage** : Impossible de créer des howto cross-package car howto packages dépendant, ni par le créateur d'un package ni par l'utilisateur lui-même.

**Cahier de charges client doc 2.0** 
Quel cahier des charges pour la documentation de demain ?

1. Repartir de l'existant : package le plus abouti à mon jour = Pandas : 
	- Disponibilité hors ligne
	- Utilisation d'un logiciel éprouvé et déjà largement utilisé
	- Présence de *User guides*.
Pour l'évaluation des fonctionnalités offline : j'utilise [[Zeal]], en considérant que tous les logiciels proposent grosso modo les mêmes features.

Les features à ajouter : 
- Systématiser la création de documentation offline
- Naviguer plus efficacement dans les historiques de documentation : réalité du développement logiciel & data = pas toujours possible d'utiliser la dernière version de package. Hors, impossible de naviguer entre les versions hors ligne.
- Lien les fonctions entre la partie *API reference* et *User guide* : rendre la navigation possible d'une couche à l'autre. Dans la partie *user guide*, le lien renverrait vers la documentation de la fonction *API reference*. Dans la partie *API reference*, une partie de la documentation serait dédiée à la liste des *User guide* utilisant cette fonction, avec possibilité de cliquer sur un script poury accéder.
- Permettre à l'utilisateur de surcharger un docset avec ses propres *User guide*, et intégrer à ces guides maisons la feature de liaison des coucehs *API reference* et *user guide*.

*Le guide utilisateur* : 
*user guide* utilisateur = 
- Permet d'utiliser des fonctions de plusieurs packages (avec lien cross-layer, nécessité de systématiser le hors-ligne pour permettre ce lien cross-layer).
- Pour chaque package utilisé dans le script : sélecteur de version du package. Si une fonction du script n'est pas disponible dans la version du package cité, cette dernière se met en police rouge pour avertir l'utilisateur et n'est alorsp lus cliquable.
  Par défaut, la version du package sélectionnée est la dernière version disponible dans el gestionnaire offline de package de l'utilisateur, pour lui éviter d'avoir à update la version à considérer systématiquement.
- Format permettant de publier les guides, pour que les autres personnes puissent les récupérer et permettant le lien cross-layer
- Pour les fonctions ayant le même nom mais dans 2 packages différents : laisser la possibilité à l'utilisateur de modifier si besoin la package auquel chaque fonction du script se rattache.

*Liens API reference-User guide & navigation de versions* : 
- Si une fonction du package n'est pas disponible dans la version du package cité, cette dernière se met en police rouge pour avertir l'utilisateur.

**La place de l'IA** : 
Impossible de faire cet article sans parler d'IA. C'est parti pour l'IA ! 

- IA = 2 usages possibles : 
	- Nous donner l'information que je recherche quand je le souhaite (exemple : *comment créer un dasbhoard avec duckdb et streamlit ?*)
	- faire à notre place.
Dans les 2 cas, problème : 
- interface opaque entre l'information (documentation) et la réalisation (le code écrit). Pas de transaprence sur le code, ses limites, ses failles, ses biais
- Pansement au problème : réponse instantanée, mais aucun apprentissage ni création de connaissance :  réponse directe -> pas de temps pris à explorer le package, à voir les à-cotés d'une fonction prévue par les développeurs, les autres fonctions disponibles, les autres chemins potentiels -> limite drastique de la prise en main du package, en nous mettant des œillères dans l'utilisation du pcakge. 
Nouvelles idées viennent en faisant -> besoin de réaliser par soit même et d'explorer par soit même pour avancer.

IA = solution intéressante dans certains cas, mais loin d'être une panacée. Besoin d'explorer et de réaliser par soit même pour progresser et créer des solutions plu perfectionnées.

**Quelles solutions déjà existantes ?**
Classé de la plus simple a mettre en place a la plus compliqué subjectivement.

***Knowkedge management***
- *User guide* utilisateur = problème profondément knowkedge management -> besoin d'aller voir les solutions qui y sont proposé.
- Obsidian -> permet de réaliser ses guides maisons, de les éditer. L'unité de base du système = script, qui réalise une action donnée.
- + :
	- Créer ses propres guides éditables
	- Facilement partageable : format markdown, avec possibilité de les partagés via les journaux déjà existants (Towards Data Science, Level Up Coding, Data Science Collective, ... )
- - : 
	- Pas de chainage du *User guide* utilisateur ni *User guide* du package et de la partie *API reference*, car utilisation d'un logiciel tierce pour générer ses propres How To.
	- Besoin de créer un élément qui transforme le docset en base de notes markdown, avec 1 note par fonction et l'arborescence du docset pour garder la filiation des fonctions et de leur objets au sein du package.

Je ferai un article dédié à cette solution, abonnez-vous si vous souhaitez être notifié dès sa sortie.

***Faire évoluer les standards***
Pandas = documentation riche, qui dispose nativement online et offline des 2 couches citées : doc-guide et manuel par fonction -> standard de documentation qui se rapproche le plus de la doc' 2.0

Besoin de compléter les outils existants avec des features plus avancées : 
- créer des liens *fonctions* <-> *guide*, généré au moment de la création du docset,
- donner la possibilité a l'utilisateur d'écrire ses propres guides = créer une partie d'édition de guide intrapackage, dans un format type markdown pour permettre le partage de ces guides via des journaux existants,
- ajout d'une navigation inter-version d'un même package, plutôt que remplacé l'ancienne version par la nouvelle dans les outils de documentation offline,

- + :
	- base de travail déjà riche, avec les 2 couches de doc' déjà existante et intégrer dans un visuel utilisateur
- - :
	- Besoin d'une modification de fonctionnement des logiciels non négligeable, et notamment la méthode de création et de chargement de docset, pour garder les guides au fur et a mesure des versions & permettre les liens
	- N'intégre pas les *user guide* utilisateur interpackage car fonctionnement par silo, package par package.

***Créer un outil maison***
Créer un outil = permet de se libérer de contrainte de devoir faire évoluer l'existant, en repartant d'une feuille blanche. 
- + :
	- repartie d'une page blanche
	- intégrer des technos, des visuels plus modernes
- - :
	- Doc offline Zeal et Dash = déjà implanté avec une bonne communauté -> nécessite de recréer une communauté
	- doc sphinx = doc puissante, visuelle avec déjà tous les briques. Seulement besoin de les interconnecter différemment. Nouvelle outil = nouveau paradigme, nouvelle experience utilisateur a imaginer -> plus compliqué.

**Conclusion** : 
- Package de plus en plus complexe, docset = outil genial, mais nécessitant déjà de maîtriser le package pour en connaître le fonctionnement global, et aucune information quand a l'articulation avec d'autres packages.
- besoin de faire évoluer un format un peu vieillot de documentation pourjune documentation plus partageable, riche et plus adapté aux besoins des développeurs de tour niveau,
- Nouvelle forme de documentation -> impact dingue sur la communauté : sans contraindre le format des guides, il créerai une banque de guides dans un format universel, utilisable, téléchargeable par tous.m, chaîné aux docset pour maîtriser un package et ses relations avec d'autre packages.

Merci : 
- Dveloppez pour les alternatives à Zeal : https://programmation.developpez.com/actu/345115/Zeal-un-outil-permettant-aux-developpeurs-de-telecharger-les-documentations-des-langages-et-d-y-acceder-hors-ligne-y-compris-les-documentations-des-bibliotheques-des-API-et-d-autres-ressources/

---
## Towards Python package documentation 2.0?
Sous-titre de publication : *Proposal for specifications for multi-layer documentation*

I previously wrote an article reviewing how Python package documentation works, from docstrings to publication: ==[[Master the Python's documentation to make it an ally - article]]==. This article gave me a deep understanding of how package documentation works, from function docstrings to offline documentation. However, this article also highlighted several flaws in this documentation structure.

## Current Issues

I have identified several issues, which I have grouped into four categories: 
- **The lack of standardization**: Sphinx has brought some alignment, but each project still uses its own format,
- **Limited offline availability**: few documentations can be accessed offline (e.g., [Dash](https://kapeli.com/dash), [[Zeal]]). Major packages like TensorFlow, LangChain, or PyTorch are missing,
- **Shallow intrapackage structure**: most documentations only offer 1–2 disconnected layers:
    - *Polars*: one layer focused on functions offline, and user guide online only,
    - *Pandas*: two layers offline (API reference and user guide), but navigation between them is impossible.
- **No interpackage structure**: users and maintainers cannot create cross-package user guides.

*Today's documentation works very well, so why should it be changed?*
Current documentation fills an essential link in the information chain, such as providing a complete description of functions (what inputs, what outputs, how it works, etc.). 
But a function never stands alone; it is always part of a whole. Documentation must evolve accordingly and address functions within their ecosystem. Developers have understood this well by including user guides directly in the package. But with the evolution of current knowledge management and its tools, it is both necessary and possible to go further.

Furthermore, the inaccessibility of most packages offline complicates the user experience: instead of having a single software package that brings together all the packages with the ability to use all the software's tools offline, particularly the search functions, the developer must navigate online between the different documentation sets to finally find the desired information. This is a minimal waste of time, but it multiplies with each search and is therefore not insignificant.

## Specifications for Documentation 2.0
*The goal of this section is to imagine the ideal 2.0 documentation. I will discuss technical considerations or proposed implementation methods later.*

*What already exists?*
I think Pandas provides the most advanced model:
- Offline availability,
- Widely used tooling,
- Existence of user guides.
Offline features are tested with [[Zeal]], assuming similar tools offer comparable capabilities.

*What features to add?*
- Systematize the creation of offline documentation,
- On offline document management software, add a version history navigation: real-world projects often require older versions. Offline tools don’t allow browsing them.
- Allow navigation between layers API and user guides:
    - From user guides : make functions clickable, with a link pointing to the function documentation,
    - From API : list the user guides using the function, and allow the user to go to the user guide by clicking on it
- Allow the user to create their own user guides.

*About the User’s User Guides* 
User-generated guides are an important part of the process. They allow users to build their own development repositories, writing outlines for scripts they will later apply. This feature allows users to move beyond understanding and into action.

Key features are:
- **Multi-package support** with cross-layer linking: a user-generated guide: A user-generated guide should be able to span multiple packages within the same guide
- **Package version selector**: within each guide, the packages used are listed, and the user can choose the version of each package he wishes to use via a selector.
    - Functions missing from the selected version appear in red and are not clickable.
    - Default version of each pacakge is latest available in the offline tool.
- **Shareable and publishable format**: User-generated guides must be in a format that allows them to be shared and published
- **Conflict resolution** : If a function corresponds to 2 packages within the guide, the user chooses which package to attach this function to.

*How to reconcile the link between the API and the user guide and the versioning of package versions?* 
If a function does not exist in the selected version, it appears in red to alert the user.

## The Role of AI
No discussion about documentation would be complete without AI.

AI could have two main uses:
1. **On-demand information retrieval**: I ask my question to the AI, which answers me instantly (example: How do I build a dashboard with Streamlit and DuckDB?)
2. **Code generation**: Ask the AI ​​to generate the response (example: Generate a dashboard with Streamlit and Duckdb).
But AI has two huge problems:
- Opaque interface between documentation and code: no transparency on code quality, limitations, or biases.
- Instant answers with no learning process: prevents developers from exploring packages, discovering features, or experimenting with alternatives.
AI is useful in specific contexts, but it is not a silver bullet. True mastery requires exploration and hands-on experimentation. AI is a temporary band-aid, but the underlying problem will never be solved.

## Existing Solutions
I have ranked the solutions from simplest to most complicated:

### 1. Knowledge management
The need for custom user guides falls under knowledge management. Knowledge management software allows you to edit your own user guides. The formats used (often Markdown) allow these guides to be published with little rework. I personally recommend Obsidian.

Pros: 
✅ Easy to edit
✅ Format compatible with existing platforms (e.g., Towards Data Science).

Cons: 
⛔ No link between API reference and guides from package or users. This would require transforming the entire document into markdown, respecting the fact that each function has its own note, in order to then be able to cite the functions in the user guides.

I plan to write an article soon on this solution specifically, subscribe so you don't miss it!

### 2. Evolving standards
Pandas is already close to a model. But following improvements are needed:
- Auto-generate function ↔ guide links
- Provide an Markdown editor for guides
- Add inter-version navigation

Pros: 
✅ strong foundation already exists.  

Cons: 
⛔ Requires heavy modifications in tooling. Still package-siloed.

### 3. Building a new tool
Creating new tools to create documentations and to download and use then offline would give full freedom.

Pros: 
✅ Fresh start
✅ Modern front-end technologies, new UX

Cons: 
⛔ Zeal and Dash already have strong communities
⛔ Sphinx already provides powerful components
A new tool means building both a new paradigm and a new community.

## Conclusion

Packages keep growing in complexity. Current docsets are powerful but demand prior expertise and lack interpackage vision. The documentation format needs to evolve into something richer, more shareable, and better suited to developers’ needs.
A new model could have a tremendous impact: a universal, shareable guide bank, linked to docsets, enabling deeper understanding of both packages and their relationships.

To write this article, I researched Zeal and Dash competitors to see what features they had. I found a great [website](https://programmation.developpez.com/actu/345115/Zeal-un-outil-permettant-aux-developpeurs-de-telecharger-les-documentations-des-langages-et-d-y-acceder-hors-ligne-y-compris-les-documentations-des-bibliotheques-des-API-et-d-autres-ressources/) that helped me a lot. I thank the Developpez website for this little help!