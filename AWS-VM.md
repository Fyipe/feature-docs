# Post Deployment Steps

### Add Security Groups

Open Port 22, Port 80 and Port 443 on your EC2 instance. 

### Wait 15 mins

Please wait for 15-30 mins after you create your VM instance for the service to start.

**Optional:** If you want to check the status of the service. SSH into the VM and:

```
sudo k get pods
```

### Log in to Admin Account

Go to the VM External IP from your browser (https://<vm-external-ip>) and log in to new admin account. 
This is your master admin account (and not a user account). 
```
Username: admin@admin.com
Password: <your ec2 instance id>
```

### Setup Email

Head over to "Settings" -> "Email"

Add your SMTP server details here to enable email alerts.

![Add SMTP Settings](https://www.dropbox.com/s/0hzq50ajohfsdyt/Screenshot%202020-04-14%20at%209.09.58%20AM.png?dl=0&raw=1)

### Setup Twilio

Head over to "Settings" -> "Call and SMS"

Add your Twilio Settings here to enable call and SMS alert.

![Twilio](https://www.dropbox.com/s/0r4rs5ankko4d6c/Screenshot%202020-04-14%20at%209.11.02%20AM.png?dl=0&raw=1)

### Create User

On the Admin Dahboard, go to the "Users" menu 

![Users Menu](https://www.dropbox.com/s/700pgycz3stz6pu/Screenshot%202020-04-14%20at%209.12.04%20AM.png?dl=0&raw=1)

and add a new user. 

![Add User](https://www.dropbox.com/s/45a72jop84a791i/Screenshot%202020-04-14%20at%209.12.17%20AM.png?dl=0&raw=1)

Log out of the admin account, and log in with a user account to access User's Fyipe Dashboard.

### Support and Demo

Demo: If you're looking for a personlized Fyipe demo. Please email us at demo@fyipe.com to schedule one.

Support and Help: If you're looking for help with anything, Please email us at support@fyipe.com and we'll get back to you in less than 1 business day.
