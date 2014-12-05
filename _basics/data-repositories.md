---
title: Data Repositories
layout: default
---

{:toc}

# Introduction

Generally, a data repository serves as the centerpiece of an open data effort. It serves as a central location to find data, a venue for standardizing practices, and a showpiece of the use of that data. In a practical sense, a repository serves as a central, searchable place for people (both outside and inside of government) to find data.

Some repository software will automatically convert data from one format to others, so even though you can only provide data in one format (e.g., CSV), it will generate XML, JSON, Excel, etc.

Some software will visualize datasets right in the browser, letting people map, sort, search, and combine datasets, without requiring any knowledge of how to program.

And some repository software allows syndicatation, permitting other organizations to automatically incorporate your own data (e.g., a state transportation agency could gather up all localities' transportation data and republish it).

Generally, repository software supports either uploading files to be stored in the repository, or pointing the repository at an existing website address where the file lives. The former works well for smaller governments (localities, small agencies), while the latter works well for larger governments, for which centralizing assets can be impractical.

To make a broad division, there are three types of hosting available: commercial hosting, self-hosting, and free hosting.

# Overview

An at-a-glance list of available data repositories.

| Name              | Type          | Notes
|:------------------|:--------------|:-------------|
| CKAN              | open source   |              |
| DataHub           | free, hosted  | CKAN-powered |
| DKAN              | open source   |              |
| GitHub            | free, hosted  |              |
| Junar             | hosted        |              |
| NuData            | hosted        |              |
| OpenData.city     | free & hosted | CKAN-powered |
| Open Data Catalog | open source   |              |
| Socrata           | hosted        |              |

Details on each follow.

# Commercial Hosting

For most governments, commercial hosting is going to be the most viable options. Paying somebody to host your own data requires little to no technical knowledge on the part of your government, and they’ll hold your hand through the process. Your organization won't have to provide any technical infrastructure (e.g., servers) or know how to program.

## Junar

* http://www.junar.com/
* less expensive than Socrata
* clients include
  * [Sacramento, CA](http://data.cityofsacramento.org/)
  * [Palo Alto, CA](http://paloalto.opendata.junar.com/)
  * [Lima, Perú](http://lima.datosabiertos.pe/)

## NuData

* http://nucivic.com/products/
* less expensive than Socrata
* based on DKAN

## OpenData.city

* http://www.opendata.city/
* Ontodia
* free tier (<=20 datasets)
* less expensive than Socrata
* for up to 100 datasets and 100GB, $499/month

## Socrata Open Data Portal

* http://www.socrata.com/products/open-data-portal/
* the major vendor of open data repositories
* most expensive option
* clients include
  * [San Francisco, CA](https://data.sfgov.org/)
  * [New York, NY](https://data.cityofnewyork.us/)
  * [Medicare](https://data.medicare.gov/)
  * [Maryland](https://data.maryland.gov/)
* [demo site](https://sandbox.demo.socrata.com/)


# Open Source Software

There are some excellent open source data repository programs that are solid options for technically savvy governments, for governments with a committment to use the open source software, or for governments with the budget to hire a consultant to deploy the software.

## CKAN

"CKAN" is nominally an initialism for "Comprehensive Knowledge Archive Network," but it’s only ever referred to as “CKAN.” A creation of the UK-based Open Knowledge Foundation, CKAN is the most commonly used open source data repository software.

* users include...
* consultants include...
  * http://www.ontodia.com/solutions/data-publishing/
* paid hosts include...
  * http://ckanexpress.com/
  * http://opendata.city/
* example site

## DKAN

DKAN is a clone of CKAN, rewritten as a Drupal module. For an organization that uses the Drupal content management system and also wants a data repository, DKAN is an especially good option.

* http://nucivic.com/dkan/, https://www.drupal.org/project/dkan
* users include...
* consultants include...
* paid hosts include...
  * [NuCivic Data](http://nucivic.com/data/enterprise/)
* demo site
  * http://demo.getdkan.com/

## Open Data Catalog

This was written for Philadelphia by Azavea. It is not as widely used as the other open source options, but it is full-featured and robust.

* https://github.com/azavea/Open-Data-Catalog
* users include...
  * [Philadelphia](http://www.opendataphilly.org/)
* consultants include...
  * Azavea

# Free Hosting

There are some options available for free hosting of open data repositories. (Note that the above listed open source options are also free, but require setup, a server, and maintenance time.) Generally, this is the lowest tier of service provided by paid hosts.

## DataHub

The Open Knowledge Foundation provides [DataHub](http://datahub.io/), a free, CKAN-based data host. It's a large, collective repository—users don’t get their own site, although it is possible to list only one’s own data, and share a URL that only lists those datasets.

## GitHub

* http://github.com/
* not really a data repository, but it can serve as one
* it has none of the niceties of proper repository software (conversion of formats, retrieving data from remote URLs, etc.), but it does offer previews of some types of data, publicly track changes, and it’s a reasonable place to store datasets
* it does offer one significant advantage, which is that GitHub—unlike any other repository software—provides a mechanism for people to propose changes to your datasets, which you can accept or decline, if they spot mistakes or areas for enhancement

## OpenData.city

A commercial host run by Ontodia, they provide [a free tier](http://www.opendata.city/pricing/) that includes 10GB of data storage, 20 datasets, and a custom subdomain (e.g., `http://springfield.opendata.city/`). It's CKAN-based.