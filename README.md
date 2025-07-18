# Bowie375
This is my [web homepage.](https://Bowie375.github.io)

---

## Instructions
1. To modify the main page, edit the `_pages/about.md` file. 
2. To add publications, create a new file under the `_publications` directory. 
3. To modify CV, change the file under `files/resume.pdf`
4. To create new pages, modify the `_data/navigation.yml` file.
5. To modify style, edit `_sass/*` files.

## Main Working Principles
1. Under `_pages` directory, there are different pages like `about.md`, `publications.md`. These pages are written in markdown format, and they control the content of the page. Things writen in these markdowns will be passed to the layout file as `{{ content }}` variable.

2. Under _config.yml, you will see the layout for the page. For example, the publication page: 
        
        scope:
          path: ""
          type: publications
        values:
          layout: single
          author_profile: true
          share: true
          comments: true

    which means that `single.html` layout will be used to display the page. And you will find a `{{ content }}` in `single.html`, this variable will be replaced by the content of the `publications.md` file. 

3. Go to corresponding layout file under `_layouts` directory to modify the layout. For example, the `single.html` file under `_layouts` directory.

4. All the included files (called like `{% include archive-single-publication.html %}` in `publication.md` file) are under `_includes` directory. You can modify them to change the style of the page.