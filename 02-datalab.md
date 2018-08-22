## Agenda
- Datalab overview
- Exercises

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/datalab-integrated.svg)

# Datalab overview
## Data Exploration
Cloud Datalab is a powerful interactive tool created to explore, analyze, transform and visualize data and build machine learning models on Google Cloud Platform. It runs on Google Compute Engine and connects to multiple cloud services easily so you can focus on your data science tasks.
## Integrated & Open Source
Cloud Datalab is built on Jupyter Notebook (formerly IPython). Notebooks are documents which contain both computer code (Python, SQL, and JavaScript) and rich text elements (paragraph, equations, figures, links, etc…). Notebook documents are both human-readable documents containing the analysis description and the results (figures, tables, etc..) as well as executable documents which can be run to perform data analysis.

Datalab notebooks simplifies data processing with Cloud BigQuery, Cloud Machine Learning Engine, Cloud Storage, and Stackdriver Monitoring. Authentication, cloud computation and source control are taken care of out-of-the-box.
## Pricing
There is no charge for using Google Cloud Datalab. However, you do pay for any Google Cloud Platform resources you use with Cloud Datalab, for example:
* Compute resources: The default Cloud Datalab VM machine type is n1-standard-1, but you can choose a different machine type . You are also charged for a 20GB Standard Persistent Disk, which is used as a Boot Disk, and a 200GB Standard Persistent Disk, where user notebooks are stored (see Storage resources). The 20GB boot disk is deleted when the VM instance is deleted, but the 200GB disk remains after the deletion of the VM until you delete it. The following command deletes the VM instance and 20GB boot disk as well as the 200GB user notebook disk.
## Datalab exercises
```
gcloud components update
```
