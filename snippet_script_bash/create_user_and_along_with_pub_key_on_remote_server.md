### create_user_and_along_with_pub_key_on_remote_server.md


ssh "server_ip_address" "sudo useradd -m <username> && sudo mkdir -p /home/<username>/.ssh && sudo chmod 700 /home/<username>/.ssh && echo '<cat /home/spadala/.ssh/id_rsa.pub' | sudo tee /home/<username>/.ssh/authorized_keys && sudo chmod 600 /home/<username>/.ssh/authorized_keys && sudo chown -R <username>:<username> /home/<username>/.ssh && echo '<username> ALL=(ALL) NOPASSWD:ALL' | sudo tee /etc/sudoers.d/<username>"
