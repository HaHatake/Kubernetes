# Kubernetes
Kubernetes test repository.  
Lets learn container management :)  

# This method needs
AWS account  (able to create EC2 instans)
AWS key  
Azure key  


# First step ( Launch Rancher Kubernetes Engine instans)


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
RKE start page is opended! and add cluster  
![2019-02-20 16 33 27](https://user-images.githubusercontent.com/20141292/53074280-ac2de480-352d-11e9-87b2-b5fadf775989.png)

## create Rancher EC2 nodes  

select EC2  
![2019-02-21 9 53 06](https://user-images.githubusercontent.com/20141292/53135470-a502e700-35be-11e9-9920-d445b7f358cf.png)

Cluster setting  
![2019-02-21 11 12 38](https://user-images.githubusercontent.com/20141292/53138446-a5ed4600-35c9-11e9-89e9-04324e9c694e.png)



## create Template
select template plus mark  
Enter your AWS key information  
![2019-02-21 11 34 50](https://user-images.githubusercontent.com/20141292/53139365-c5d23900-35cc-11e9-9992-c6df00bc4ad4.png)

Enter VPC network setting  
![2019-02-21 11 36 50](https://user-images.githubusercontent.com/20141292/53139450-0762e400-35cd-11e9-9597-d17cf5016c8d.png)


if you encounted the error "AuthFailure: AWS was not able to validate the provided access credentials"  
  maybe your EC2 instans's time was wrong. check ntp synchronization.
  
  
## moniterling Cluster
if you encounted the error "[network] Host [*masuternode IPaddress*] is not able to connect to the following ports: [*your nodes IPaddress*]. Please check network policies and firewall rules"

check your Security Group. Permit any port (ex.79) from master node IPaddress.


