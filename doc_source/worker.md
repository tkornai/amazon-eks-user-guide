# Worker Nodes<a name="worker"></a>

Worker machines in Kubernetes are called nodes\. Amazon EKS worker nodes run in your AWS account and connect to your cluster's control plane via the cluster API server endpoint\.

Amazon EKS worker nodes are standard Amazon EC2 instances, and you are billed for them based on normal EC2 prices\. For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/)\.

By default, Amazon EKS provides AWS CloudFormation templates to spin up worker nodes in your Amazon EKS cluster\. This AMI is built on top of Amazon Linux 2, and is configured to serve as the base image for Amazon EKS worker nodes\. The AMI is configured to work with Amazon EKS out of the box, and it includes Docker, kubelet, and the AWS IAM Authenticator\. The AMI also contains a specialized bootstrap script that allows it to discover and connect to your cluster's control plane automatically\.

**Note**  
You can track security or privacy events for Amazon Linux 2 at the [Amazon Linux Security Center](https://alas.aws.amazon.com/alas2.html) or subscribe to the associated [RSS feed](https://alas.aws.amazon.com/AL2/alas.rss)\. Security and privacy events include an overview of the issue, what packages are affected, and how to update your instances to correct the issue\.

The AWS CloudFormation worker node template launches your worker nodes with specialized Amazon EC2 user data\. This user data triggers a specialized [bootstrap script](https://github.com/awslabs/amazon-eks-ami/blob/master/files/bootstrap.sh) that allows your worker nodes to discover and connect to your cluster's control plane automatically\. For more information, see [Launching Amazon EKS Worker Nodes](launch-workers.md)\.

For more information about worker nodes from a general Kubernetes perspective, see [Nodes](https://kubernetes.io/docs/concepts/architecture/nodes/) in the Kubernetes documentation\.

**Topics**
+ [Amazon EKS\-Optimized AMI](eks-optimized-ami.md)
+ [Amazon EKS Partner AMIs](eks-partner-amis.md)
+ [Launching Amazon EKS Worker Nodes](launch-workers.md)
+ [Worker Node Updates](update-workers.md)