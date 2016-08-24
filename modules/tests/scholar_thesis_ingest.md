# Scholar Thesis Ingest Data

####What is this data? scholar_thesis_pdf_dc.zip
Unpack the zip-file to see a directory containing 8 files.
	scholar_thesis_pdf_dc/
	âââ utk_gradthes-1202.pdf
	âââ utk_gradthes-1202.xml
	âââ utk_gradthes-3142.pdf
	âââ utk_gradthes-31xml
	âââ utk_gradthes-3673.pdf
	âââ utk_gradthes-36xml
	âââ utk_gradthes-5030.pdf
	âââ utk_gradthes-50xml

####Both tests assume that there is a collection home waiting to receive new data of type pdf-dc.
        0.  These directions match the drush commands that will be presented lower down.  Feel free to change anything, but then remember to change the drush commands.
	1.  Use the GUI create a new collection. (Add collection item to top-level.)
	2.  If you make this new collection under "top-level", the parent collection is "islandora".
	3.  Name the pid for your collection "islandora:ETD"
	4.  The child name space will be "ETD"
	5.  The content model for this collection should be islandora:sp_pdf
	6.  The collection name can be "ETD Collection".  This does not affect the drush commands.

####This data may be used for two different kinds of tests.

  -  Manual GUI Test
  	- The scholar_thesis_pdf_dc.zip file should be unpacked on your desktop.
  	- Select a pair of files (one object) to ingest with the GUI.
	- For example:
		- utk_gradthes-1202.pdf
		- utk_gradthes-1202.xml
	- Use the data from the xml file to fill out the MODS ingest form in the GUI.
	- Upload the pdf with the GUI. (Click on Browse and navigate to it.)
	- View the web display and the datastream files.
	- Purpose of the GUI Test:
		- Confirm that your scholar repository is set up correctly.
		- If your drush batch ingest is having mysterious problems, but the GUI works,
		  this may help  you investigate the problem.
		- Just for fun look at the fedora pids that you created: 
		http://localhost:8080/solr/collection1/select?q=*%3A*&sort=PID+asc&rows=1000000&fl=PID&wt=csv&indent=true

  -  Drush batch ingest Test
  	- The scholar_thesis_pdf_dc.zip file should be unpacked and uploaded to your localhost vagrant.
  	- Rename the directory scholar_thesis_pdf_dc to something less cumbersome, such as etds
	- Move the etds directory to /home/vagrant/
	- This becomes your target directory /home/vagrant/etds

  - Assuming file paths, directory names, Collection pids, from above, there are 4 commands.
  	1. vagrant@trace:~$ sudo -i
	2. root@trace:~# cd /var/www/drupal
	3. root@trace:/var/www/drupal# drush -v --user=admin --uri=http://localhost --content_models=islandora:sp_pdf --type=directory --target=/home/vagrant/etds --parent=islandora:ETD ibsp
	4. root@trace:/var/www/drupal# drush islandora_batch_ingest -v --user=admin --uri=http://localhost

  - About the 4 commands
  	1. You have to be root.
	2. You have to be in the drupal home directory to use drush.
	3. This command may look wrapped, but it has to be typed on one continuous line.
	4. Another command that must be typed on one continuous line.



#### What is this test?<br/>
Batch ingest 4 pdfs representing Master's theses with drush commands from a target directory.<br/>

#### What is this going to test?<br/>
PDF Collection items for each of the 4 ETDs from  batch ingest<br/>

#### Future Test: Searching for subject terms and personal names in this collection.<br/>

#### Technology to use: *Drush*<br/>

#### What is the needed test environment<br/>
[Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)<br/>

#### Files needed for testing<br/>
```terminal
./This repo/
├── modules
│   └── tests
│       └── test_files
│           └── scholar_thesis_pdf_dc.zip
```
<br/>

[http://localhost:8000/](http://localhost:8000/)<br/>

### Islandora Repository > ETD Collection > <br/>

**With Alpha Channel | Without Alpha Channel | embedded**

Pages > Any Page > Manage > Datastreams<br/><br/>


#### Passing Test Results:

I don't understand this part.



<br/><br/>

#### Make Test Fail<br/>

Using an outdated version of Islandora<br/>

***Failing Test Results:***

I don't understand this part.

### Where to find more information<br/>
### Report a bug<br/>
### Update Readme<br/>
### Community Envolvement / Interest Groups
