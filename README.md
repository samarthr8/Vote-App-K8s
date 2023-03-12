# Vote-App-K8s
Deploying voting app using K8s
1. Launch an EC2 with specs- t2.medium and 20gb storage
2. Create an IAM role with Administrator access and attach it with the ec2 machine

########## Installations on the ec2 ######################
Run the following command for the required installations
kubectl
Python3-Pip
eksctl
awscli
1. sudo apt-get update
2. sudo apt install python3-pip (Install Python3-Pip)
3. pip3 install awscli --upgrade --user (use Sudo if not run in the first place)
4. sudo rm /usr/local/bin/kubectl (removing the Kubectl)
5. https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/ (link to download Kubectl consists of 3 steps)
6. sudo apt install awscli (Before running aws eks update command check awscli version. If aws cLi is not present install it with the 
   mentioned command)
7. https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html (to download eksctl) 


########## Cluster creation ######################

1. eksctl create cluster -f cluster.yaml
2. kubectl create ns local
3. kubectl apply -f vote.yaml --namespace=local
4. kubectl apply -f redis.yaml --namespace=local
5. kubectl apply -f db.yaml --namespace=local
6. kubectl apply -f worker.yaml --namespace=local
7. kubectl apply -f result.yaml --namespace=local
