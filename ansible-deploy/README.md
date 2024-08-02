# How to Run the Playbook:
Save the above YAML content to a file, e.g., deploy_apache.yml.

Ensure you have an inventory file that defines the webservers group. For example, an inventory.ini file might look like this:

[webservers]
webserver1.bamise.com
webserver2.bamise.com

# Run the playbook using the ansible-playbook command:

ansible-playbook -i inventory.ini deploy_apache.yml

Make sure you have SSH access to the target machines and that they have Python installed, as Ansible uses Python to execute tasks. If you’re using a different Linux distribution, adjust the package manager and package names accordingly (e.g., yum for RHEL/CentOS).