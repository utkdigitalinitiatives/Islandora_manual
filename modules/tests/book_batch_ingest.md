# Book Batch Ingest with Alpha Channel

#### What is this test?<br/>
Batch ingest a book with drush commands from a zip or directory. In the folder is a **DC.xml** files with 2 folders containing the **Obj** images representing pages.<br/>

#### What is this going to test?<br/>
OCR/HOCR is created for all images/pages during batch ingest<br/>

#### Technology to use: *Drush*<br/>

#### What is the needed test environment<br/>
[Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)<br/>

Test Files:
* [Test book batch with alpha channel and with book level DC Metadata ZIP](test_files/book-batch-with-alpha-channel-with-book-DC.zip)
* [Test book batch with embedded datastreams with page level DC Metadata ZIP](test_files/book-batch-with-embedded-datastreams-with-page-DC.zip)
* [Test book batch with nonalpha channel with page level DC Metadata ZIP](test_files/book-batch-with-nonalpha-channel-with-page-DC.zip)

*Note: Any of these should work. They are specially designed to test program functionality and show the different datastream layout options available.*

#### Files needed for testing<br/>
```terminal
Islandora_Manual/
├── modules
│   └── tests
│       └── test_files
│           ├── book-batch-with-alpha-channel-with-book-DC.zip
│           ├── book-batch-with-embedded-datastreams-with-page-DC.zip
│           └── book-batch-with-nonalpha-channel-with-page-DC.zip
```
<br/>
***Optional to test directory:***<br/>
 Unzip into the root folder of [Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant/)
```terminal
├── book-batch-with-alpha-channel-with-book-DC/
│   ├── 1
│   │   └── OBJ.tif
│   ├── 2
│   │   └── OBJ.tif
│   ├── 3
│   │   └── OBJ.tif
│   ├── 4
│   │   └── OBJ.tif
│   └── DC.xml
├── book-batch-with-embedded-datastreams-with-page-DC/
│   ├── 1
│   │   ├── DC.xml
│   │   └── OBJ.tif
│   └── 2
│       ├── DC.xml
│       ├── HOCR.shtml
│       ├── OBJ.tif
│       ├── OCR.asc
│       └── TN.jpg
└── book-batch-with-nonalpha-channel-with-page-DC/
    ├── 1
    │   └── OBJ.tif
    ├── 2
    │   └── OBJ.tif
    ├── 3
    │   └── OBJ.tif
    ├── 4
    │   └── OBJ.tif
    └── DC.xml
```
<br/>

#### Possible ways to test & Step by Step to replicate test<br/>
**From Terminal**
```terminal
$ cd path/to/islandora_vagrant
$ vagrant up
$ cd /var/www/drupal/
```
*For Directory*
```terminal
$ drush -v --user=admin --uri=http://localhost islandora_book_batch_preprocess --namespace=book --type=directory --target=/vagrant/book-batch-with-nonalpha-channel-with-page-DC/
$ drush -v -u 1 --uri=localhost islandora_batch_ingest
```
*For Zip*
```terminal
$ drush -v --user=admin --uri=http://localhost islandora_book_batch_preprocess --namespace=book --type=zip --target=/vagrant/book-batch-with-nonalpha-channel-with-page-DC.zip
$ drush -v -u 1 --uri=localhost islandora_batch_ingest
```

[http://localhost:8000/](http://localhost:8000/)<br/>

### Islandora Repository > Book Collection > <br/>

**With Alpha Channel | Without Alpha Channel | embedded**

Pages > Any Page > Manage > Datastreams<br/><br/>


#### Passing Test Results:

| ID       | LABEL                                          | TYPE        | MIME TYPE           | SIZE           | VERSIONS | OPERATIONS  | OPERATIONS   | OPERATIONS | OPERATIONS     |
|----------|------------------------------------------------|-------------|---------------------|----------------|----------|-------------|--------------|------------|----------------|
| RELS-EXT | Fedora Object to Object Relationship Metadata. | Inline XML  | application/rdf+xml | 757 B          | 2        |             | download     |            |                |
| MODS     | MODS Record                                    | Inline XML  | application/xml     | 179 B          | 1        | replace     | download     | delete     |                |
| DC       | DC Record                                      | Inline XML  | application/xml     | 369 B          | 1        | replace     | download     |            |                |
| OBJ      | OBJ Datastream                                 | Managed     | image/tiff          | 14.36 MiB      | 1        | replace     | download     | delete     |                |
| TN       | Thumbnail                                      | Managed     | image/jpeg          | 17.36 KiB      | 1        | replace     | download     |            | delete         |
| JPG      | Medium sized JPEG                              | Managed     | image/jpeg          | 110.51 KiB     | 1        | replace     | download     | delete     | regenerate     |
| JP2      | JPEG 2000                                      | Managed     | image/jp2           | 919.16 KiB     | 1        | replace     | download     |            | delete         |
| RELS-INT | Fedora Relationship Metadata.                  | Inline XML  | application/rdf+xml | 353 B          | 2        |             | download     | delete     |                |
| PDF      | PDF                                            | Managed     | application/pdf     | 11.35 MiB      | 1        | replace     | download     | delete     | regenerate     |
| **OCR**  | **OCR**                                        | **Managed** | **text/plain**      | **9.86 KiB**   | **1**    | **replace** | **download** | **delete** | **regenerate** |
| **HOCR** | **HOCR**                                       | **Managed** | **text/html**       | **291.33 KiB** | **1**    | **replace** | **download** | **delete** | **regenerate** |
| TECHMD   | TECHMD                                         | Managed     | application/xml     | 6.64 KiB       | 1        | replace     | download     | delete     | regenerate     |


<br/><br/>

#### Make Test Fail<br/>

Using an outdated version of Islandora<br/>

***Failing Test Results:***

| ID       | LABEL                                          | TYPE       | MIME TYPE           | SIZE       | VERSIONS | OPERATIONS | OPERATIONS | OPERATIONS | OPERATIONS |
|----------|------------------------------------------------|------------|---------------------|------------|----------|------------|------------|------------|------------|
| RELS-EXT | Fedora Object to Object Relationship Metadata. | Inline XML | application/rdf+xml | 757 B      | 2        |            | download   |            |            |
| MODS     | MODS Record                                    | Inline XML | application/xml     | 179 B      | 1        | replace    | download   | delete     |            |
| DC       | DC Record                                      | Inline XML | application/xml     | 369 B      | 1        | replace    | download   |            |            |
| OBJ      | OBJ Datastream                                 | Managed    | image/tiff          | 14.36 MiB  | 1        | replace    | download   | delete     |            |
| TN       | Thumbnail                                      | Managed    | image/jpeg          | 17.36 KiB  | 1        | replace    | download   | delete     | regenerate |
| JPG      | Medium sized JPEG                              | Managed    | image/jpeg          | 110.51 KiB | 1        | replace    | download   | delete     | regenerate |
| JP2      | JPEG 2000                                      | Managed    | image/jp2           | 919.16 KiB | 1        | replace    | download   | delete     | regenerate |
| RELS-INT | Fedora Relationship Metadata.                  | Inline XML | application/rdf+xml | 353 B      | 2        |            | download   | delete     |            |
| PDF      | PDF                                            | Managed    | application/pdf     | 11.35 MiB  | 1        | replace    | download   | delete     | regenerate |


### Where to find more information<br/>
### Report a bug<br/>
### Update Readme<br/>
### Community Envolvement / Interest Groups
