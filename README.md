## Connecting Windows Machine with Ansible Playbook
This pipeline is reference to setup Jenkins with Windows server.

Pre-Requisites:
1. Install WinRM Client Pluging from Jenkins. 
2. Make sure ports are open from Jenkins server on 5985 or respective port number.
3. Install winrm on Jenkins box - Command : yum install python2-winrm.noarch
   Note: You can also install as pip3 install pywinrm or  python3 -m pip install --user --ignore-installed pywinrm
4. Store the Credentials in Jenkins under Manage Jenkins->Manage Credentials and note down the Credential ID

Code:
Jenkinsfile fetch the latest code from Git, and using credential ID define under withCredentials execute the ansible playbook define inside the stage. In the stage the playook is called "site.yml" which reference to the whoami role and execute the task define under main.yml file.
Inside roles another folder is given so that in future if we have other role we can just get it added under roles folder and reference particular role from site.yml


