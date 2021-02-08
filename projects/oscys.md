---
title: O Say Can You See
layout: page

# locations
data_server_dev: cdrhdev1.unl.edu
data_server_prod: cors1601.unl.edu
media_server: cors1601.unl.edu
data_dir: oscys
media_dir: oscys

# reference urls
data: "https://github.com/CDRH/data_oscys"
code: "https://github.com/CDRH/earlywashingtondc"
url_dev: "https://cdrhdev1.unl.edu/earlywashingtondc/"
url_prod: "https://earlywashingtondc.org"

# website tech
app: rails
search: solr
html: true
webs: false

# overrides and custom
after_update: overrides/oscys_after_update.html
---

OSCYS (or Early Washingon DC) is a unique site because not only is there a map component, but there are a huge amount of relationships stored as RDF data. To update this site, you will need to run a specific script to regenerate these relationships.

Behind the scenes, it is good to know that OSCYS was an early Rails site, and as such does <strong>NOT</strong> rely on the CDRH's API, but rather on a proto-API in Solr. Additionally, the interaction between documents, cases, and people in OSCYS is pretty complex and so we use Ruby to generate the Solr files rather than relying on XSLT.

Unlike other projects, the maps will be automatically generated if you run any HTML generation. However, if you would like to update ONLY the maps, you may simply specify `-f csv`.
