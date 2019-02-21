# Kubernetes
Kubernetes test repository.  
Lets learn container management :)  



## Launch Amazon Linux 2 EC2 instans and access SSH
updates  
```sudo yum -y update```

## Install Docker
read the docker web  
https://docs.docker.com/install/  

install docker and autolaunch  
```sudo yum install -y docker```  
```sudo service docker start```  
```sudo usermod -a -G docker ec2-user```  
```sudo systemctl enable docker```


## Install RKE(:Rancher Kubernetes Engine)  
read how to install rke  
https://rancher.com/announcing-rke-lightweight-kubernetes-installer/  

```sudo docker run -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/rancher```

## Access RKE site
Assuming that EC2 security group permitted access HTTP(80)

in your brouser
access your EC2 IPaddress and setup new password  

![2019-02-20 16 07 09](https://user-images.githubusercontent.com/20141292/53072982-0fb61300-352a-11e9-87ab-f5e6fa71f77a.png)  

setup your EC2 server IPaddress  
this server IPaddress is accessed from each other clastered servers  
!Reminder : default EC2 instans haven't static Groval IPaddress.Elastic IP atatche the rancher master EC2 instans.
![2019-02-20 16 13 36](https://user-images.githubusercontent.com/20141292/53074197-7557ce80-352d-11e9-92d6-90e50fa4d4ec.png)  

## Hello RKE  
RKE start page is opended!
![2019-02-20 16 33 27](https://user-images.githubusercontent.com/20141292/53074280-ac2de480-352d-11e9-87b2-b5fadf775989.png)

