# Islandora OAI / Test XML

#### This is a test of how the mods_to_dc_oai.xsl transforms the MODS in Fedora to create the oai_dc output record



### Technology to use GUI or Drush
    Drush 6.* or the GUI

create a namespace:

1. create a test2 collection folder
2. give it the name "test2" as a label
3. fill in the parent namespace and the PID of the collection
4. uncheck the inherit properties checkbox
5. select the large image content model
6. put the collection namespace beside the content model selection
7. save the object

Ingesting the test files:

use drush to ingest the zip file
https://wiki.lib.utk.edu/display/DI/Ingesting

drush -v -u 1 --uri=http://localhost ibsp --content_models=islandora:sp_large_image_cmodel --type=zip --parent=islandora:test2 --namespace=test2 --target=/home/vagrant/test-files/test-data.zip

and then the second command:

drush -v -u 1 --uri=http://localhost islandora_batch_ingest
#### What is the needed test environment

 a new islandora_vagrant instance, no new modules, just the standard modules from HEAD


#### Files needed for testing
`<br/> *test_files\test-data.zip <br/>* \`


#### Possible ways to test & Step by Step to replicate test

the output can be found in a brower at: 
http://localhost:8000/?verb=GetRecord&metadataPrefix=oai_dc&identifier=test2_  (+ the pid number of the image you are testing)

What is the expected output
the oai-dc on different records will have different things to look for.




Success
the oai_dc looks as expected

Failure
the oai_dc does not look as expected

How verify test was successful
????

Optional Notes:

#### Make test fail
Optional Notes: *
