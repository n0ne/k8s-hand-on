### Docker commands

- `docker images ls` - 
- `docker image pull richardchesterwood/k8s-fleetman-webapp-angular:release0-5-arm64` -
- `docker container run -p 8080:80 -d  richardchesterwood/k8s-fleetman-webapp-angular:release0-5-arm64` -
- `docker container ls` -
- `docker container stop <id>` -
- `docker container rm <id>` -



<!-- ### Installation

1. `brew install kubectl`
2. `brew install qemu`
    I use docker
3. `brew install minikube`


### Run
`minikube start --driver=qemu` or
`minikube start --driver=docker`

### Apply different configs

- `kubectl  apply -f .` - apply all yml-files in the current directory
- `kubectl  apply -f pod.yml` - apply specific yml file


### Commands
- `kubectl get pods` - command is used to list all the pods in the current Kubernetes context. It provides information about the pods, including their names, statuses, and other details.
- `kubectl get services` - command is used to retrieve information about Kubernetes services in the current context or namespace. It provides a list of services, including details such as service names, cluster IP addresses, external IP addresses (if applicable), ports, and their corresponding selectors.
- `kubectl get all` - command is used to retrieve information about all resources in the current namespace. 
- `kubectl get ingress` - this will display a list of Ingress resources along with their details, including the NAME, HOSTS, ADDRESS, PORTS, and AGE.
- `kubectl get deployments.apps` -  command is used to retrieve information about Deployments in the current namespace. 
- `kubectl delete pod <pod-name>` - delete the pod with specified name
- `kubectl delete service short-app-port` - delete the service with name `short-app-port`
- `kubectl delete deployments <deployment-name>` - delete deployment from Kubernetes cluster
- `kubectl describe pods <pod-name>` - command is used to retrieve detailed information about a specific pod in a Kubernetes cluster.
- `kubectl describe service <service-name>` - command is used to retrieve detailed information about a specific service in a Kubernetes cluster. 
- `kubectl describe deployments.apps <deployment-name>` - command is used to get detailed information about a specific Deployment in Kubernetes. 
- `kubectl logs <pod-name>` - command is used to retrieve the logs of a specific pod in a Kubernetes cluster.
- `kubectl rollout history deployment <deployment-name>` - command to view the rollout history of a deployment in Kubernetes using kubectl
- `kubectl set image deployment.app/<deployment-name> <container-name> =<docker-image-name>` - the command you provided is used to update the container image of a deployment in Kubernetes.
- `kubectl run my-pod --image=<docker-image-name> --labels="components=frontend"` - command is used to create and run a particular image on the cluster. 
- `kubectl port-forward --address 0.0.0.0 -n default service/<service-name> 31200:3000` - command is used to forward Kubernetes services to a set of local ports. I don't know why, but my minikube cluster has IP `192.168.49.2`. I need this port forward to access it locally.
- `kubectl get storageclasses.storage.k8s.io` - this command will display a list of storage classes along with their properties. If there are no storage classes created, the output will be empty.
- `kubectl get persistentvolumeclaims` - this command will display information about the existing PVCs, including their names, status, volume, and other relevant details. Make sure to run this command in the context of the Kubernetes cluster you're interested in.
- `kubectl create secret generic pg-secret --from-literal PASSWORD=my_pass` - fter running this command, a secret named pg-secret will be created in the default namespace, containing the specified key-value pair. You can then reference this secret in your Kubernetes resources, such as pods, by mounting it as a volume or using it as environment variables.
- `kubectl get secret ` - command is used to retrieve information about secrets in a Kubernetes cluster. 
- `kubectl describe secret` - command is used to display detailed information about a specific secret in a Kubernetes cluster. 
- `kubectl get secrets pg-secret --template={{.data.PASSWORD}}` - the command you provided uses the kubectl get command with a custom template to extract the value of the PASSWORD key from the pg-secret secret.
- `kubectl get secret pg-secret --template='{{.data.PASSWORD}}' | base64 --decode` - get the secret
- `kubectl delete secrets <secret-name>` - delete the secret 
- `kubectl exec -it <pod-name> -- /bin/bash` - command allows you to execute commands in a running container. 
- `kubectl describe configmaps demo-config` - describe configmaps in a Kubernetes cluster
- `kubectl rollout undo deployment <deployment-name> --ti-revision=<revision-version>` - his command will roll back the deployment named <deployment-name> to revision <revision-version>.
- `kubectl get namespaces` - get the list of namespaces in a Kubernetes cluster
- `kubectl get pods -n <namespace-name>` - the correct syntax for listing pods in a specific namespace
- `kubectl config set-context --current --namespace=<namespace-name>` - this command sets the namespace for the current context to <namespace-name>
- `kubectl api-resources --namespaced=false` - command lists API resources that are not namespaced, meaning they are cluster-wide resources. These resources are applicable to the entire Kubernetes cluster and are not confined to a specific namespace.
- `kubectl apply -f <yml-file> -n <namespace-name>` - apply file in specific namespace


#### Munukube commands
- `minikube status` - command is used to check the status of a local Minikube cluster.
- `minikube start` - start cluster minikube
- `minikube stop` - stop cluster minikube
- `minikube delete` - delete cluster minikube
- `minikube ip` - get IP address of cluster minikube
- `minikube dashboard` - command is used to open the Kubernetes Dashboard for the Minikube cluster. The Kubernetes Dashboard is a web-based user interface that provides insights into the state of your Kubernetes cluster, allowing you to view and manage various resources.
- `minikube service <service-name>` - command allows you to access a service exposed within your Minikube cluster. This command opens the specified service in your default web browser.
- `minikube tunnel` - command is used to create a route to services deployed in a Minikube cluster. It sets up a network tunnel to expose LoadBalancer services to your local machine. This is especially useful when you have services of type LoadBalancer that you want to access from your local environment.
- `minikube addons list` - this command will display a list of available addons along with their status (enabled or disabled).
- ` minikube addons enable <addon-name>` - enable minikube addon


#### Helm
- `helm repo list` - command is used to list the configured Helm repositories on your system
- `helm repo add stable https://charts.helm.sh/stable` - add stabe repo for charts
- `helm repo update` - command is used to update existing stable charts
- `helm install <chart-name> --generate-name` - command is used to install a Helm chart with an automatically generated release name.
- `helm show chart <chart-name>` - command is used to display the contents of a Helm chart
- `helm show all stable/mysql` - command is used to display all information about a Helm chart, including its chart metadata, values, and README.
- `helm install <release_name> <charts>` - In Helm 3 and later versions, when you install a chart, you provide the release name after the helm install command and then specify the chart name. `<charts>` - can be folder with charts
- `helm ls` - command is used to list releases in a Kubernetes cluster.
- `helm install --debug --dry-run <release_name> charts` - This command will not deploy the release but will give you a preview of what would happen during installation. It's a helpful way to validate your Helm chart before actually applying it to your Kubernetes cluster.
- `helm install --debug --dry-run short-service-release --set name=Sad_boo./short-service` - the same like previous command, but set value to variable `name` -->