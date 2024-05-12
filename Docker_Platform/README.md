# Docker_Platform
Try to create a repository to build and use docker from github
Test to try push code from local
Test Merge code
Test Merge and deleted brach
Config Inveroment
$ sudo apt-get update 
$ sudo apt-get install bzip2 git libxml2-dev curl wget vim

Config python:
  $ wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh 
  $ bash Miniconda3-latest-Linux-x86_64.sh 
  $ rm Miniconda3-latest-Linux-x86_64.sh 
  $ source .bashrc 
  $ conda install scikit-learn pandas jupyter ipython

Config git:
$ git config --global user.name 'chithien'
$ git config --global user.email 'chithien2507@gmail.com'
$ ssh-keygen -t rsa -b 4096 -C 'chithien2507@gmail.com'
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_rsa
$ cat < ~/.ssh/id_rsa.pub
  Tạo folder nếu cần:
  $ mkdir Platform_with_git
  $ cd Platform_with_git
$ git clone git@github.com:chithien9x/Docker_Platform.git

Pull and merge code
$ git pull git@github.com:chithien9x/Docker_Platform.git
$ git merge FETCH_HEAD

Config Docker:

$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common gnupg2

$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"

$ sudo apt update
$ sudo apt install docker-ce

$ cat /etc/apt/sources.list
Or
$ ls /etc/apt/sources.list.d/

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
or
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian bullseye $(lsb_release -cs) stable"

Kiểm tra:
$ sudo systemctl status docker
$ sudo docker build -t hello-world-app .
$ sudo docker images
$ sudo docker run hello-world-app

Setup - Docker compose:
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

Sử dụng Docker:
  $ sudo docker-compose up -d
  $ sudo docker-compose restart airflow
  $ sudo docker ps
  $ sudo docker-compose down
  http://34.125.182.229:9090
  $ cd ~/Platform_with_git && git pull git@github.com:chithien9x/Docker_Platform.git && git merge FETCH_HEAD && cd ~/Platform_with_git/airflow
  $ sudo docker logs -f 4632a8a2b69e


sudo mkdir -p /usr/local/airflow/
sudo touch /usr/local/airflow/airflow.db