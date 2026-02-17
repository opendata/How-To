# Inventorying Your Data

## Introduction

The first step in building a data repository is inventorying the data that you’re already publishing. Very small governments and government agencies might have one person (hopefully you) who knows every dataset that they’re publishing, where it is, how often it’s updated, etc. But this is rarely the case. Here we’ll look at how to inventory your existing data holdings to incorporate them into your data repository.

## Finding Existing Datasets

Tracking down every dataset that you’re already publishing can be exhausting, but there’s a shortcut to make it simpler: Google.

You can use Google to search for particular file types and sequences of text, which you can use to identify every dataset already published on your website. To find every file on your site (we use `example.gov` in this example—replace it with your own organization’s domain name) that contains the text `xml`, `csv`, `json`, or `xls` in the filename (those being filename extensions of common formats for data), run this search:

```
site:example.gov filetype:csv OR filetype:xls OR filetype:json
```

This will yield somewhere between zero and thousands of results, depending on the number of data files on your site. The query can be modified to include other open and open-ish file formats, such as `shp`, `geojson`, `tsv`, `yml`, and `rdf`, among others, but you’ll get most general-purpose data files with the above query.

## Cataloging Your Finds

This is where the work gets laborious, if you’re lucky enough to already have a substantial amount of data files on your website. It’s necessary to review each search result to see if it’s useful and, if so, what it contains.

There’s likely to be a fair amount of noise, including:

* XML and JSON files that control website functions, such as indices of all pages on the site (`sitemap.xml`) and slideshow control files (e.g., `slides.xml`)
* web pages that erroneously use the file extension `xml` anywhere in them (e.g., `http://example.com/help/xml-formats/`), instead of `.html`
* geodata JSON files, which may or may not be considered noise, depending on whether you’re prepared to include these in your repository
* Excel files that, while data-bearing, are not formatted correctly (i.e., a header row with column labels, each record exactly one row long, etc.)
* files that are of such narrow applicability that they don’t make sense to include in a general-interest data repository

After a few minutes of paging through results, it becomes easy to skim right over most of the noise.

You’ll need to open each file, one at a time, to see if it merits inclusion. Then record each one, preferably in a spreadsheet, noting the URL, title, description, agency/department affiliation, and anything that's notable about it that you might need to know about later.

## Implementation

Then all of these files need to be added to your repository. In practice, this probably means entering them, one by one, into your repository software. Some software may support batch-adding many datasets by uploading a single CSV file, in which case make sure that your spreadsheet meets its requirements when you first gather the data.

## Ownership Disputes

There’s one major obstacle to adding your data inventory to your open data repository: territorialism. Many datasets are “owned” by somebody, and some of those people don’t like the idea of that dataset being available elsewhere.

You may well be told that you cannot add a dataset without permission of the owner of that dataset. You may be told that there’s a rule or a policy that you must get permission. With the exception of municipal GIS departments, this is basically never true. Ask to see the policy. Ask where the rule is written down. There is no policy, and it is not written down. If you’re bold, that means that you can push ahead, fully in compliance with policies. But if you want to play it safe with your own employment, then you’ve got to go through agency by agency and department by department, and gain permission to add their dataset. Keep in mind here, _you’re getting permission to link to a file,_ which is absurd.
