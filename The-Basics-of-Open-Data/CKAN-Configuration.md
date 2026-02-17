# CKAN Configuration

## Introduction

CKAN is often hard to install. When you do finally install it, it’s wholly functional, but capable of much more. By enabling a few features and installing a few extensions, it can be a markedly more useful product. There is [a comprehensive list of available extensions on CKAN’s website](http://extensions.ckan.org/) that is worth browsing, to see if any are useful to your particular needs.

## Installation

The biggest obstacle to using CKAN is installing it. Under most environments, it’s just plain hard.

If you're a rare government agency that is able to use Amazon Web Services, simply launch an EC2 server using [Link Digital's CKAN image](https://aws.amazon.com/marketplace/pp/B00JEF0278/ref=srh_res_product_title?ie=UTF8&sr=0-2&qid=1407963627693). Within a minute, you’ll have a CKAN server up and running.


If you can’t use AWS, then set up an Ubuntu server and [install CKAN from package](http://docs.ckan.org/en/latest/maintaining/installing/install-from-package.html). Compared to installing from source, this is trivial.
 
If you can [install it using a Docker image](http://docs.ckan.org/en/latest/maintaining/installing/install-using-docker.html), that's wonderful, but then you probably should be contributing to this How-To guide, not just reading it.

Failing those options, you can always [install from source](http://docs.ckan.org/en/ckan-2.2/install-from-source.html). This is hard.

## Paid Hosting

You can always just pay somebody to install and host CKAN. [This is a service that CKAN sells](http://ckan.org/solutions/pricing/), and more vendors are starting to offer this service.

## Recommended Additions

* [FileStore](http://docs.ckan.org/en/1117-start-new-test-suite/filestore.html): Allows files to be uploaded to and stored within CKAN, instead of merely linking to them elsewhere.
* [DataStore](http://docs.ckan.org/en/ckan-2.2/datastore.html): Opens up CSV and Excel files to store their contents, creating a lightweight API for the data and providing an on-screen preview of the data for end users.
* [DataPusher](http://docs.ckan.org/projects/datapusher/en/latest/): When files in your repository are housed on a remote server, fetches them periodically to live within and benefit from DataStore.
* [data.json](https://github.com/HHS/ckanext-datajson): Generates an inventory of all of your repository’s datasets, per the [the U.S. Project Open Data standard](https://project-open-data.cio.gov/).
* [ckanext-spatial](http://docs.ckan.org/projects/ckanext-spatial/en/latest/): Displays a map for geodata and supports spatial queries against that data.
* [ckanext-googleanalytics](https://github.com/okfn/ckanext-googleanalytics): Provides Google Analytics data for your CKAN repository.
