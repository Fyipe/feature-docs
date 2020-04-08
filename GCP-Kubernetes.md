# Google Marketplace Install and Upgrades

Fyipe is one complete DevOps and IT Ops platform. 

Fyipe lets you do: 

**Monitoring:** Monitors your website, web apps, APIs, servers and more and give you detailed metrics of things that might be wrong with your infrastructure. 

**Status Page:** Fyipe gives you a beautiful and customizable status page for your online business which helps improve transparency with your customers and cuts support costs.

**Tests:** Write automated tests for your website, API's and more and know instantly when they start failing. 

**On-Call and Incident Management:** On-Call Management lets you alert the right team at the right time saving you critical time during downtime.

**Performance Monitoring:** Monitor the performance of your apps, servers, APIs, and more and alert your team when any of your performance metrics degrades.

**Website:** https://fyipe.com

This documentation is specific to deploying and managing Fyipe using GCP Marketplace. For other deployment scenarios on Google Kubernetes Engine (GKE), please refer to the more general GKE install instructions.

## Fyipe on Google Marketplace 

### Prerequisites

- Connect to the cluster where you intend to install Fyipe via kubectl

- Ensure that your cluster has been created with a Service Account with the required access to the underlying storage infrastructure. See Using the Default GCP Service Account for more details.

- Create a dedicated namespace where you will install Fyipe. For example, if you want to create namespace fyipe, you will run the following command.

```
$ kubectl create namespace fyipe
```

### Install from GCP Marketplace Console

To deploy using the GCP Marketplace UI follow these steps:

 - From the Applications section of Google Kubernetes Engine, select Deploy from Cloud Marketplace

 - Locate Fyipe from the list of applications.

 - Select the Configure option.

 - Select the cluster on which you would like to deploy.

 - Select the dedicated namespace you have just created for  Fyipe.

 - Create a new Fyipe Service Account that will have the proper permissions.

 - Specify a name for the application instance.

 - Confirm by typing 'yes' that you are deploying in a dedicated non-default namespace

 - This will deploy a version of Fyipe using default settings.

**Note:**

It is strongly recommended that you install Fyipe in a dedicated non-default namespace on your cluster.

## Using Fyipe

============================================ 
#### IMPORTANT: After Installation Steps
============================================ 

** Thank you for installing Fyipe **
** Please be patient while the chart is being deployed **
** This usually takes few minutes or more **

To access your Fyipe app from steps below:

============================================ 
#### Make sure external IP's are assigned. 
============================================ 

Please run these commands to get Fyipe URL

```
$ kubectl get svc nginx-ingress-controller --namespace=<fyipe namespace>
```

NOTE: It may take a few minutes for the LoadBalancer IP to be available. 
If the load balancer did not assign an external IP yet (if the IP is still pending). 
Retry this command after few mins. 

============================================ 
#### Sign Up
============================================

Go to the External IP (generated from step 1) from your browser and sign up a new admin account. 
This is your master admin account (and not a user account). 
To create a user account. Please follow steps below.

============================================ 
#### Setup Email
============================================

When you're done signing up the admin account. Head over to "Settings" -> "Email"

Add your SMTP server details here to enable email alerts. 

============================================ 
#### Setup Twilio
============================================

When you're done signing up the admin account. Head over to "Settings" -> "Call and SMS"

Add your Twilio Settings here to enable call and SMS alert.

============================================ 
#### Create User
============================================

On the Admin Dahboard, go to the "Users" menu and add a new user. 
Log out of the admin account, and log in with a user account to access User's Fyipe Dashboard.

============================================ 
#### Support and Demo
============================================

Demo:
If you're looking for a personlized Fyipe demo. 
Please email us at demo@fyipe.com to schedule one. 

Support and Help:
If you're looking for help with anything,
Please email us at support@fyipe.com and we'll get back to you in less than 1 business day. 

# Deleting Fyipe

Deleting from the GCP Marketplace Console
Select Fyipe from the Applications section of the Google Kubernetes Engine Console and then select Delete.

Deleting Via the Command Line
To delete a  Fyipe instance that was installed using GCP Marketplace simply delete the all resources with the label corresponding to the application instance from the Fyipe namespace.

```
$ kubectl delete all --namespace=<fyipe namespace>
```


For example, if  Fyipe was installed in namespace fyipe and the application was named kasten-k10, then you can delete using the command.

```
$ kubectl delete all --namespace=fyipe 
```

If you followed best practices and installed  Fyipe in a dedicated namespace, you should be able to simply delete that namespace.

$ kubectl delete namespace <k10 namespace>

Regardless of the approach, all resources will be cleaned up unless you have changed the default ReclaimPolicy for PersistentVolume to something other than the default of delete. If that is the case, you will need to manually clean PVs.
