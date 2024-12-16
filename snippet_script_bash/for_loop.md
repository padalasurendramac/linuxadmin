### basic script 

#!/bin/bash

# List of servers Arrey method
servers=("172.20.3.170" "10.0.0.5")

# Command to run on remote servers
command="cat /etc/hosts"

# Loop through each server
for server in "${servers[@]}"; do
    echo "Running command on $server"
    ssh user@$server "$command"  # Replace 'user' with your actual username
done
