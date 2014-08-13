---
title: CKAN Configuration
layout: default
---

{:toc}


# Introduction

* CKAN is bare-bones out of the box
* by enabling a few features and installing a few extensions, it can do a lot more
* lists of extensions [1](https://github.com/ckan/ckan/wiki/List-of-extensions), [2](https://docs.google.com/spreadsheets/d/1izCpljO6Et7zLUKcUlB4BzsMZTurENp56Iqi9kXOtgs/edit#gid=0)

# Installation

* if you're able to use Amazon Web Services, simply launch an EC2 server using [Link Digital's CKAN image](https://aws.amazon.com/marketplace/pp/B00JEF0278/ref=srh_res_product_title?ie=UTF8&sr=0-2&qid=1407963627693)
* if at all possible, run Ubuntu 12.04 and [install CKAN from package](http://docs.ckan.org/en/latest/maintaining/installing/install-from-package.html)—this is a trivial operation compared to installing from source
* if you can [install it using a Docker image](http://docs.ckan.org/en/latest/maintaining/installing/install-using-docker.html), that's wonderful, and you probably should be contributing to this How-To guide, not just reading it
* failing those options, you can always [install from source](http://docs.ckan.org/en/ckan-2.2/install-from-source.html)

# Recommended additions

* FileStore: http://docs.ckan.org/en/1117-start-new-test-suite/filestore.html
* DataStore: http://docs.ckan.org/en/ckan-2.2/datastore.html
* DataPusher: http://docs.ckan.org/projects/datapusher/en/latest/
* data.json: https://github.com/HHS/ckanext-datajson
* ckanext-spatial: https://github.com/ckan/ckanext-spatial
* ckanext-googleanalytics: https://github.com/okfn/ckanext-googleanalytics

