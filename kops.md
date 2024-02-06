# Download the kops binary
curl -Lo kops https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

# Make the kops binary executable
chmod +x kops

# Move the kops binary to /usr/local/bin/
sudo mv kops /usr/local/bin/kops

# Verify kops installation
kops

# Check the SHA256 checksum of the kubectl binary
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check

# Install kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# Verify kubectl version
kubectl version --client

# Check Kubernetes cluster version
kubectl version

# Download the AWS CLI zip file
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Unzip the AWS CLI zip file
unzip awscliv2.zip

# Install unzip if not already installed
apt install unzip

# Download the AWS CLI zip file again in the 'downloads' directory
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Unzip the AWS CLI zip file in the 'downloads' directory
unzip awscliv2.zip

# Install AWS CLI
sudo ./aws/install

# Check the AWS CLI version
aws --version

# Configure AWS CLI with access and secret key
aws configure

# List IAM users using AWS CLI
aws iam list-users

# Set environment variables for the Kubernetes cluster name and KOPS state store
export NAME=none-clusterr.k8s.local
export KOPS_STATE_STORE=s3://none-k8s-hands-on

# Describe availability zones in the specified AWS region
aws ec2 describe-availability-zones --region us-west-2

# Set environment variable for the Kubernetes cluster name
export NAME=none-cluster.k8s.local

# Create a Kubernetes cluster configuration for AWS
kops create cluster --name=${NAME} --cloud=aws --zones=us-west-2a --discovery-store=s3://prefix-example-com-oidc-store/${NAME}/discovery

# Create a Kubernetes cluster configuration for AWS with multiple zones
kops create cluster --name=${NAME} --cloud=aws --zones=us-west-2a,us-west-2b,us-west-2c,us-west-2d --discovery-store=s3://none-k8s-hands-on/${NAME}/discovery

# Edit the Kubernetes cluster configuration
kops edit cluster --name ${NAME}

# Get information about instance groups
kops get ig

# Get information about instance groups for a specific cluster
kops get ig --name {NAME}

# Get information about instance groups for a specific cluster
kops get ig --name ${NAME}

# Edit instance group configuration for a specific availability zone
kops edit ig nodes-us-west-2a --name {NAME}

# Edit instance group configuration for a specific availability zone
kops edit ig nodes-us-west-2a

# Get information about instance groups for a specific cluster
kops get ig --name ${NAME}

# Edit instance group configuration for a specific availability zone
kops edit ig nodes-us-west-2a

# Edit instance group configuration for a specific availability zone and cluster
kops edit ig nodes-us-west-2a --name ${NAME}

# Edit instance group configuration for a specific availability zone and cluster
kops edit ig nodes-us-west-2a --name ${NAME}

# Get information about instance groups for a specific cluster
kops get ig --name ${NAME}

# Edit instance group configuration for a specific availability zone and cluster
kops edit ig nodes-us-west-2a --name ${NAME}
