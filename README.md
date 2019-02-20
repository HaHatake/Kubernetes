# Kubernetes
Kubernetes test repository.  
Lets learn container management :)  



## Launch Amazon Linux 2 EC2 instans and access SSH
updates  
```sudo yum -y update```

## Install docker
read the docker web  
https://docs.docker.com/install/  

install docker and autolaunch  
```sudo yum install -y docker```  
```sudo service docker start```  
```sudo usermod -a -G docker ec2-user```  
```sudo systemctl enable docker```


## get RKE(:Rancher Kubernetes Engine)  

Get rke softwares  
```curl -O https://github.com/rancher/rke/releases/download/v0.1.16/rke_linux-amd64```

### if your machine is other OS, you choise your OS version rke from here
https://github.com/rancher/rke/releases

## install RKE
read how to install rke  
https://rancher.com/announcing-rke-lightweight-kubernetes-installer/  

```sudo docker run -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/rancher```

## access RKE site
Assuming that EC2 security group able to access HTTP(80)

in your brouser
access your EC2 IPaddress and setup new password  

![2019-02-20 16 07 09](https://user-images.githubusercontent.com/20141292/53072982-0fb61300-352a-11e9-87ab-f5e6fa71f77a.png)  

setup your EC2 server IPaddress


