---
title: Old Cody Archive
layout: page

# locations
data_server_dev: cdrhdev1.unl.edu
data_server_prod: cors1601.unl.edu
media_server: cors1601.unl.edu
data_dir: cody_archive
media_dir: cody_archive

# reference urls
data: "https://github.com/CDRH/data_cody"
code: "https://github.com/CDRH/cocoon_cody"
url_dev: "https://cdrhdev1.unl.edu/cocoon/codyarchive.org/"
url_prod: "https://codyarchive.org"

# website tech
app: cocoon
search: solr
html: false
webs: false

# Overrides and Custom
after_check: overrides/cody_after_check.html
---

<p>This is the Cocoon implementation of the Cody Archive, which powers the current production website. In the near future it will be replaced by a Rails application.</p>

<p>This application has an unusual aspect, which is that if you are changing the personography, you will need to break and hard refresh the file creating JSON from a faceted response from Solr.</p>
