# TOP relearning
A website with all my TOP learning and experiences while refreshing and relearning Website Development

## 🚀 Features
* Feature 1: HTML, CSS, And JS playground

## 🛠️ Built With
* HTML
* CSS
* JS

## 📦 How to Run
1. Clone this repo: https://github.com/chichaproduction/theodinproject-relearn-webdev-basics.git
2. Open `index.html` (or run your start command)


## Additional Setup "Nginx"

This project uses Nginx as a web server to serve static assets. To maintain a production-grade environment while keeping development friction low, we follow a Sync-to-Prod workflow.

1. Installation
Install the Nginx stable binaries via the package manager:

sudo apt update
sudo apt install nginx

2. Project Structure
Deployment: /var/www/folder_name (Where Nginx reads put your web folders here)
Config: /etc/nginx/nginx.conf

3. Nginx Configuration
Update your nginx.conf (or create a file in conf.d/) with the following server block to handle the project:
server {
    listen 8080;
    server_name localhost;

    root /var/www/html-boilerplate;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}

4. Permission & Security Setup
To simulate a production environment without compromising your /home directory security, set up the web directory permissions:
# Create the target directory
sudo mkdir -p /var/www/html-boilerplate

# Give ownership to the Nginx user
sudo chown -R nginx:nginx /var/www/html-boilerplate
sudo chmod -R 755 /var/www/html-boilerplate

5. Deployment Workflow (The "Sync" Method)
Instead of editing files directly in /var/www (which requires sudo and breaks GUI search), edit in your home folder and "deploy" changes using rsync.

To deploy changes:
sudo rsync -av --delete ~/repos/html-boilerplate/ /var/www/html-boilerplate/

To reload Nginx:
sudo nginx -t && sudo nginx -s reload

## 👤 Author
* David John Morandarte - https://github.com/chichaproduction 
