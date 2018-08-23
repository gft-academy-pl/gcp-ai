## Agenda
- Datalab overview
- Pricing
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
* Compute resources: You incur costs of Datalab VM machine (default type type is n1-standard-1). You can minimize costs by stopping VM instances when you are not using them. 
```
datalab stop instance-name
```
* Storage resources: You are also charged for a 20GB VM Boot Disk +  200GB Standard Persistent Disk, where user notebooks are stored. 200GB disk remains after the deletion of the VM until you delete it. The following command deletes the VM instance and 20GB boot disk as well as the 200GB user notebook disk.
```
datalab delete --delete-disk instance-name
```
* Data Analysis Services: You incur Google BigQuery costs when issuing SQL queries. Also, when you use Google Cloud Machine Learning, you may incur Cloud Machine Learning Engine and/or Google Cloud Dataflow charges.
* Other resources: You may incur costs for other API requests you make within the Cloud Datalab notebook environment. 
## Cloud Datalab setup
Cloud Datalab can be created either using Cloud SDK on your local machine or using [Cloud Shell](https://cloud.google.com/shell/docs/starting-cloud-shell#starting_a_new_session) from Google Cloud Console. Run the following command to create a new Cloud Datalab VM instance:
```
 datalab create --zone zone-name instance-name
```
Run the following command to connect to a existing Cloud Datalab VM instance:
```
 datalab connect --zone zone-name --port 8081 instance-name 
```
Open your browser to the Cloud Datalab home page by clicking the Web preview button ![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/web-preview-button.png), and then selecting Change port→Port 8081.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/web-preview.png)

When you create Datalab for the first time, it adds a datalab-notebooks [Cloud Source Repository](https://console.cloud.google.com/code/develop/repo) in the project. This is a remote repository for the /content/datalab/notebooks git repository created in the docker container running in your Cloud Datalab VM instance.

The Cloud Datalab container includes ungit, a web-based git client, which allows you to make commits to the Cloud Datalab VM repo and push notebooks to the cloud remote repo from the Cloud Datalab browser UI.

To open ungit on the Cloud Datalab /content/datalab/notebooks repo, select the repository icon in the right-top section of the Google Cloud Datalab menu bar.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/ungit-icon.png)

A browser window opens on the Cloud Datalab VM repo.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/ungit-open-repo.png)
