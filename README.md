# CDRH Posting Documentation

This here is the place to find some rad documentation, or at least links to documentation!

## Add Project

Create a new file at `projects/[new_project].md` and paste in the below yaml snippet to the top. Add an explanation of the project and notes about any oddities as markdown or HTML after the three final `---` marks.

Fill out the yaml content with your project's information. Please refer to the explanations below for more information about each setting. You may delete any below the portion marked as OPTIONAL.

You will need to visit `projects.md` to add your new project's link to its page, also.

```yaml
---
title: Cody Archive
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
app: orchid
search: es
html: true
webs: false

# OPTIONAL

# individual project settings
include_list: production_files.txt
section_type: subCategory
section_name: marginalia

# overrides and custom
after_check: overrides/cody_after_check.html
---
```

## Override or Append to Sections

You may override an entire section of the documentation or append more instructions to the end of a step. First, create a file at `_includes/overrides/[project_name]_[after_update].html`. Please use the convention `[project_name]_[override_type].html` to keep the overrides organized.

Then, add one of the following settings to your original project file in `projects/[project_name].md` and set it to point at your new file. For example:

```
after_check: overrides/cody_after_check.html
```

The above will include the `cody_after_check.html` file's content after the step where you refresh the webpage to view your updated contents. Alternatively, you could use `alt_check` to override the entire section.

__override entire page__
- alt_docs: overrides all documentation

__overrides entire section__
- alt_login
- alt_update
- alt_check
- alt_push

__appends to end of existing section__
- after_login
- after_update
- after_check
- after_push

## Settings

### title:
The title of your project as you would like it to display for the purposes of this documentation and in the tab title

### layout: page
This is a Jekyll thing and it needs to be set to page. Just ignore it.

### data_server_dev: cdrhdev1.unl.edu
The server where your development data files are stored, typically cdrhdev1 or cather-dev, etc.

### data_server_prod: cors1601.unl.edu
The server where your production data files are stored, typically cors1601 or cather, etc.

### media_server: cors1601.unl.edu
The media server where images, video, audio, etc are stored. Probably cors1601 or whitman-prod, etc.

### data_dir:
The directory name of your data repo on the dev and production server, typically a shortname for your project like "cody_archive" or "oscys"

### media_dir:
The directory name of your project in the `media` location on the server, which includes audio, video, and images. This is likely the name which appears in IIIF requests.

### data: "https://github.com/CDRH/data_[project]"
GitHub link for data repository (use quotation marks)

### code: "https://github.com/CDRH/[project]"
GitHub link for website code (use quotation marks)

### url_dev: "https://cdrhdev1.unl.edu/[project]"
Link to development version of website (use quotation marks)

### url_prod: "https://[project].unl.edu"
Link to production version of website (use quotation marks)

### app: orchid
Type of technology powering website. Likely `cocoon` or `orchid` (rather than rails) but potentially something else!

### search: es
The type of search powering the website, probably `es` or `solr`. If there is no search, remove or comment out this setting.

### html: true
Does the website use pre-generated HTML? True or false.

### webs: false
Does the website populate the search with webscraping? True or false.

### include_list: production_files.txt
Does this data repository rely on a file to set which files should be added to the website? If so, please list the file's name. This is optional.

### section_type and section_name
If this project is part of a larger one, such as the Whitman Marginalia data repo is a piece of the larger Whitman Archive, please note the field in Solr or Elasticsearch. You will need both `section_type` and `section_name` so that Solr or ES can be cleared with `-f section_type -r section_name`.

- section_type (the field name in Solr or ES)
- section_name (the field value in Solr or ES)

For example: `subCategory` and `marginalia` or `category` and `Writings`

### Custom things you make up

You may add additional variables to this front matter and use them with `{{ page.[your_variable] }}`.


## More information

This is a Jekyll app using the Liquid templating engine. You should be able to run it locally with `jekyll s`

If you're trying to figure out how it's all put together, check out `_includes/instructions.html`, which is the place to be if you want to figure out where other templates in `_includes` are being added and how.
