# Share your Open Science

1. Create a public github repo

Example:

```https://github.com/jmunroe/opensci_playbook```

2. Set up Github Pages

Settings -> Pages

Source: GitHub Actions


Change the 'About' gear box to edit repository details and click 'Use your GitHub Pages website' 


2. Clone locally and change directory

```
git clone https://github.com/jmunroe/opensci_playbook.git
cd opensci_playbook
```

3. Install mystmd locally

```
pip install mystmd
```

:::{note}
Use can also use conda, mamba, nix, uv, or your preferred package manager
:::

4. Create your content

```
mkdir content
touch content/index.md
```

5. Generate myst configuration files

```
myst init
```

Edit `myst.yml` to add Title, Author as needed.

6. Generate myst table of contents

```
myst init --write-toc
```
  
6. Use myst to help author your content

```
myst start
```

:::{note}
Open a web browser and use it to live-preview your site. Use text editor of choice to edit content/*.md and myst.yml as needed.

See https://mystmd.org/ for MystMD features to explore.
:::


:::{note} Have computational content? Use binder and jupytext!

Install jupytext and convert any `.ipynb` files to `.md` (md:myst).

```
pip install jupytext
jupytext --to md:myst *.ipynb
```

Add these .md files to your `myst.yml`

Create your computational environment

```
mkdir binder
```

Copy files from http://github.com/jmunroe/opensci_playbook/binder as starting point. Adjust `environment.yml` to suit.


Add 

```
  jupyter:
    binder:
      url: https://binder.opensci.2i2c.cloud/
```

to `myst.yml` enable content to run on the 2i2c Open Science Binder

:::


9. Create GitHub action to automatically publish content to GitHub Pages

```
myst init --gh-pages
```

9. Commit and push to GitHub

```
git add *
git commit -m "add myst-ified openscience content"
git push
```

10. Github action will automatically build your myst site

Once the action completes, your site should be deployed:

Example: https://jmunroe.github.io/opensci_playbook



