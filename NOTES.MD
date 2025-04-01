Then go to Cloud9 terminal, resize the partition
 sudo growpart /dev/xvda 1
# Resize the root file system
 sudo xfs_growfs /
# You should be able to see the new disk size
df-h

# install kind
curl -sLo ./kind https://kind.sigs.k8s.io/dl/v0.26.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/
# Install kubectl – important! It should match cluster version 1.29
# https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html
curl -LO https://dl.k8s.io/release/v1.29.13/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/
kubectl version --client


CHECK AWS CREDENTIAL 
aws s3 ls
aws sts get-caller-identity


-------------------------------------------
Application code could be any applicaiton file - named index.js 


Docker Image Build 
go to the folder where docker file exists

view docker images
COMMAND - docker images

remove docker image
COMMAND - docker rmi -f imageid
example - docker rmi -f 7996ffchh

Build docker image 
COMMAND - docker build -t app .
app: This is the name of the Docker image
app:v1 if you want a versioned tag if not tagged then it will :latest


Now running the image locally with port assigned to it, match the port with the Dcoekrfile
COMMAND - docker run app -p 8081:8081
-p 8081:8081: This flag is used to publish a port
 first 8081 is the port on your host machine
 second 8081 is the port inside the containe
---------------------------------
-	Publish the created Docker image on Amazon ECR
Create a ECR repo manually 
go to push commands 
login success using the command given 
as we already created image now we have to push it only so use the push command
push is done 
---------------------------------
KIND CLUSTER COMMAND - kind create cluster --config kind.yaml
go to the directory where kind.yaml is present
Create kind cluster - 


-------------------------------
