Add new projects to the `projects` directory with the following front matter:


```yaml
title: Cody Archive
layout: page

# locations
data_server_dev: cdrhdev1.unl.edu
data_server_prod: cors1601.unl.edu
media_server: cors1601.unl.edu
data_dir: cody_archive
media_dir: cody_archive

# settings
# include_list: production_files.txt

# reference urls
data: "https://github.com/CDRH/data_cody"
code: "https://github.com/CDRH/cocoon_cody"
url_dev: "https://cdrhdev1.unl.edu/cocoon/codyarchive.org/"
url_prod: "https://codyarchive.org"

# website tech
app: cocoon     # cocoon or orchid
search: solr    # solr or es
html: false     # true or flase
webs: false     # webscraping, true or false

# Overrides and Custom
after_check: overrides/cody_after_check.html
```

## Override or Append to Sections

You may override an entire section of the documentation or append more instructions to or after a step by adding a new template to `_includes/projects` and then setting one of the following in the front matter. Please use the convention `[projectname]_alt_login.html` to keep that directory organized. 

- alt_docs: overrides all documentation

# overrides entire section
- alt_login
- alt_update
- alt_check
- alt_push

# appends to end of existing section
- after_login
- after_update
- after_check
- after_push
