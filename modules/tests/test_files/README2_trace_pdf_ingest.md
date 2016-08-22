README2_trace_pdf_ingest.md

The trace_objects.zip file is located at:
https://github.com/utkdigitalinitiatives/Islandora_manual/tree/master/modules/tests/test_files

trace_objects.zip contains its own README file.

The trace_objects_drush.zip file is located at:
https://github.com/utkdigitalinitiatives/Islandora_manual/tree/master/modules/tests/test_files

This zip file contains 4 sub-directories and a single very simple readme that describes the url from which the pdf and xml files were obtained.
Each sub-directory contains a matched pair of name.pdf and name.xml, where the name.pdf is a master's thesis and the name.xml is the oaidc for that thesis. Each sub-directory contains everything needed to create an object in an Islandora PDF Collection.

For ingest you will need the following in VAGRANT.
1. Create a collection, content model pdf. (Aedt is the child namespace of my collection)
2. Determine the pid for that collection. (islandora:Aedt)

Fast with drush commandline.

    Unpack the directory trace_objects_drush.zip and load trace_objects_drush to vagrant (contains 8 files)
    I put mine in /vagrant/home/trace_objects_drush
    Note: each drush command is on one line even though it wraps in this display.

1. root@islandora:~# cd /var/www/drupal
2 root@islandora:/var/www/drupal# drush -v --user=admin --uri=http://localhost --content_models=islandora:sp_pdf --type=directory --target=/home/vagrant/trace_objects_drush --parent=islandora:Aetd ibsp
3. root@islandora:/var/www/drupal# drush islandora_batch_ingest -v --user=admin --uri=http://localhost

The file 160822_vagrant_transcript is located at: 
https://github.com/utkdigitalinitiatives/Islandora_manual/tree/master/modules/tests/test_files  
This shows everything that appeared on the screen for this ingest, including the 3 ingest commands.


Fast with GUI

    Unpack the directory trace_objects.zip to your desktop
    Use the directory trace_objects (contains 4 subdirections that each contain 2 files)

1. Go to Manage Your Collection >> Add an item to your collection >> Marc ingest (skip to next) >> MODS INPUT FORM
2. Navigate to trace_objects/sub-directory
3. Open the xml file in a browser. Copy data from xml to the MODS INPUT FORM.
4. Click next, Upload the pdf. (They are small enough, I have already tested this)
