# Step by step to install EdgeGallery
## Step 1. Download required gitee repositories on Deploy Node
`git clone -b Release-v1.5 https://gitee.com/edgegallery/helm-charts.git`

`git clone -b Release-v1.5 https://gitee.com/edgegallery/installer.git`

## Step 2. Docker Installation on All Nodes

### IMPORTANT NOTES: 
> Please clean up the installed docker and container on the Server and reinstall with the correct version as follows:						
						
```log
    docker-ce=5:20.10.7~3-0~ubuntu-bionic 						
    docker-ce-cli=5:20.10.7~3-0~ubuntu-bionic containerd.io
```				 	


* Uninstall old versions:

    `apt-get remove docker docker-engine docker.io containerd runc`

* Install docker 20.10.7 version:
    ```shell 
    > apt-get update
    > apt-get install ca-certificates curl gnupg lsb-release
    > curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    > echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    > apt-get update
    > apt-get install -y docker-ce=5:20.10.7~3-0~ubuntu-bionic docker-ce-cli=5:20.10.7~3-0~ubuntu-bionic containerd.io

### Expected output: 
```log
root@ubuntu-KVM:~# docker -v
Docker version 20.10.7, build f0df350 
```

## Step 3: Kubernetes Tools Installation on All Nodes

### IMPORTANT NOTES: 

> Need to install kube tool & docker cli with the correct version below:

```log 
kubeadm=1.23.4-00 						
kubelet=1.23.4-00 						
kubectl=1.23.4-00						
docker-ce=5:20.10.7~3-0~ubuntu-bionic 						
docker-ce-cli=5:20.10.7~3-0~ubuntu-bionic containerd.io						
```
        

    