# EC2-AWS

## User data

#!/bin/bash

yes | sudo apt update

yes | sudo apt install apache2

cd /var/www/html/

echo "<h1>Server Details</h1><p><strong>Hostname:</strong>$(hostname)</p> <p><strong>IP Address:</strong>$(hostname -I | cut -d' ' -f1)</p>" | sudo tee /var/www/html/index.html

sudo systemctl restart apache2
