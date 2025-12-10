# Full guide to Build a professionna lportfolio with GitHub Pages
*How to develop your image as a developer or data worker with a quality portfolio*

## My previous portfolio

In 2023, I’d been coding for data projects for 2 years and was looking to create my first portfolio to present my data science projects. I discovered [Matt Chapman’s TDS article](https://towardsdatascience.com/the-portfolio-that-got-me-a-data-scientist-job-513cc821bfe4) and [Matt Chapman’s portfolio](https://mattschapman.github.io/). This article corresponded perfectly to my technical knowledge at the time (Python, Git). Thanks to Matt Chapman’s article, I begun my first portfolio! So I decided to explore this solution and figure out how to go about it. I discovered [the reference that Matt Chapman used](https://medium.com/@evanca/set-up-your-portfolio-website-in-less-than-10-minutes-with-github-pages-d0efa8ff56fd) and the [corresponding repository](https://github.com/evanca/quick-portfolio). I used this reference to create my portfolio.

In 2024, I found my old portfolio old-fashioned compared to existing portfolios, and not very attractive to data enthusiasts or recruiters. Exploring the projects already carried out in the community, I found several projects with superb documentation. Here are 2 links that inspired me: [Multi pages documentation based on GitHub Pages](https://github.com/aphp/edsnlp), and [JavaScript portfolio based on GitHub Pages](https://github.com/KeeganFernandesWork/KeeganFernandesDataScience) and [corresponding Medium article](https://keeganfdes03.medium.com/making-a-data-science-portfolio-using-github-pages-for-free-ee831d4dec68).

## The adventure begins

For this new edition of my portfolio, my criteria were: a free solution, with minimal configuration. Looking through existing documentations and portfolios, I had several options:

- option 1: Keeping the same visual and architecture from my previous portfolio
- option 2: Fork the JavaScript portfolio mentioned above
- option 3: Use the [mkdocs](https://www.mkdocs.org/) Python package

As I don’t code in JavaScript, I would have been quickly limited in my customization, so I preferred to pass. Using a single GitHub Pages as in my previous portfolio wasn’t enough of an improvement on my portfolio. During my research, I discovered 2 mkdocs sub-packages that particularly caught my attention for the visuals they offered: [mkdocs-material](https://squidfunk.github.io/mkdocs-material/) and [just-the-docs](https://just-the-docs.com/). I finally chose mkdocs for 3 reasons:

- the package (mkdocs) is easy to use, and I know Python and Git, which are the 2 technologies required
- the website content is in Markdown, and the package automatically generates the site with a minimum of action on my part on the GitHub repository
- the website generated is beautiful and functional

Mkdocs-material allows the use of Google Tags, perfect for tracking traffic on my portfolio!

## The code

At the time of this project, I had already set up my GitHub Pages, created my repository and created the virtual environment for my previous portfolio. To enable everyone to follow and reproduce this article, I’ve decided to start from scratch. For those of you who already have a GitHub Pages portfolio, you’re already familiar with Git and Python and will be able to hang on to the branches without any worries.

In this article, I’ll be sharing some URL links. My aim is to give you a good understanding of every aspect of the code and, if necessary, to provide you with resources to go into more detail on a subject or solve an error that I haven’t described in my article.

### Software needed

For this work, you will need at least Python and Git installed and configured on your computer, and a GitHub account. Personally, I work on VSCode and [Miniconda integrated into PowerShell](https://stackoverflow.com/questions/64149680/how-can-i-activate-a-conda-environment-from-powershell) so that I can have my scripts and terminal on the same screen. To configure Git, I refer you to the *Your identity* part of the page on the [Git site](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup).

### Configure the local environment

I work with [Miniconda](https://docs.anaconda.com/miniconda/). If you work with the same tool, you will recognize the *‘(base)>’* elements. If not, this element represent the current virtual python environment (base is the default virtual environment of Miniconda). The element `working_folder` is the the terminal’s current folder.

1. The first step is to create the virtual environment for the portfolio project:

```bash
(base)> conda create -n "portfolio_env" # Create the new virtual env named portfolio_env  
(base)> conda activate portfolio_env # Activate the new virtual env, (base) become (portfolio_env)
```

2. In this new environment, we need to install the Python packages:

(portfolio_env)> pip install mkdocs mkdocs-material

3. To guarantee the reproducibility of your environment, we export requirements:

```bash
(portfolio_env)> conda env export > "environnement.yml" # Export the environment.yml file, to ensure conda env repoductibility (including the python version, the conda env configuration, … )  
(portfolio_env)> conda list > "requirements.txt" # Export packages installed only
``` 

### Create the working folder

My previous portfolio didn’t use mkdocs, so I create the mkdocs structure:

```python
(portfolio_env)> mkdocs new "<your GitHub username>.github.io"
```

Replace *\<your GitHub username>* by your GitHub username. For the rest of this article, I’ll call the folder *\<your GitHub username>.github.io working_folder*. The new folder will have the following architecture:

```markdown
<your GitHub username>.github.io  
|- mkdocs.yml  
|- environment.yml  
|- requirements.txt  
|- docs/  
    |- index.md
```

To understand the mkdocs package, you will find the documentation [here](https://www.mkdocs.org/).

### Prepare Git

If you already have a GitHub Pages, you can clone your *\<your GitHub username>.github.io* repository and skip this part. The step part is to create the local Git repository.

1. Create a file named _readme.md._ This file is the classic readme file for any Git repository
2. Open a Git terminal and create the local repository

```bash
working_folder> git init # Initiate the local repo  
working_folder> git add . # Save the readme file  
working_folder> git commit -m "Initiate repo" # Commit changes
```

3. On your GitHub account, create a new repository named *\<your GitHub username>.github.io* (replace *\<your GitHub username>* by your GitHub username)

4. Connect the local repository with the remote repository. In the Git terminal:

```bash
working_folder> git remote add github https://github.com/<your GitHub username>.github.io
```

If you are not familiar with GitHub Pages, the [GitHub Pages website](https://pages.github.com/) will introduce them to you and explain why I use *\<your GitHub username>.github.io* as repository name.

The working folder will have the following architecture:

```bash
<your GitHub username>.github.io  
|- .git  
|- readme.md  
|- mkdocs.yml  
|- environment.yml  
|- requirements.txt  
|- docs  
    |- index.md
```

### Feed the website

Mkdocs allows you to display website and dynamically include modifications, so you can see your site evolve over time. The code to dynamically generate the site:

```bash
mkdocs serve
```

This command returns a local URL (e.g. *127.0.0.1:8000*) to paste into the browser.

**readme.md and index.md**

The readme file corresponds to the home page of the remote repository. When you created the working folder with the mkdocs package, it created a *docs/index.md* file which corresponds to the site’s home page.

**The menu**

The first step is to configure the menu of the website (the left panel, to navigate between pages). In the *working_folder/mkdocs.yml* file, this is the *nav* part:

```mkdocs
# Page tree: refer to mkdocs documentation  
nav:  
- Home: index.md  
- Current project:  
  - "Health open data catalog": catalogue-open-data-sante/index.md  
- Previous data science projects:  
  - "Predict Health Outcomes of Horses": horse_health_prediction_project/readme.md  
  …  
- Previous skills based projects:  
  - "Predict US stocks closing movements": US_stocks_prediction_project/readme.md  
  …
```

The *Home* element is important: this is the home page of the website. You can choose to duplicate the *readme.md* file inside the *index.md* file to have the same home page on the GitHub repository and the website, or write a new *index.md* file to have a specific home page for your portfolio.

Let’s break down the following block:

```markdown
- Previous data science projects:  
  - "Predict Health Outcomes of Horses": horse_health_prediction_project/readme.md  
  …
```

*Previous data science project*: will represent the name of a group of pages in the navigation bar. *“Predict Health Outcomes of Horses”* will be the name displayed in the menu of the file indicated, in this case: *horse_health_prediction_project/readme.md* . Mkdocs automatically finds the pages to display in the docs folder, so there is no need to specify this in the path. However, as the horse health prediction project is presented in an eponymous folder, you must specify in which folder the file you wish to display is located.

In the *docs/* folder, I add my previous project:

```markdown
working_folder  
|- docs  
    |- horse_health_prediction_project  
        |- readme.md  
        |- notebook.ipynb  
        |- notebook.html  
    |- US_stocks_prediction_project  
        |- reamd.me  
        |- notebook.ipynb  
        |- notebook.html
```

Then I add each project’s presentation in the nav bar with the following syntax: *`“<displayed name>”: <path_from_docs_to_project_file>/<project_presentation>.md`*.

The indentation here is very important: it’s define folders of the navigation bar. Not all files in the docs folder need to be listed in the navigation bar. However, if they are not listed, they will not be directly accessible to the visitor.

### Website configuration

Then I configure invisible but very important aspects of my website:

- Basic web site information asked by mkdocs-material:

```markdown
# Project information  
site_name: Pierre-Etienne's data science portfolio  
site_url: https://petoulemmonde.github.io/  
site_author: Pierre-Etienne Toulemonde  
site_description: >-  
  I'am Pierre-Etienne Toulemonde, PharmD and Data scientist,   
  and you are here on my data science portfolio
```

The *site_name* corresponding to the name on the tab browser.

- Some repo informations to allow mkdocs-material to display information in the top right-hand corner of the repository hosting the site:

```markdown
# Repository: necessary to display the repo on the top right corner  
repo_name: petoulemonde/petoulemonde.github.io  
repo_url: https://github.com/petoulemonde/petoulemonde.github.io
```

- I define the design to use here:

```markdown
# Configuration:  
theme:  
  name: material
```

It’s a very important step because this line says to mkdocs: ‘Use the mkdocs-material package to build the website’. If you miss this step, the GitHub Pages will not have the mkdocs-material visual and functionalities!

I add some additional information, to track the traffic on my website:

```markdown
# Additional configuration  
extra:  
  analytics:  
    provider: google  
    property: <your google analystics code>
```

The *property* is a code from Google Analytics, to track traffic on my portfolio. The code is generated with Google Analytics and linked to my Google account (you can found a tutorial to create your code [here](https://www.w3schools.com/howto/howto_google_analytics.asp)).

Of course I didn’t write the whole file at once. I started to add one project files and information in the file architecture and in the navigation bar, then the configuration, then another project, then configuration, …

## The final _mkdocs.yml_ file

My final *mkdocs.yml* file is:

```markdown
# Project information  
site_name: Pierre-Etienne's data science portfolio  
site_url: https://petoulemonde.github.io/  
site_author: Pierre-Etienne Toulemonde  
site_description: >-  
  I'am Pierre-Etienne Toulemonde, PharmD and Data scientist,   
  and you are here on my data science portfolio  
  
# Repository  
repo_name: petoulemonde/petoulemonde.github.io  
repo_url: https://github.com/petoulemonde/petoulemonde.github.io  
  
# Configuration  
theme:  
  name: material  
  
# Additional configuration  
extra:  
  analytics:  
    provider: google  
    property: <google analystics code>  
# Page tree  
nav:  
- Home: index.md  
- Current project:  
  - "Health open data catalog": catalogue-open-data-sante/index.md  
- Previous data science projects:  
  - "Predict Health Outcomes of Horses": horse_health_prediction_project/readme.md  
  …  
- Previous skills based projects:  
  - "Predict US stocks closing movements": US_stocks_prediction_project/readme.md  
  …
```

## The final file structure

At this step, my file structure is:

```markdown
petoulemonde.github.io  
|- .git  
|- readme.md  
|- mkdocs.yml  
|- requirements.txt  
|- environnement.yml  
|- docs/  
    |- index.md  
    |- US_stocks_prediction_project/  
        |- README.md  
        |- notebook.ipynb  
        |- notebook.html  
    |- horse_health_prediction_project/  
        |- README.md  
        |- notebook.ipynb  
        |- notebook.html  
    |- … others projects …
```

### Deploy the work

Mkdocs allows to generate the code for the website in 1 command line:

```bash
mkdocs gh-deploy
```
Mkdocs translate all the mkdocs files to html website, like a magician! The Markdown links are transformed into HTML links and the sitemap of the site is generated.

Then, commit all the changes in the local repository and push it in the remote repository.

working_folder> git add .  
working_folder> git commit -m "Create website"  
working_folder> git push github master

## The GitHub Pages configuration

To set up a GitHub Pages, the steps are:

- Follow previous steps, to push a minimal portfolio
- On [GitHub](https://github.com/), in the remote repo home page, click on ‘_Settings_’ (top menu)
- On the left menu, click on ‘_Pages_’
- Configure the page:  
    - *Source: deploy from a branch*  
    - *Branch: gh-deploy and /root*  
    - then save

In the top menu, click on ‘_Actions_’. You should see a ‘workflow run’. Leave it there, and as soon as it is green, it’s good, your site is online! Well done, you succeeded!

You can see you website on *https://\<your GitHub username>.github.io*.

## Iterative improvements

The more I look at my portfolio to check and present it, the more errors I notice. To correct them, nothing could be simpler:

1. Make changes on your computer (to take a quick look at the modification made and make others if necessary, quick reminder: *`mkdocs serve`*)
2. Regenerate the site using *`mkdocs gh-deploy`*
3. Commit all changes
4. Push into the remote repo.

And the magic happens: GitHub automatically makes the modification (look at the ‘_Actions_’ tab to see where GitHub is at).

## My final 2024-edition portfolio!

You’ll find my edition 2024 portfolio [here](https://petoulemonde.github.io/) and the GitHub repository [here](https://github.com/petoulemonde.github.io). In the future, I’d like to integrate JavaScript to make the portfolio more dynamic.

Why didn’t I buy a website for my portfolio? I’d like to concentrate on creating content for my portfolio and new projects, and keep the administrative aspect of these tasks to a minimum. What’s more, for a website as for a GitHub Pages, people will find out about the project by clicking on a link that redirects them to my site, so purchased website or not, the result will be the same.

Many thanks for your attention, this was my first medium article. Feel free to respond on the article, I’d love to hear what you think. See you soon!