# HELM-IN-k8s


Installing Helm 3 
 
Note: The workstation you are running should have the kubectl context set to the cluster you want to manage with Helm. Helm works inside Kubernetes and uses by default the kubeconfig file (“~/.kube/config”). 
 
You can use another file if you set the environment variable $KUBECONFIG. 
Download the latest helm 3 installation script. 
# https://helm.sh/docs/intro/install/ 
$ curl -fsSL -o get_helm.sh	 
https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
 
Add execute permissions to the downloaded script & run. 
 
$ chmod 700 get_helm.sh 
 
$ ./get_helm.sh 
 
Validate helm installation by executing the helm command. 
# vi /etc/sudoers 
$ helm 
 
Hub.helm.sh  
Now, add the public stable helm repo for installing the stable charts. 
 
$ helm repo add nginx-stable https://helm.nginx.com/stable 
 
helm repo add nginx https://helm.nginx.com/stable 
 
$ helm repo update  
Let’s install a stable nginx chart and test the setup. 
 
$ helm install nginxingress nginx-stable/nginx-ingress  
 
$ helm install <deploymentName> <chartName> 
 
List the installed helm chart 
 
$ helm ls 
 
You can add more number of repos 
 
$ helm repo add stable https://kubernetes-charts.storage.googleapis.com/  
$ helm search repo stable  
