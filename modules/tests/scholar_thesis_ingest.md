# Scholar Thesis Ingest Data

####What is this data? scholar_thesis_pdf_dc.zip Unpack the zip-file to see a directory containing 8 files.  
	0.  scholar_thesis_pdf_dc/
	1.  utk_gradthes-1202.pdf
	2.  utk_gradthes-1202.xml
	3.  utk_gradthes-3142.pdf
	4.  utk_gradthes-31xml
	5.  utk_gradthes-3673.pdf
	6.  utk_gradthes-36xml
	7.  utk_gradthes-5030.pdf
	8.  utk_gradthes-50xml

####Where is this data?
	- The filepath to download is:
	- https://raw.githubusercontent.com/utkdigitalinitiatives/Islandora_manual/master/modules/tests/test_files/scholar_thesis_pdf_dc.zip
	- Paste this url in a browser window and it should cause a download popup to appear.
	- Download to your favorite directory.
	- Upload to /home/vagrant
	- Unpack the zip file.  
	- The ingest target directory should be /home/vagrant/scholar_thesis_pdf_dc


####Where will this data be ingested?
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


####Test Batch Ingest of Multiple Theses with drush.
	1.  parent namespace: islandora:gradthes
	2.  child namespace: gradthes
	3.  target directory: /home/vagrant/scholar_thesis_pdf_dc
	4.  content models: islandora:sp_pdf,ir:thesisCModel
	5.  Run the test as user=vagrant.  (I have done it as user=root; there were problems.)	

####The Three Commands 
	1. vagrant@trace:~# cd /var/www/drupal
	2. vagrant@trace:/var/www/drupal# drush -v --user=vagrant --uri=http://localhost --content_models=islandora:sp_pdf,ir:thesisCModel --type=directory --target=/home/vagrant/scholar_thesis_pdf_dc  --parent=islandora:gradthes --namespace=gradthes ibsp
	3. vagrant@trace:/var/www/drupal# drush islandora_batch_ingest -v --user=vagrant --uri=http://localhost

  - About the 3 commands
	1. You have to be in the drupal home directory to use drush.
  	2. You have to be user vagrant.
	3. The drush commands may look as if they are typed on multiple lines, but it has to be typed on one continuous line.


#### What is the next step?<br/>
	1. Writing a script to perform the drush ingest of several theses automatically.
	2. Instead of focusing on ingestion, the team should be considering other tests, such as:
		-  Permission testing.
		-  Seaching for terms.
		-  Retrieving a thesis from the IR.
		-  State testing (i.e. from embargo to publish)
	

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

### Islandora Repository > ETD Collection > <br/>

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
