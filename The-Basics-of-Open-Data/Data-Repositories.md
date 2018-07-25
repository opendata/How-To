# Introduction

Generally, a data repository serves as the centerpiece of an open data effort. It serves as a central location to find data, a venue for standardizing practices, and a showpiece of the use of that data. In a practical sense, a repository serves as a central, searchable place for people (both outside and inside of government) to find data.

Some repository software will automatically convert data from one format to others, so even though you can only provide data in one format (e.g., CSV), it will generate XML, JSON, Excel, etc.

Some software will visualize datasets right in the browser, letting people map, sort, search, and combine datasets, without requiring any knowledge of how to program.

And some repository software allows syndication, permitting other organizations to automatically incorporate your own data (e.g., a state transportation agency could gather up all localities' transportation data and republish it).

Generally, repository software supports either uploading files to be stored in the repository, or pointing the repository at an existing website address where the file lives. The former works well for smaller governments (localities, small agencies), while the latter works well for larger governments, for which centralizing assets can be impractical.

To make a broad division, there are three types of hosting available: commercial hosting, self-hosting, and free hosting.

# Overview

An at-a-glance list of available data repositories.

| Name              | Type          | Notes
|:------------------|:--------------|:-------------|
| ArcGIS Open Data  | hosted        |              |
| CKAN              | open source   |              |
| DataHub           | free, hosted  | CKAN-powered |
| DKAN              | open source   |              |
| GitHub            | free, hosted  |              |
| JKAN              | open source   |              |
| Junar             | hosted        |              |
| NuData            | hosted        |              |
| OpenDataSoft      | hosted        |              |
| Open Data Catalog | open source   |              |
| Socrata           | hosted        |              |

Details on each follow.

# Commercial Hosting

For most governments, commercial hosting is going to be the most viable options. Paying somebody to host your own data requires little to no technical knowledge on the part of your government, and they’ll hold your hand through the process. Your organization won't have to provide any technical infrastructure (e.g., servers) or know how to program.

## ArcGIS Open Data
[ArcGIS Open Data](https://opendata.arcgis.com/about) is a new entrant in the field, having been released in late 2014. After a rocky roll-out, in which the company showed that its strengths still lay primarily in working with geodata, the platform has improved markedly since. ArcGIS Open Data is included with an ArcGIS Online contract—because of the universality of that service among municipalities and states, it’s effectively free for those existing customers. This makes it a very attractive option for governments with low levels of buy-in to an open data program, because it eliminates the cost of a data catalog. ArcGIS Open Data is only available as hosted software—it is not possible to run an instance of it on your own servers.

Clients include [Minneapolis, MN](http://opendata.minneapolismn.gov/), [Charlotte, NC](http://clt.charlotte.opendata.arcgis.com/), and [Washington, DC](http://data.dc.gov/).

## Junar

[Junar](http://www.junar.com/) is quite unlike other open data repository options. It is unlike other repositories, with an interesting feature set and a focus on data collection and analysis. Junar is uniquely bilingual, supporting English and Spanish audiences seamlessly. Their pricing is targeted at small- to medium-sized cities, starting around $10,000. Their clients include [Sacramento, CA](http://data.cityofsacramento.org/), [Palo Alto, CA](http://paloalto.opendata.junar.com/), and [Lima, Perú](http://lima.datosabiertos.pe/).

Junar’s demo site is available [upon request](http://junar.com/solicitar-demo/).

## NuCivic Data

[NuCivic Data](http://www.nucivic.com/solutions/) is based on DKAN, which was created and is maintained by nücivic. They’re a mid-range provider, in terms of pricing—their rates are much lower than socrata, but more expensive than, for example, Junar.

## CivicDashboards

Open data consulting firm [Ontodia](http://www.ontodia.com/) provides hosted CKAN under the [CivicDashboards](http://www.civicdashboards.com/) banner. They offer a free tier, for storing a small number of datasets. Their pricing is comparable with Junar’s.

## OpenDataSoft

[OpenDataSoft](http://www.opendatasoft.com/) is a French company that has moved into the U.S. market recently. They offer a free tier (up to 5 datasets, each of up to 20,000 records). Their clients include [Durham, North Carolina](https://opendurham.nc.gov/), [Paris, France](http://opendata.paris.fr/) [Corsica, France](http://opendata.corse.fr/), the [French Minister of the Interior](http://www.interieur.gouv.fr/), and [Société Nationale des Chemins de Fer Français](https://data.sncf.com/).

## Socrata Open Data

[Socrata](https://www.socrata.com/) is the major vendor in the open data repository space, with their [Socrata Open Data platform](http://www.socrata.com/products/open-data/). Socrata only offers hosted options—there is no way to run Socrata’s software on your own servers. It is both the most feature-rich and the most expensive option, with plans running hundreds of thousands of dollars a year. Their clients include many states and cities throughout the U.S., such as [San Francisco, CA](https://data.sfgov.org/), [New York, NY](https://data.cityofnewyork.us/), [Medicare](https://data.medicare.gov/), and [Maryland](https://data.maryland.gov/).

[A Socrata demo site is available](https://sandbox.demo.socrata.com/).


# Open Source Software

There are some excellent open source data repository programs that are solid options for technically savvy governments, for governments with a committment to use the open source software, or for governments with the budget to hire a consultant to deploy the software.

## CKAN

"CKAN" is nominally an initialism for "Comprehensive Knowledge Archive Network," but it’s only ever referred to as “CKAN.” A creation of the UK-based [Open Knowledge](https://okfn.org/), CKAN is the most commonly used open source data repository software. It’s written in Python, and is the standard-bearer for repository software. Lamentably, it is also known for being difficult to install, although [Docker images](https://hub.docker.com/u/ckan/) and [Amazon Web Service’s Amazon Machine Images](https://aws.amazon.com/marketplace/pp/B00JEF0278) have simplified this substantially.

Users of CKAN include [Data.gov](https://www.data.gov/), [Denver, Colorado](http://data.denvergov.org/), and [the National Oceanic and Atmospheric Administration](https://data.noaa.gov/dataset), among [many others](http://ckan.org/instances/).

CKAN consultants include [Open Knowledge](http://services.okfn.org/ckan/), [Ontodia](http://www.ontodia.com/solutions/data-publishing/), and [Accela](https://www.accela.com/), in addition to many independent consultants. Paid CKAN hosts include [Open Knowledge](http://services.okfn.org/hosting/) and [Ontodia](http://www.civicdashboards.com/).

[A CKAN demo site is available](http://demo.ckan.org/).

## DKAN

[DKAN](http://nucivic.com/dkan/) is a clone of CKAN, although it shares no code with CKAN—it’s been rewritten in PHP, as a Drupal module. For an organization that uses the Drupal content management system and also wants a data repository, DKAN is an especially good option.

Users of DKAN include [the U.S. Department of Health & Human Services](http://www.healthdata.gov/), [the U.S. Department of Agriculture](https://data.nal.usda.gov/), [Oklahoma](http://data.ok.gov/), among [others](https://github.com/NuCivic/dkan-sites).

DKAN creator and maintainer [nücivic](http://www.nucivic.com/) is the primary consultant and paid host for DKAN.

[A DKAN demo site is available](http://demo.getdkan.com/).

## JKAN

[JKAN](https://jkan.io/) is nominally based on CKAN, although it shares no code with it. [JKAN was created by Tim Wisniewski](https://usopendata.org/2016/03/28/jkan/), Philadelphia’s Chief Data Officer, as a data catalog powered by [Jekyll](https://jekyllrb.com/). The use Jekyll makes it trivial to host, because Jekyll produces a website that consists entirely of static files. Note that JKAN is a data _catalog,_ not a _repository,_ which is to say that it stores links to data and metadata about that data, but not the data itself. The data could be hosted on an FTP server, in-place on agency websites, in Amazon S3, in Dropbox, or anywhere else one might store a file for public access. Setting up a site takes just a few minutes.

The only users of JKAN right now are hobbyists, but this is likely to change soon, given the enthusiasm with which it has been received. There are no consultants or paid hosts for JKAN.

[A JKAN demo site is available](https://demo.jkan.io/).

# Free Hosting

There are some options available for free hosting of open data repositories. (Note that the above listed open source options are also free, but require setup, a server, and maintenance time.) Generally, this is the lowest tier of service provided by paid hosts.

## DataHub

The Open Knowledge Foundation provides [DataHub](http://datahub.io/), a free, CKAN-based data host. It's a large, collective repository—users don’t get their own site, although it is possible to list only one’s own data, and share a URL that only lists those datasets.

## GitHub

[GitHub](https://www.github.com/) isn’t really _meant_ as a data repository, but it can serve as one. It has none of the niceties of proper repository software (conversion of formats, retrieving data from remote URLs, etc.), but it does offer previews of some types of data, publicly tracks changes, and it’s a reasonable place to store datasets.

It does offer one significant advantage, which is that GitHub—unlike any other repository software—provides a mechanism for people to propose changes to your datasets, which you can accept or decline, if they spot mistakes or areas for enhancement.

## JKAN on GitHub

[JKAN](#jkan) is designed to be deployed onto GitHub, where the resulting data catalog can be hosted for free. In this way, GitHub can serve as a free host without sacrificing the niceties of a data catalog.

