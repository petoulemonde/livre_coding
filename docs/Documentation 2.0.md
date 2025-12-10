# Towards Python package documentation 2.0?
*Proposal for specifications for multi-layer documentation*

I previously wrote an article reviewing how Python package documentation works, from docstrings to publication: Master the Python's documentation to make it an ally - article. This article gave me a deep understanding of how package documentation works, from function docstrings to offline documentation. However, this article also highlighted several flaws in this documentation structure.

## Current Issues

I have identified several issues, which I have grouped into four categories: 
- **The lack of standardization**: Sphinx has brought some alignment, but each project still uses its own format,
- **Limited offline availability**: few documentations can be accessed offline (e.g., [Dash](https://kapeli.com/dash), Zeal). Major packages like TensorFlow, LangChain, or PyTorch are missing,
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
Offline features are tested with Zeal, assuming similar tools offer comparable capabilities.

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

### Knowledge management
The need for custom user guides falls under knowledge management. Knowledge management software allows you to edit your own user guides. The formats used (often Markdown) allow these guides to be published with little rework. I personally recommend Obsidian.

Pros: 
✅ Easy to edit
✅ Format compatible with existing platforms (e.g., Towards Data Science).

Cons: 
⛔ No link between API reference and guides from package or users. This would require transforming the entire document into markdown, respecting the fact that each function has its own note, in order to then be able to cite the functions in the user guides.

I plan to write an article soon on this solution specifically, subscribe so you don't miss it!

### Evolving standards
Pandas is already close to a model. But following improvements are needed:
- Auto-generate function ↔ guide links
- Provide an Markdown editor for guides
- Add inter-version navigation

Pros: 
✅ strong foundation already exists.  

Cons: 
⛔ Requires heavy modifications in tooling. Still package-siloed.

### Building a new tool
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