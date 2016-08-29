# Islandora Book Batch

This module implements a batch framework, as well as a basic ZIP/directory ingester.

The ingest is a two-step process:

Preprocessing: The data is scanned, and a number of entries created in the Drupal database. There is minimal processing done at this point, so it can complete outside of a batch process.
Ingest: The data is actually processed and ingested. This happens inside of a Drupal batch.

## Tests:
[Book Batch Ingest](tests/book_batch_ingest.md) includes an Alpha Channel Tif
