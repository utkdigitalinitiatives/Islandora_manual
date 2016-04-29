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

#### GUI
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

Step by Step to break the test

Where to find more information
