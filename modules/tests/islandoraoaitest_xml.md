# Islandora OAI / Test XML

#### This is a test of how the mods_to_dc_oai.xsl transforms the MODS in Fedora to create the oai_dc output record



### Technology to use GUI or Drush
    Drush 6.* or the GUI

create a namespace, use drush to ingest the zip file
https://wiki.lib.utk.edu/display/DI/Ingesting


#### What is the needed test environment
 a new islandora_vagrant instance


#### Files needed for testing
`<br/> *test_files\test-data.zip <br/>* \`


#### Possible ways to test & Step by Step to replicate test

the output can be found in a brower at 
http://localhost:8000/?verb=GetRecord&metadataPrefix=oai_dc&identifier=your-namespace_PID

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
