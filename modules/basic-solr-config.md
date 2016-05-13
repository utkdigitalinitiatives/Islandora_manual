# Basic Solr Config #

* [What is basic-solr-config](#what-is-this)
* [Testing](#testing)
* [Using the Branches](#using-the-branches)

<a id="what-is-this"></a>
## What is this? ##

*basic-solr-config* is a collection of configuration files and XSL transforms for Fedora Commons, Fedora Generic Search (fedoragsearch or gsearch), and Solr.
The components in basic-solr-config are **not** pre-installed. The default configurations in islandora_vagrant differ slightly. The following notes point out how to use our localizations. 

<a id="testing"></a>
## Testing ##

[Tests](modules/tests/...) rely on (need to work out how to get these extra branches into the upstream repository) the [4.x-vagrant branch](...) of the basic-solr-config. See [below](#using-the-branches) for details on file placement.


<a id="using-the-branches"></a>
## Using The Branches ##

There are two (or three) branches that are significant for us:

### 4.x ### 

* *fedora-conf/fedora.fcfg* should be under production:$FEDORA_HOME/server/config
* *fedoragsearch-conf/updater* should be under production:$CATALINA_HOME/webapps/fedoragsearch/WEB-INF/classes/fgsconfigFinal/ and **replaces** the pre-existing updater directory there
* *fedoragsearch-conf/fedoragsearch.properties* should be under production:$CATALINA_HOME/webapps/fedoragsearch/WEB-INF/classes/fgsconfigFinal/ and **replaces** the pre-existing fedoragsearch.properties file there
* All of the following files and directories should be under production:$CATALINA_HOME/webapps/fedoragsearch/WEB-INF/classes/fgsconfigFinal/index/FgsIndex/
    * *islandora_transforms/* 
    * *foxmlToSolr.xslt* 
    * *index.properties*

####  Notes for production & dev: ####
* $FEDORA_HOME = /vhosts/fedora/
* $CATALINA_HOME = /vhosts/fedora/tomcat
* Ownership is usually `islandora:islandora`

### 4.x-vagrant ###

localizations for testing in islandora_vagrant


