# Scholar Thesis Ingest Data

####What is this data? 
These files were copied from the current trace repository at:

DATA:/arc1/TRACE/TRACE/utk_gradthes/

These are real files, not renamed or cleaned up. 

The set001 directory contains the simplest kind of objects in the repostiory:

  - one xml file named: metadata.xml
  - one pdf file named: fulltext.pdf


####Where is this data?

  - http://dlwork.lib.utk.edu/vboxes/trace_samples/set001/
  - 170.zip -- unpacked size: 14928 K
  - 1789.zip -- unpacked size: 10928 K
  - 2771.zip -- unpacked size: 10232 K
  - 3684.zip -- unpacked size: 6668 K

  Each zip file represents one master's thesis.
  
  Each zip file has one dirctory containing the files:

    - metadata.xml 
    - fulltext.pdf 

  A full descripton of these files is at:
  http://dlwork.lib.utk.edu/vboxes/trace_samples/set001/index.htm


####Downloading this data.
	- The filepath to visit is: http://dlwork.lib.utk.edu/vboxes/trace_samples/set001/
	- Download each zip file to your favorite directory.
	- Upload to /home/vagrant
	- Unpack the zip file(s).  
	- The ingest target directories should be 
	    -- /home/vagrant/170
	    -- /home/vagrant/1789
	    -- /home/vagrant/2771
	    -- /home/vagrant/3684


####Where will this data be ingested in TRACE vagrant?
	1.  The built in collection is "Graduate Theses".
	2.  The pid is islandora:gradthes.
	3.  The content models are:  islandora:sp_pdf, ir:thesisCModel.


####Test Manual Ingest of single thesis with GUI.
	1. Select the Graduate Thesis Collection.
	2. Click the Manage Tab.
	3. Click the Add and oject to this Collection link.
	4, On the dropdown menu for Content Model, select Thesis Content Model, click Next.
	5. The next page asks you to browse to a MARCXML file.  Do not browse, click Next.
	6. You have a form to fill out.  Use the DC file for data.
	7. Title is REQUIRED.  Copy it from the DC file.
	8. Date is REQUIRED. Copy it from the DC file.
	9. Fill out the form as much as you want, click Next.
	10. Check the checkbox by the question: Would you like to include a PDF document for this citation?
	11. This causes a form to appear.  Browse to the pdf.
	12. Upload the pdf, fill out the rest of the form, click Next.
	13. The thesis should be ingested to the collection.


####Test Batch Ingest of one Thesis with drush.
	1.  parent namespace: islandora:gradthes
	2.  child namespace: gradthes
	3.  target directory: /home/vagrant/170  (for example)
	4.  content models: islandora:sp_pdf,ir:thesisCModel
	5.  Run the test as user=admin.  
	6.  I have used the drush commands logged in as vagrant and logged in as root.  It did not matter which.

####The Three Commands 
	1. vagrant@trace:~# cd /var/www/drupal
	2. vagrant@trace:/var/www/drupal# drush -v --user=admin --uri=http://localhost --content_models=islandora:sp_pdf,ir:thesisCModel --type=directory --target=/home/vagrant/170  --parent=islandora:gradthes --namespace=gradthes ibsp
	3. vagrant@trace:/var/www/drupal# drush islandora_batch_ingest -v --user=admin --uri=http://localhost

  - About the 3 commands
	1. You have to be in the drupal home directory to use drush.
  	2. You have to run with  user=admin.
	3. The drush commands may look as if they are typed on multiple lines, but they each have to be typed on one continuous line.

####Test Batch Ingest of Multiple Theses with drush.

    - I will write this up when I figure out how to do it without renaming everything.
    - Having all the names be fulltext.pdf and metadata.xml in every directory is not the islandora way of doing things.

#### What is the next step?<br/>

	After ingestion:

		-  Permission testing.
		-  Seaching for terms.
		-  Retrieving a thesis from the IR.
		-  State testing (i.e. from embargo to publish)
	

#### Technology to use: *Drush*<br/>

#### What is the needed test environment<br/>
[Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)<br/>


### Islandora Repository > Graduate Thesis Collection > <br/>

#### Passing Test Results:

I don't understand this part.

<br/><br/>

#### Make Test Fail<br/>

Using an outdated version of Islandora<br/>
Using wrong data.<br/>

***Failing Test Results:***

I don't understand this part.

### Where to find more information<br/>
### Report a bug<br/>
### Update Readme<br/>
### Community Envolvement / Interest Groups
