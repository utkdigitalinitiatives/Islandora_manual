# Book Batch Ingest with Alpha Channel

#### What is this test?<br/>
Batch ingest a book with drush commands from the sample folder containing a book folder. In the folder is a **DC.xml** files with 2 folders containing the **Tif** images/pages.<br/>

#### What is this going to test?<br/>
OCR/HOCR is created for all images/pages during batch ingest<br/>

***Optional Notes:*** <br/>
Tesseract Open Source OCR Engine v3 cannot directly handle images with an alpha channel
```terminal
$ tesseract OBJ.tif hocr
```
<br/>

#### Technology to use: Drush<br/>

#### What is the needed test environment<br/>
Current release [Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)<br/>

#### Files needed for testing<br/>
```
* modules/
  * tests/
    * test_files/
      * with-alpha-channel-book.zip
```
<br/>
***Optional Notes:***<br/>
 Unzip into the root folder of [Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)
<br/>

#### Possible ways to test & Step by Step to replicate test<br/>
From Terminal 
```terminal
$ cd path/to/islandora_vagrant
$ vagrant up
$ cd /var/www/drupal/
$ drush -v --user=admin --uri=http://localhost islandora_book_batch_preprocess --namespace=book --type=directory --target=/vagrant/with-alpha-channel-book/
$ drush -v -u 1 --uri=localhost islandora_batch_ingest
```

[http://localhost:8000/](http://localhost:8000/)<br/>

Islandora Repository > Book Collection > The independent truth.<br/>
Pages > book:75-1 > Manage > Datastreams

##### Ideal Results:
book:75-2 - book:76

| ID	| LABEL	| TYPE	| MIME TYPE	| SIZE	| VERSIONS	| OPERATIONS | OPERATIONS | OPERATIONS | OPERATIONS |
|--|--|--|--|--|--|--|--|--|--|--|
| RELS-EXT	|Fedora Object to Object Relationship Metadata.	| Inline XML |	application/rdf+xml	| 757 B	| 2		|   | download |	|  |		
| MODS	| MODS Record	| Inline XML	| application/xml	| 179 B	| 1	| replace	| download		| delete |	|
| DC	| DC Record	| Inline XML	| application/xml	| 369 B	| 1	| replace	| download |	|  |		
| OBJ	| OBJ Datastream	| Managed	| image/tiff	| 14.36 MiB	| 1	| replace	| download		| delete| 	|
| TN	| Thumbnail	| Managed	| image/jpeg	| 17.36 KiB	| 1	| replace	| download	| |	delete	| regenerate|
| JPG	| Medium sized JPEG	| Managed	| image/jpeg	| 110.51 KiB	| 1	| replace	|download		| delete	| regenerate|
| JP2	| JPEG 2000	| Managed	| image/jp2	| 919.16 KiB	| 1	| replace	| download	| 	| delete	| regenerate| 
| RELS-INT	| Fedora Relationship Metadata.	| Inline XML	| application/rdf+xml	| 353 B	| 2		|  | download	| delete |  |
| PDF	| PDF	| Managed	| application/pdf	| 11.35 MiB	| 1	| replace	| download	| delete	| regenerate|
| **OCR**	| **OCR**	| **Managed**	| **text/plain**	| **9.86 KiB**	| **1**	| **replace**	| **download**	| **delete**	| **regenerate**| 
| **HOCR**	| **HOCR**	| **Managed**	| **text/html**	| **291.33 KiB**	| **1**	| **replace**	| **download**	|	**delete**	| **regenerate**|
| TECHMD	| TECHMD	| Managed	| application/xml	| 6.64 KiB	| 1	| replace	|download	|	delete	| regenerate|


#### Make test fail<br/>
Optional Notes:<br/>
<br/>
___
### Where to find more information<br/>
### Report a bug<br/>
### Update Readme<br/>
### Community Envolvement / Interest Groups