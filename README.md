# oauth2_proxy-setup

## oauth2_proxy

wget https://github.com/pusher/oauth2_proxy/releases/download/v3.2.0/oauth2_proxy-v3.2.0.linux-amd64.go1.11.tar.gz

tar xzvf  oauth2_proxy-v3.2.0.linux-amd64.go1.11.tar.gz

sudo mkdir /usr/bin/oauth2_proxy

sudo cp release/oauth2_proxy-linux-amd64 /usr/bin/oauth2_proxy

Move oauth2_proxy.cfg file of project into /etc/oauth2_proxy.cfg by following command

sudo cp oauth2_proxy.cfg /etc/oauth2_proxy.cfg

Move oauth2_proxy.template file of project into /etc/init.d/ by following command

sudo cp oauth2_proxy.template /etc/init.d/oauth2_proxy

sudo chmod +x /etc/init.d/oauth2_proxy

Change values in redirect_url, email_domains, client_id, and, client_secret in /etc/oauth2_proxy.cfg. Then run this command

sudo service oauth2_proxy start
