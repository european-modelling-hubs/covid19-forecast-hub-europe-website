# Web site source for the European Covid-19 Forecast Hub

To make change, edit the Rmd (or yml/css) files and commit. The site gets automatically re-built with a github action following any changes.

## Building locally

### Installing dependencies

In a R console:

```r
remotes::install_deps()
```

For the Angular app, run in a terminal:

```sh
npm install
```

### Rendering the HTML files

In a terminal (**not** the R console)

```sh
Rscript -e "rmarkdown::render_site()"
cd angular-app
ng build --index=../_site/visualisation.html --output-path=../_site/ --delete-output-path=false --base-href="/"
```

### Viewing the result

You can view the output by opening any HTML file in the `_site` folder. 
