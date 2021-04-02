

.. toctree::
   :maxdepth: 2

   releasenotes
   tutorial/index
   users/index
   reference/holopy

## PyDHM Python library for numerical reconstructions of holograms 

PyDHM is a python library to mainly obtain numerical reconstructions for holograms in digital holography and digital holography microscopic.  Besides, PyDHM can be used to numerical propagation of scalar wave fields.

PyDHM was developed by the cooperation of OIRL research group form The University of Memphis and the EAFIT university.  

PyDHM contains two main packages, propagation approaches PyDHM.propagation and DHM implementations PyDHM.Implementations. Below an explanation of each package. 

You can use the [editor on GitHub](https://github.com/OIRL/PyDHM/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.


<p>Capítulo 1: <a href="index1.html">pulsar quí</a></p>

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/OIRL/PyDHM/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

---
title: How To 
layout: template
filename: howto
--- 

# How to Create a Multi-page Website using Github Pages

### To Create the Template
1. Create the page normally following [pages.github.com](https://pages.github.com), but use `CONTENT` as the content of the page
2. Choose a theme and publish the page
3. Fetch and checkout the gh-pages branch on your local repository
4. Create a directory `_layouts` in the repository
5. Rename `index.html` to `template.html` and move it into the `_layouts` directory
6. Open `template.html` and replace the `<p>CONTENT</p>` placeholder with {% raw %}`{{ content }}`{% endraw %} (this is [Jekyll](https://jekyllrb.com) syntax to grab the content from the MarkDown pages you will create)
7. Identify the navigation/button section of HTML
8. Copy one navigation/button item (probably a `<a href="">` or similar tag)
9. Insert this code at the top of the navigation/button item section:

```
{% raw %}
{% for page in site.pages %}
    <a href={{ page.filename }}>{{ page.title }}</a>
{% endfor %}
{% endraw %}
```

To match your theme, paste the copied navigation/button item in place of `<a href={{ page.filename }}>{{ page.title }}</a>`, but use `{{ page.filename }}` for the href and `{{ page.title }}` for the content (as shown in the example in step 9)

### To Create Your First Page
1. Make a new file called `index.md` in your repository
2. Copy the content of your `readme.md` or write a new home page in MarkDown into this file
3. At the top of this file, add the following:

```
---
title: PAGE TITLE HERE
layout: template
filename: NAME OF THIS .md FILE HERE
--- 
```

Commit your changes and push them to the gh-pages branch

Now, when you go to `YOURGITHUBNAME.github.io/YOURPROJECTNAME`, you should see the contents of your index.md formatted with the theme that you chose.

### To Create Additional Pages
1. Make a new file called `PAGENAME.md` in your repository (where PAGENAME is the name of your new page)
2. Write the content for this new page in MarkDown
3. At the top of this file, add the following:

```
---
title: PAGE TITLE HERE
layout: template
filename: NAME OF THIS .md FILE HERE
--- 
```

Commit your changes and push them to the gh-pages branch

Now, when you go to `YOURGITHUBNAME.github.io/YOURPROJECTNAME`, you should see a link to your new page. When you click this link, you should see your new page formatted with the theme that you chose. 
