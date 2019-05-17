Leaflet, R, Jekyll and GitHub
================

Recently I have been struggling when trying to embed a
[leaflet](https://rstudio.github.io/leaflet) map created with
**RStudio** on my blog, hosted in GitHub via
[Jekyll](https://jekyllrb.com). In my case, I use the [**Beautiful
Jekyll**](https://deanattali.com/beautiful-jekyll/getstarted/)
implementation created by [daattali](https://github.com/daattali).

1.  [The GitHub/Jekyll part](#gitjek)

2.  TBD

3.  TBD

### 1\. The GitHub/Jekyll part <a name="gitjek"></a>

The first step is to call the requested libraries in your GitHub page.
As Jekyll basicaly transforms `markdown` into `html`, this step is a
matter of **what to include** and **where** in your own repository.

#### What to include

This part is not complicated. When having a look to the source code of
[Leaflet for R](https://rstudio.github.io/leaflet/) site it can be seen
this chunk

``` html
 <script src="libs/jquery/jquery.min.js"></script>
<meta name="viewport" content="width=device-width, initial-scale=1" />
<link href="libs/bootstrap/css/flatly.min.css" rel="stylesheet" />
<script src="libs/bootstrap/js/bootstrap.min.js"></script>
<script src="libs/bootstrap/shim/html5shiv.min.js"></script>
<...more code>
<link href="libs/rstudio_leaflet/rstudio_leaflet.css" rel="stylesheet" />
<script src="libs/leaflet-binding/leaflet.js"></script>
```

So now we have it\! The only thing to remember is **to reference that
part to the source repository (Leaflet for R)**, like
this:

``` html
    <script src="https://rstudio.github.io/leaflet/libs/jquery/jquery.min.js"></script>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://rstudio.github.io/leaflet/libs/bootstrap/css/flatly.min.css" rel="stylesheet" />
    <...more code>
        <script src="https://rstudio.github.io/leaflet/libs/leaflet-markercluster/leaflet.markercluster.layersupport.js"></script>
    <link href="https://rstudio.github.io/leaflet/libs/ionicons/ionicons.min.css" rel="stylesheet" />
```

In my case I included it on
[`./_includes/leaflet.html`](https://github.com/dieghernan/dieghernan.github.io/blob/master/_includes/leaflet.html).

#### Where to include

This is the complicated part. The code chunk should be included in the
`<head>` section of your page, so you would need to find where to put
it. In the case of **Beautiful Jekyll** it is on
[`./_includes/head.html`](https://github.com/dieghernan/dieghernan.github.io/blob/master/_includes/head.html).