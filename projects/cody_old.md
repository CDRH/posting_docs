---
title: Old Cody Archive
layout: page

shortname: cody_archive

# locations
# data_dir
# iiif_path:

# settings
# include_list

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

# funny business (most will be false)
# html_extra: false

---

<p>This is the Cocoon implementation of the Cody Archive, which powers the current production website. In the near future it will be replaced by a Rails application.</p>

<p>This application has an unusual aspect, which is that if you are changing the personography, you will need to break and hard refresh the file creating JSON from a faceted response from Solr.</p>
