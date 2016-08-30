# Ingest Procedures
## Basic Image

__GUI:__<br/>
Islandora Repository >> Basic Image Collection >> Manage >> Add an item to this Collection >> Next >> title >> Pick image >> Upload >> Ingest

__Drush:__<br/>
Image Folder Formatting:<br/>
![Folder Structure](Basic Image Structure.png)
<br/>
```bash
drush -v -u 1 --uri=http://localhost islandora_batch_scan_preprocess --content_models=islandora:sp_large_image_cmodel --parent=yul:F0433 --parent_relationship_pred=isMemberOfCollection --type=directory --scan_target=/tmp/batch_ingest

drush -v -u 1 --uri=http://localhost islandora_batch_ingest
```

## Large Image
__GUI:__<br/>
Islandora Repository >> Basic Image Collection >> Manage >> Add an item to this Collection >> Next >> title >> Pick image >> Upload >> Ingest

## Book
## PDF
## Manuscript
## Audio
## Video
## Compound Object


