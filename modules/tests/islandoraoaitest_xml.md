# Islandora OAI / Test XML

#### This is a test of how the mods_to_dc_oai.xsl transforms the MODS in Fedora to create the oai_dc output record



### Technology to use GUI or Drush
    Drush 6.* or the GUI

#### What is the needed test environment

 a new islandora_vagrant instance, no new modules, just the standard modules from HEAD


#### Files needed for testing

make a directory:  /home/vagrant/test_files
copy or download the test sample files there

test-data.zip

####create a namespace from within Islandora:

1. create a test2 collection folder
2. give it the name "test2" as a label
3. fill in the parent namespace and the PID of the collection
4. uncheck the inherit properties checkbox
5. select the basic image content model
6. put the collection namespace beside the content model selection
7. save the object

####Ingesting the test files:

use drush to ingest the zip file (reference: https://wiki.lib.utk.edu/display/DI/Ingesting)

    drush -v -u 1 --uri=http://localhost ibsp --content_models=islandora:sp_basic_image --type=zip --parent=islandora:test2 --namespace=test2 --target=/home/vagrant/test-files/test-data.zip

and then the second command:

    drush -v -u 1 --uri=http://localhost islandora_batch_ingest

At this point you should have 6 basic images and metadata in the "test2" folder.

#### Possible ways to test & Step by Step to replicate test

 in the islandora admin pages, go to the oai setup,  use the standard values and click "configure" on the handler setup at the bottom of the screen.
 
 Be sure the "insert link for thumbnail box is checked.
 
 In the METADATA FORMAT section:
 
 select "OAI_DC" in the select  pull-down.
 
 check the box next to " Force include a link to the object within Islandora? ".
 
 put "identifier" in the "Field" input text box.
 
 in the transformations area, select "DC" in the datastream id box.
 
 in the first transformation select pull-down, select no transformation
 
 select nothing in the second one.
 
 save your changes and go back to the test2 collection page.
 
 
the output can be found in a brower at: 
http://localhost:8000/oai2?verb=GetRecord&metadataPrefix=oai_dc&identifier=test2_  (+ the pid number of the image you are testing)

do a view source on the page you are seeing.
the result should look like this on the first image.

     <?xml version="1.0" encoding="UTF-8"?>
    <OAI-PMH xmlns="http://www.openarchives.org/OAI/2.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/ http://www.openarchives.org/OAI/2.0/OAI-PMH.xsd"><responseDate>2016-05-02T21:26:29Z</responseDate><request>http://localhost:8000/oai2</request><GetRecord><record><header><identifier>oai:drupal-site.org:test2_27</identifier><datestamp>2016-05-02T21:02:23Z</datestamp><setSpec>islandora_test2</setSpec></header><metadata><oai_dc:dc xmlns:oai_dc="http://www.openarchives.org/OAI/2.0/oai_dc/" xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.openarchives.org/OAI/2.0/oai_dc/ http://www.openarchives.org/OAI/2.0/oai_dc.xsd">
    <dc:title>Bear in Trash Can</dc:title>
    <dc:subject>Bears</dc:subject>
    <dc:description>Transcribed from slide mount: Man from New Orleans with Sulphor [sp.]; He gave me a paper weight.; He gave me a sulphor [sp.] paperweight</dc:description>
    <dc:contributor>Derris, William (Creator)</dc:contributor>
    <dc:date>1953-06</dc:date>
    <dc:date>1953-06</dc:date>
    <dc:type>StillImage</dc:type>
    <dc:format>transparencies</dc:format>
    <dc:identifier>test2:27</dc:identifier>
    <dc:identifier>local: 0012_000603_000206_0001</dc:identifier>
    <dc:identifier>local: derris_574</dc:identifier>
    <dc:identifier>derris:574</dc:identifier>
    <dc:language>zxx</dc:language>
    <dc:relation>William Derris Collection--http://digital.lib.utk.edu/collections/derriscollection</dc:relation>
    <dc:relation>William Derris Slide Collection--MS.2123</dc:relation>
    <dc:rights>May be protected by copyright. For more information, contact Special Collections at special@utk.edu.</dc:rights>
    <dc:identifier.thumbnail>http://localhost:8000/islandora/object/test2%3A27/datastream/TN/view/Bear%20in%20Trash%20Can.jpg</dc:identifier.thumbnail><identifier>http://localhost:8000/islandora/object/test2%3A27</identifier></oai_dc:dc></metadata></record></GetRecord></OAI-PMH>


( I don't know if the above DC is correct, it looks like there are too many identifiers, but if we are just testing for whether it adds the namespaces, this doesn't.)

Now if you go back into the OAI set for the handler, and set the datastream ID to MODS, and set the first transformation to mods_to_dc_oai.xsl and do this again, you will see namespaces in the record.

At this point, you can check the data stream in Fedora to see what was created there by the transform in the batch or importer module.

(more later....)




Success

Failure

How verify test was successful
????

Optional Notes:

#### Make test fail
Optional Notes: *
