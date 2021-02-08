---
title: Family Letters
layout: page

# locations
data_server_dev: cdrhdev1.unl.edu
data_server_prod: cors1601.unl.edu
media_server: cors1601.unl.edu
data_dir: family_letters
media_dir: family_letters

# reference urls
data: "https://github.com/CDRH/data_family_letters"
code: "https://github.com/CDRH/family_letters"
url_dev: "https://cdrhdev1.unl.edu/family_letters"
url_prod: "https://familyletters.unl.edu"

# website tech
app: orchid
search: es
html: true
webs: true

# overrides and custom
after_update: overrides/family_letters_after_update.html
---

<p>Family Letters, or Cartas a la Familia, is a unique site in that the data repository populates the API and <strong>THEN</strong> requests information from the API to build GeoJSON. This means that you will need to check that you have filled out the following in `config/public.yml` or `config/private.yml`.</p>

- api_request: true
- api_endpoint: https://cdrhapi.unl.edu/v1/collection/family_letters/item

<p>If you choose to disable the API requests or skip this step, the map will not be updated even if letter or photograph locations have been altered or added.</p>
