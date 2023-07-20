# springboot-crud-k8s
Run &amp; Deploy Spring Boot CRUD Application With MySQL on K8S

1. Launch an instance from an Amazon Linux 2 or Amazon Linux AMI.
2. Connect to your instance.
3. Update the packages and package caches you have installed on your instance.
`
yum update -y

4. Install the latest Docker Engine packages.

Amazon Linux 2 amazon-linux-extras install 
docker yum install docker -y

5. Start the Docker service.

systemctl start docker 
systemctl enable docker

6. Install Conntrack:

yum install conntrack -y

7. Install k8

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube


8. Start Minikube

/usr/local/bin/minikube start --force --driver=docker

/usr/local/bin/minikube version

9. Install kubectl

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

/usr/local/bin/kubectl version

10. Make the DB up

11.yum install maven -y	

12. Create the docker image

docker build -t praveensingam1994/springboot-crud-k8s:1.0 .

13. docker login


14. /usr/local/bin/kubectl  apply -f app-deployment.yaml

15. /usr/local/bin/kubectl  get svc

16.  /usr/local/bin/minikube ip

17. http://<minikubeIP>:31125/orders


18. PUT PORT FORWARD

/usr/local/bin/kubectl port-forward --address 0.0.0.0 svc/springboot-crud-svc 8080:8080 &

[HOST PORT TO CONTAINER PORT 


kubectl port-forward --address 0.0.0.0 svc/{your service name} {external port to the Internet}:{your service port, the port your app is listening on in it's container}

for example, if my service is named badstore and is listening on 80

kubectl port-forward --address 0.0.0.0 svc/badstore 8888:80




