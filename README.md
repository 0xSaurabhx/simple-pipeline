# Process
setting up website using a web server (Apache or Nginx), version control system (Git), and an automation tool (ansible). Automating deployment process by creating a pipeline that automatically deploys changes when there will be changes in the git repo.

## connecting to ssh

`ssh [your_username]@[server_ip]`




## update package & install nginx

To deploy this project run

```bash
sudo apt update
sudo apt install nginx
sudo systemctl start nginx
```
we have to make sure ngnix start on boot so for that we have to run below command.

```bash
sudo systemctl enable nginx
```
Create a server block (similar to Apache's VirtualHost) in 
`/etc/nginx/sites-available/your_domain_name`

### test ngnix config

```bash
sudo nginx -t
sudo systemctl reload nginx
```
### set up git
make sure .gitignore file is created.
```bash
mkdir /var/www/your_domain_name
cd /var/www/your_domain_name
git init
```
## automate deployment with ansible

### install ansible
```bash
pip install ansible
```

### run the playbook
```bash
ansible-playbook deploy.yml
```
