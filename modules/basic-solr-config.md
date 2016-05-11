# Basic Solr Config #

* [What is basic-solr-confi](#what-is-this)
* [Testing](#testing)
* [Using the Branches](#using-the-branches)

<a id="what-is-this"></a>
## What is this? ##

*basic-solr-config* is a collection of configuration files for Fedora Commons, Fedora Generic Search (fedoragsearch or gsearch), and Solr.
The components in [basic-solr-config](https://github.com/utkdigitalinitiatives/basic-solr-config) are **not** pre-installed. The default configurations in islandora_vagrant differ slightly. The following notes point out how to use our localizations. 

<a id="testing"></a>
## Testing ##

[Tests](modules/tests/...) rely on (need to work out how to get these extra branches into the upstream repository) the [4.x-vagrant branch](...) of the basic-solr-config. See [below](#using-the-branches) for details on file placement.


<a id="using-the-branches"></a>
## Using The Branches ##

There are two (or three) branches that are significant for us:

* **4.x** - our production branch
* **4.x-vagrant** - localizations for testing in islandora_vagrant
