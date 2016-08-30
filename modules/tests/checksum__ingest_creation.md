# Islandora Checksum / Ingest Creation

#### What is this test?
Test if checksum datastream is create during the ingestion process for new objects.

#### What is this going to test? (images, audio...)
Test basic image, large image, newspaper, pdf, audio, video, and books

#### Technology to use GUI or Drush
Use GUI and Drush

#### What is the needed test environment
Use a stock Islandora Vagrant setup without custom vagrant script

#### Files needed for this test
```
* modules/
  * tests/
    * test_files/
      * basic_images_sample_batch.zip
      * large_image_sample_batch.zip
      * newspaper_sample_issue.zip
      * basic_with_OCR.pdf
      * audio.mp3
      * video.mp4
      * books.zip
```

## Test for Success:

#### GUI:
Administration >> Islandora >> Islandora Utility Modules >> Checksum

* Check Enable Checksum checkbox
* Checksum type = SHA-512
* Datastreams to Checksum = MODS,OBJ
* Save configuration

**Ingest test files**
[Ingest with GUI](ingest_procedures.md) & [batch](modules/test/batch_ingest.md)

#### Drush:
```bash
$ drush --root=/var/www/drupal --user=admin pm-enable islandora_checksum
```
```bash
$ drush -v -u 1 --uri=http://localhost islandora_batch_scan_preprocess --type=zip --target=/path/to/archive.zip
$ drush -v -u 1 --uri=http://localhost islandora_batch_ingest
```

**Verify Success**:<br/>
Islandora Repository >> Basic Image Collection >> Manage >> PREMIS


| Field |VALUE|
| --------------| ---------------------------------------- |
| ... | ... |
| objectidentifierValue | MODS.0 |
| messageDigestAlgorithm | SHA-256 |
| messageDigest | b3cf86c63c6554735a1588d4dbcc297b75c9eff9 |
| ... | ... |
| objectidentifierValue | OBJ.0 |
| messageDigestAlgorithm | SHA-256
| messageDigest | 75821241902ef18291b67728b2f7fc65ce52d52a |
| ... | ... |


## How to Make the test fail

#### Files to test with (mismatched DC names or corrupted files)
```
* modules/
  * tests/
    * test_files/
      * basic_image_corrupt.jpg
      * large_image_Mismatch_Mods.zip
      * newspaper_invalid_naming.zip
      * basic_with_password_protected.pdf
      * audio.mp4
      * video.mp3
      * books_missing_mods.zip
```

**Ingest test files**
[Ingest with GUI](/basics/ingest_procedures.md) & [batch](modules/test/batch_ingest.md)

___
### Where to find more information
### Report a bug
### Update Readme
### Community Envolvement / Interest Groups
