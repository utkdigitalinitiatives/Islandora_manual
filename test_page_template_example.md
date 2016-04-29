# Islandora Checksum / Ingest Creation

---

#### Test if checksum datastream is create during the ingestion process for new objects.

---

#### Test basic image, large image, newspaper, pdf, audio, video, and books

---

#### Use GUI and Drush

---

#### Use a stock Islandora Vagrant setup without custom vagrant script

---

#### Files to test with
```
test_date/
  basic_images.zip
  large_image.zip
  newspaper.zip
  basic_with_OCR.pdf
  audio.mp3
  video.mp4
  books.zip
```

---

#### Ingest test files
Proceedure here....

---
## Test for Success
#### GUI:
Administration >> Islandora >> Islandora Utility Modules >> Checksum

* Check Enable Checksum checkbox
* Checksume type = SHA-512
* Datastreams to Checksum = MODS,OBJ
* Save configuration

Possible ways to test & Step by Step to replicate test
  What is the expected output
    * Success
    * Failure

  How verify test was successful

#### Drush:
```bash
$ drush --root=/var/www/drupal --user=admin --uri=http://localhost --namespace=testing --content_models=islandora:sp_basic_image_cmodel --parent=testing:1 --type:directory ==target=/vagrant/testdata/largeimages/
$ next command....
```
## Make test fail


___
### Where to find more information
### Report a bug
### Update Readme
### Community Envolvement / Interest Groups