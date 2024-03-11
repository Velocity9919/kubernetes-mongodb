To determine which Ubuntu release your host is running, run the following command on the host's terminal:
````
cat /etc/lsb-release
````

Import the public key used by the package management system
````
sudo apt-get install gnupg curl
````
````
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
````

Create a list file for MongoDB
````
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
````
Reload local package database
````
sudo apt-get update
````
To install the latest stable version, issue the following
````
sudo apt-get install -y mongodb-org
````
If you are unsure which init system your platform uses, run the following command:
````
ps --no-headers -o comm 1
````
You can start the mongod process by issuing the following command:
````
sudo systemctl start mongod
````
````
sudo systemctl status mongod
````
````
sudo systemctl enable mongod
````
````
sudo systemctl restart mongod
````
