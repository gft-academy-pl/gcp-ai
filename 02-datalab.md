## Agenda
- Datalab overview
- Key concepts & components
- Pricing
- Cloud Datalab setup
- Troubleshooting

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/datalab-integrated.svg)

## Datalab overview
Cloud Datalab is a powerful interactive tool created to explore, analyze, transform and visualize data and build machine learning models on Google Cloud Platform. It runs on Google Compute Engine and connects to multiple cloud services easily so you can focus on your data science tasks.
## Key concepts & components
Cloud Datalab is packaged as a container and run in a VM (Virtual Machine) instance.

Cloud Datalab is built on Jupyter Notebook (formerly IPython). Notebooks are documents which contain both computer code (Python, SQL, and JavaScript), documentation written as markdown, and the results of code execution (text, image or, HTML/JavaScript). This way Notebooks contain analysis description, the results (figures, tables, etc..) as well as executable documents which can be run to perform data analysis.

Like a code editor or IDE, notebooks help you write code: they allow you to execute code in an interactive and iterative manner, rendering the results alongside the code. Further, when you share a notebook with team members, you can include code, markdown-formatted documentation, and results that include interactive charts, to provide them with context that goes beyond what Python or SQL code files alone can provide.

When you open a notebook, a backend “kernel” process is launched to manage the variables defined during the session and execute your notebook code. When the executed code accesses Google Cloud services such as BigQuery or Google Machine Learning Engine, it uses the service account available in the VM. Hence, the service account must be authorized to access the data or request the service. 

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
e.g.
```
datalab create --zone europe-west4-a aiworkshop
```
Run the following command to connect to a existing Cloud Datalab VM instance:
```
 datalab connect --zone zone-name --port 8081 instance-name 
```
Open your browser to the Cloud Datalab home page by clicking the Web preview button ![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/web-preview-button.png), and then selecting Change port→Port 8081.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/web-preview.png)

When you create Datalab for the first time, it adds a datalab-notebooks [Cloud Source Repository](https://console.cloud.google.com/code/develop/repo) in the project. This is a remote repository for the /content/datalab/notebooks git repository created in the docker container running in your Cloud Datalab VM instance. Notebooks are automatically saved to VM persistent disk periodically. To share your work with other users, you commit your changes using the git client to push your changes from this local workspace to the repository. 

The Cloud Datalab container includes ungit, a web-based git client, which allows you to make commits to the Cloud Datalab VM repo and push notebooks to the cloud remote repo from the Cloud Datalab browser UI.

To open [ungit](https://cloud.google.com/datalab/docs/how-to/working-with-notebooks) on the Cloud Datalab /content/datalab/notebooks repo, select the repository icon in the right-top section of the Google Cloud Datalab menu bar.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/ungit-icon.png)

A browser window opens on the Cloud Datalab VM repo.

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/ungit-open-repo.png)

## Troubleshooting
To stop the Cloud Datalab VM, click the account icon ![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/user-icon.png) in the top-right corner of the Cloud Datalab notebook, then click **Stop VM** button (VM will be automatically stopped after 90 minutes of inactivity). 

![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/datalab-server-vm-ui-about.png)

When you install new Python library, kernel restart is required: in above menu select **About Datalab**, then click the **Restart Server** option from the *About Google Cloud Datalab* dialog.
![Diagram](https://github.com/gft-academy-pl/gcp-ai/blob/master/assets/restart-server.png)
