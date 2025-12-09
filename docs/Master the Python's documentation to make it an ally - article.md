---
Start_date: 2024-12-07
end_date: 2025-01-27
tags:
  - projet/format/article
  - projet/plateforme/medium
Status:
notes liées:
---
Data Science collective : 2025-01-27

**Idée générale (1-2 phrases)**
- Rédiger un article sur les différents solutions qui s'offre au développeur pour avori accès facilement et utiliser fluidement les documentations des logiciels et packages qu'il utilise.

**Angle/accroche** : 

**Braindump** :
titre : Get the most out of docstrings in Python
*Master the python documentation to make it an ally.*

**Méthode traditionnelle **:
- help() = `__doc__` = docstring de l'élément : 
	- Utilisation possible en console ou dans un script seulement
Limites : 
- utiliser limitée (console ou script), visualisation vieillotte et pas optimale

**Méthode tradionnelle ++** : 
- de `help()` à `pydoc` : pas de changement, basé sur le docstring des objets.
- [[pydoc]] : 
	- avantage : affichage visuel des fonctions, lisible +++
	  Inconvénients : interface plutot moche
	Les tips : 
		- Pourquoi `help()`ne marche pas alors que pydoc si ? Import préalable de l'élément cité
Avantages : 
- utilisation non limité = 
	- Possibilité de lancer un serveur web local puissant (fonctions de recherche avec `-b`)
	- Possibilité d'exporter des pages web
- Visuel plus joli

**Modules** : 
De pydoc à module : pas de changement, basé sur les docstrings
- [[mkdocstring]] to create [[mkdocs]] automatic documentation from python scripts.
- [[Sphinx]] : basé sur [[Docstring]] -> automatic documentation

**Softwares**
de module à software : Parsing des docstring par logiciels : 
- Project speciific : 
	- 
