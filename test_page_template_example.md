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

## Test for Success:

#### GUI:
Administration >> Islandora >> Islandora Utility Modules >> Checksum

* Check Enable Checksum checkbox
* Checksume type = SHA-512
* Datastreams to Checksum = MODS,OBJ
* Save configuration

**Ingest test files**
[Ingest with GUI](ingest_procedures.md) & [batch](batch_ingest.md)

#### Drush:
```bash
$ drush --root=/var/www/drupal --user=admin pm-enable islandora_checksum
$ next command....
```

**Verify Success**:<br/>
Islandora Repository >> Basic Image Collection >> Manage >> PREMIS

| Field |VALUE|
| -- | -- |
| ... | ... |
| objectidentifierValue | MODS.0 |
| messageDigestAlgorithm | SHA-256 |
| messageDigest | b3cf86c63c6554735a1588d4dbcc297b75c9eff9 |
| ... | ... |
| objectidentifierValue | OBJ.0 |
| messageDigestAlgorithm | SHA-256 
| messageDigest | 75821241902ef18291b67728b2f7fc65ce52d52a |
| ... | ... |

## Make test fail

#### Files to test with
```
test_date/
  basic_image_corrupt.jpg
  large_image_Mismatch_Mods.zip
  newspaper_invalid_naming.zip
  basic_with_password_protected.pdf
  audio.mp4
  video.mp3
  books_missing_mods.zip
```

**Ingest test files**
[Ingest with GUI](ingest_procedures.md) & [batch](batch_ingest.md)

___
### Where to find more information
### Report a bug
### Update Readme
### Community Envolvement / Interest Groups