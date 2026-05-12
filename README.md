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

4. User and Development
For ubuntu with restricted folders, we need to create a group where our users would be added

# Create a Group
sudo groupadd [name_of_group]

    -groupadd: The command to create a new group.

# Add users to Group
sudo usermod -aG [name_of_group] [user]
sudo usermod -aG [name_of_group] www-data

    usermod: User Modify. Changing user settings.

    -aG:
    -a (Append): Adds the group without removing you from your other groups (like your admin or audio groups).
    -G (Group): Specifies the group name following it.

    www-data: This is the default username Nginx uses on Ubuntu to "talk" to your files.


5. Permission & Security Setup
To simulate a production environment without compromising your /home directory security, set up the web directory permissions:

# Create the target directory
sudo mkdir -p /var/www/[folder_name]

# Give ownership to the Nginx user
sudo chown -R root:[name_of_group] /var/www

    chown: Change Owner.

    -R: Recursive. This applies the change to the folder and every file/subfolder inside.

    root:[name_of_group]: The Owner:Group format. Root is the owner; [name_of_group] is the group in charge.

sudo chmod -R 775 /var/www

    775:
    - First 7 (Root): Read (4) + Write (2) + Execute (1) = Full control.
    - Second 7 (Group/WebDevs): Read (4) + Write (2) + Execute (1). So your editor wont ask for authoritation if you save
    - Last 5 (The World): Read (4) + Execute (1). They can see the site but can't touch the code.

6. Deployment/Development Ready
To reload Nginx:
sudo nginx -t && sudo nginx -s reload

Now you can now edit the folder without the hassle of permissions, and nginx can now access the it when reference the name of the folder. 


## 👤 Author
* David John Morandarte - https://github.com/chichaproduction 
