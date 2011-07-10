Elasticsearch Cookbook for AppCloud
---------------

You know, for Search

So, we build a web site or an application and want to add search to it, and then it hits us: getting search working is hard. We want our search solution to be fast, we want a painless setup and a completely free search schema, we want to be able to index data simply using JSON over HTTP, we want our search server to be always available, we want to be able to start with one machine and scale to hundreds, we want real-time search, we want simple multi-tenancy, and we want a solution that is built for the cloud.

"This should be easier", we declared, "and cool, bonsai cool".

[elasticsearch][2] aims to solve all these problems and more. It is an Open Source (Apache 2), Distributed, RESTful, Search Engine built on top of [Lucene][1].

Dependencies
--------

  * Your application should have a gem such as [rubberband][3] to talk to Elastic Search directly.  

Using it
--------

  * Somehow get the cookcookb provided in this git repo as a cookbook called 'elasticsearch' in your local ey-cloud-recipes fork.  Submodules work, so do other methods.

``require_recipe "elasticsearch"``  

  * Upload recipes to your environment

``ey recipes upload -e <environment>``  

  * Add an utility instance with the following naming scheme(s)
      * elasticsearch_0
      * elasticsearch_1
      * elasticsearch_2
      * ...

  * Produce /data/<appname>/shared/config/elasticsearch.yml on all instances so you can easily parse/configure elasticsearch for your usage.

Caveats
--------

No plugins are setup currently.  Enabling cloud and other plugins may be useful, have not invesitgated these yet.

Backups
--------

None automated, regular snapshot should work.  If you have a large cluster this may complicate things, please consult the [elasticsearch][2] documentation regarding that.

Warranty
--------

This cookbook is provided as is, there is no offer of support for this
recipe by Engine Yard in any capacity.  If you find bugs, please open an
issue and submit a pull request.

[1]: http://lucene.apache.org/
[2]: http://www.elasticsearch.org/
[3]: https://github.com/grantr/rubberband
