# Web site source for the European Covid-19 Forecast Hub

To make change, edit the Rmd (or yml/css) files and commit. The site gets automatically re-built with a github action following any changes.

## Building locally

Before anything, make sure you have fetched the `angular-app` submodule:

```sh
git submodule init
git submodule update
```

### Installing dependencies

In a R console:

```r
remotes::install_deps()
```

For the Angular app, 

1. [Install Node](https://nodejs.dev/learn/how-to-install-nodejs)
1. Move to the `angular-app` folder (e.g., by running `cd angular-app` in your terminal)
1. Run `npm install` in a terminal

### Rendering the HTML files

In a terminal (**not** the R console)

```sh
Rscript -e "rmarkdown::render_site()"
cd angular-app
ng build --index=../_site/visualisation.html --output-path=../_site/ --delete-output-path=false
ng serve --serve-path=../_site/
```

### Viewing the result

You can view the output by opening any HTML file in the `_site` folder. 
