![Diagram](https://github.com/gft-academy-pl/gcp-data-analysis-with-bigquery/blob/master/assets/Data%20analysis%20with%20BQ%20-%20diagram%20(part_1).png?raw=true)

## Agenda
- Storage decision tree
- Cloud Storage
- gsutil 
- Cloud Storage - exercises
  - Define global variables
  - Create 2 buckets
  - Upload sample data

## Storage decision tree
![alt text][storage_options]

[storage_options]: https://cloud.google.com/images/storage-options/flowchart.svg "https://cloud.google.com/images/storage-options/flowchart.svg"

## Cloud Storage

### Concept & Purpose

Google Cloud Storage allows world-wide storage and retrieval of any amount of data at any time. You can use it for a range of scenarios including serving website content (static content multimedia), storing data for archival and disaster recovery, or distributing large data objects to users via direct download ([Google documentation]).

Widely accessible online disk space with pricing dependent on type, frequency of use and volume of the data, which is usually used to host static content and store cloud computation results.

### Cloud Storage types
![alt text][storage_types]

[Google documentation]: https://cloud.google.com/storage/docs/
[storage_types]: https://cloud.google.com/images/storage/storage-classes-desktop.svg "https://cloud.google.com/images/storage/storage-classes-desktop.svg"

## gsutil 

gsutil is a Python application that lets you access Cloud Storage from the command line (uses official [Google Cloud Storage REST API](https://cloud.google.com/storage/docs/apis) behind the scenes).

Example usages of gsutil:
* Creating and deleting buckets (no updates!).
* Uploading, downloading, deleting, moving, copying and renaming objects (files).
* Editing object metadata.
* Listing buckets and objects.
* Editing object and bucket ACLs.

More info can be found in [gsutil documentation](https://cloud.google.com/storage/docs/gsutil) and using `gsutil help`

## Cloud Storage - exercises
We need to define buckets for:
 - rate static data input
 - daily batch trade data input

### Define global variables

```
export GCP_INPUT_BUCKET=${GOOGLE_CLOUD_PROJECT}-input
export GCP_TEMP_BUCKET=${GOOGLE_CLOUD_PROJECT}-temp
```

### Create 2 buckets
 
```
gsutil mb -c regional -l us-central1 gs://${GCP_INPUT_BUCKET}
gsutil mb -c regional -l us-central1 gs://${GCP_TEMP_BUCKET}
```

### Upload sample data

```
gsutil cp gs://gft-academy-fraud-detector-public-data/trades/trades_arch.csv gs://${GCP_INPUT_BUCKET}/trades/
gsutil cp gs://gft-academy-fraud-detector-public-data/trades/trades_2016.csv gs://${GCP_INPUT_BUCKET}/trades/

gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2002.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2003.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2004.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2005.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2006.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2007.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2008.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2009.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2010.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2011.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2012.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2013.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2014.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2015.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2016.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2017.csv gs://${GCP_INPUT_BUCKET}/rates/
gsutil cp gs://gft-academy-fraud-detector-public-data/rates/rates_2018.csv gs://${GCP_INPUT_BUCKET}/rates/
```

## Documentation & Resources
- gsutils mb: https://cloud.google.com/storage/docs/gsutil/commands/mb 
- gsutils cp: https://cloud.google.com/storage/docs/gsutil/commands/cp
- bucket locations: https://cloud.google.com/storage/docs/bucket-locations

## Navigation

- [Previous Step](./00-init.md)
- [Next Step](./02-bigquery.md)