- Cross project = agrégateur de documentations : 
	- Offline : [[Outil de documentation hors ligne|Offline documentation tool]] : 
		- [[Avantages d'un outil de documentation hors ligne]]
		- Limite : seule les packages choisis par l'application
	- Online : https://devdocs.io/ : Utilisation de documentation des repos Git (cf. page About)

Comment les offline documentation tool fonctionne ?
Exemple de Zeal : https://zealdocs.org/
-> sur le site, info que documentation fourni par Dash ( https://kapeli.com/dash ) = autre offline documentation tool.
-> Sur le site de Dash (tout en bas), information des module de documentation prise en charge (Exemple python : Sphinx)
Boucle bouclée ! Développeur rédige son code, puis mis en ligne la documentation via SPhinx, reprise ensuite par des outil de documentation offline ! 

Conclusion : 
1. Importance +++ de rédiger des docstrings de bonne qualité, car la plus grosse partie de la documentation utilisée  (help, pydoc) repose là-dessus.
2. Plusieurs formats de docstring (lien externe : https://www.datacamp.com/tutorial/docstrings-python ) -> certaines solutions plus ou moins adaptés selon le format.
3. Python : pydoc = allié de poids +++ -> chargement de manuel même module pas chargé, auacune installation, visuel puissant avec serveur web local spécifique, pas de sur-cout d'apprentissage (1 commande) 
---
## Mastering Python Docs: Turn the Official Documentation into Your Secret Weapon

Every programmer knows that language's or package's'documentation is an essential part of coding, and the Python language is no exception.
In this article, I compare the different ways of accessing to Python's documentation, from the traditionnal and simpliest tool like `help()` and `pydoc()` to the most visual and organized tools like Sphinx, Mkdodcstring and offline documentation softwares.

### Traditional Method: `help()`

The `help()` function in Python relies directly on the docstring (`__doc__`) of the object being inspected. This method is a classic and straightforward approach to documentation, especially useful in interactive environments like Python consoles or scripts.

**Limitations of `help()`:**
- Restricted usage: The outputs are only available in the console or within scripts.
- Outdated visualization: The output is basic and does not offer a modern interface for easier comprehension.

Link : [help()](https://docs.python.org/3/library/functions.html#help)

### Enhanced Traditional Method: From `help()` to `pydoc`

Building on `help()`, Python provides the `pydoc` module, which extracts and displays documentation from docstrings.

**Advantages of `pydoc`:**

- Improved readability: The output is more structured and visually organized compared to `help()`.
- Flexibility: It allows running a local web server with searchable documentation (using the `-b` flag) or generating and downloading web pages.

**Drawbacks of `pydoc`:**

- Outdated interface: While better than `help()`, the interface can still feel rudimentary compared to modern web-based documentation solutions.

**Key Tip:**  
Somestimes, `help()` doesn’t work for a specific element. You need to ensure that the element is imported before invoking `help()`. With pydoc, this problem doesn't exist, as pydoc imports the package itself before trying to access its documentation.

Link : [pydoc](https://docs.python.org/3/library/pydoc.html)

### Modules for Documentation: From `pydoc` to Tools like Sphinx and MkDocstrings

There are a number of tools available for producing attractive documentation, such as  **MkDocstrings** and **Sphinx**, which build on the foundation of docstrings.

#### MkDocstrings
- This tool integrates with **MkDocs** to automatically generate documentation from Python scripts.
- It is particularly useful for creating lightweight, clean, and modern documentation for projects.
Link : [Mkdocstring](https://mkdocstrings.github.io/)

#### Sphinx
- A powerhouse for Python documentation, Sphinx transforms docstrings into professional, navigable, and searchable documentation.
- It supports a variety of output formats (HTML, PDF, etc.) and provides extensive customization options.
- Many offline documentation tools, like Dash and Zeal, rely on Sphinx-generated documentation.

Pandas utilise Sphinx pour sa documentation.

Link : [Sphinx](https://www.sphinx-doc.org/en/master/)

### Software for Offline Documentation

Offline documentation tools provide the ability to access documentation without requiring an internet connection. They parse existing docstrings or documentation generated by tools like Sphinx.

#### Examples:

1. **Zeal**
- An open-source offline documentation browser that relies on Dash’s extensive repository of precompiled documentation sets.
- Supports Python (via Sphinx), among many other programming languages and frameworks.

Link : [Zeal](https://zealdocs.org/)]

1. **Dash**
- A macOS-specific offline documentation tool that aggregates documentation for various programming languages and frameworks, including Python.

Link [Dash](https://kapeli.com/dash)

**How It Works:**

- Developers write code with detailed docstrings.
- Tools like Sphinx generate the documentation.
- Offline tools like Zeal or Dash make these documentations readily available offline, ensuring seamless access for developers.

**Advantages of Offline Documentation Tools:**

- Accessible without internet connectivity.
- Aggregated, centralized access to multiple documentation sets.

**Limitations:**

- Restricted to the packages supported by the specific tool or platform.

For example, Zeal lists Dash as its source for documentation modules, and Dash, in turn, relies on Sphinx documentation for Python.

### Best Practices for Docstrings

The cornerstone of all these tools and methodologies is the Docstring. Writing high-quality docstrings ensures that tools like `help()`, `pydoc`, Sphinx, and MkDocstrings can function effectively.

#### Key Points:

- Adopt consistent formats like **Google style**, **NumPy style**, or **reStructuredText**.
- Keep them concise yet descriptive.
- Include examples, parameter descriptions, and return value information where applicable.

[Learn more about docstring formats here](https://www.datacamp.com/tutorial/docstrings-python).

### Conclusion

Python's documentation ecosystem revolves around the **docstring**, making it essential to write clear and structured documentation at the code level. Tools like `help()` and `pydoc` provide basic yet effective means for accessing documentation, while modern tools like Sphinx and MkDocstrings automate and enhance the process for larger projects. Offline tools like Zeal and Dash complete the circle by making documentation accessible anywhere, anytime.

With the right practices and tools, Python developers can create documentation that not only supports their current projects but also contributes to a broader, reusable knowledge base for the Python community.
