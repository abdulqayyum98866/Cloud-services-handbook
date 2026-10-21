# Google Cloud Platform

## Reference

[GCP](https://cloud.google.com/)

Google Cloud Platform (GCP) is a suite of cloud computing services offered by Google that runs on the same global infrastructure Google uses for products like Google Search and Gmail.

## Connect to GCP via SSH
### Install the gcloud CLI in local terminal (My local machine is MX linux)

**Note:** You can use also `sudo apt update or upgrade`

```bash
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates gnupg curl
curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee /etc/apt/sources.list.d/google-cloud-sdk.list
sudo apt-get update
sudo apt-get install -y google-cloud-cli

````
**Note:** Now gcloud has been installed in local machine.

### Log in and set your project
**Note:** During login the web browser will open and after login (You are now logged in as [email id] shown)

```bash
gcloud auth login
gcloud projects list
gcloud config set project YOUR_PROJECT_ID

```

### List your VMs
```bash
gcloud compute instances list
```

### SSH into the VM
***Note*** Example: gcloud compute ssh my-vm --zone=us-central1-a
***Note*** The first time, it generates SSH keys automatically. Press Enter when asked for a passphrase (or set one).

```bash
gcloud compute ssh YOUR_VM_NAME --zone=YOUR_ZONE

```
### SSH by plain
```bash

ssh -i ~/.ssh/google_compute_engine YOUR_USERNAME@EXTERNAL_IP

```
***Note*** Example: ssh -i ~/.ssh/google_compute_engine you_useranme@35.200.169.253











