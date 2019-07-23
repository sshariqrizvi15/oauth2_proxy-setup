# oauth2_proxy-setup
## Google Auth Provider
For Google, the registration steps are:

- create a new project: https://console.developers.google.com/project

- choose the new project from the top right project dropdown (only if another project is selected)

- In the project Dashboard center pane, choose “API Manager”

- In the left Nav pane, choose “Credentials”

- In the center pane, choose “OAuth consent screen” tab. Fill in “Product name shown to users” and hit save.

- In the center pane, choose “Credentials” tab.

- Open the “New credentials” drop down

- Choose “OAuth client ID”

- Choose “Web application”

- Application name is freeform, choose something appropriate

- Authorized JavaScript origins is your domain ex: https://internal.yourcompany.com

- Authorized redirect URIs is the location of oauth2/callback ex: https://internal.yourcompany.com/oauth2/callback

- Choose “Create”

- Take note of the Client ID and Client Secret

## oauth2_proxy
- wget https://github.com/pusher/oauth2_proxy/releases/download/v3.2.0/oauth2_proxy-v3.2.0.linux-amd64.go1.11.tar.gz

- tar xzvf  oauth2_proxy-v3.2.0.linux-amd64.go1.11.tar.gz

- sudo mkdir /usr/bin/oauth2_proxy

- sudo cp release/oauth2_proxy-linux-amd64 /usr/bin/oauth2_proxy

- Move oauth2_proxy.cfg file of project into /etc/oauth2_proxy.cfg by following command

    sudo cp oauth2_proxy.cfg /etc/oauth2_proxy.cfg

- Move oauth2_proxy.template file of project into /etc/init.d/ by following command

    sudo cp oauth2_proxy.template /etc/init.d/oauth2_proxy

- sudo chmod +x /etc/init.d/oauth2_proxy

- Change values in redirect_url, email_domains, client_id, and, client_secret in /etc/oauth2_proxy.cfg. Then run this command

    sudo service oauth2_proxy start

## nginx

- sudo yum install nginx

- Replace nginx.conf file of project into cd /etc/nginx/ by following command
  
  sudo mv nginx.conf /etc/nginx/nginx.conf
  
- sudo nginx
