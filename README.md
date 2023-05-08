
### AWS CloudFormation Template
This AWS CloudFormation template creates a Virtual Private Cloud (VPC) with a public and a private subnet, a security group allowing SSH and HTTP access, and an EC2 instance running in the public subnet.

Parameters
The following parameters are required to run this CloudFormation template:

- VpcName: The name of the VPC.
- PublicSubName: The name of the public subnet.
- PrivateSubName: The name of the private subnet.
- InstanceName: The name of the EC2 instance.
- SecGroupName: The name of the security group.
## Resources
The CloudFormation template creates the following resources:

- MyVPC: The VPC with a CIDR block of "10.10.0.0/16" and the name specified in the VpcName parameter.
- PublicSubnet: The public subnet with a CIDR block of "10.10.1.0/24", mapped to a public IP on launch, and the name specified in the PublicSubName parameter. It is associated with the MyVPC.
- PrivateSubnet: The private subnet with a CIDR block of "10.10.2.0/24", not mapped to a public IP on launch, and the name specified in the PrivateSubName parameter. It is associated with the MyVPC.
- MySecurityGroup: The security group allowing SSH and HTTP access and the name specified in the SecGroupName parameter. It is associated with the MyVPC.
- MyEC2Instance: The EC2 instance with the image ID "ami-0c0d3776ef525d5dd", instance type "t2.micro", key pair name "test-keypair", the name specified in the InstanceName parameter, and associated with the PublicSubnet and the MySecurityGroup.
## Deployment
To deploy this CloudFormation template, you can use the AWS Management Console, AWS CLI, or AWS SDKs. You need to provide the required parameters when creating the CloudFormation stack. Once the stack is created, it will create the specified resources in your AWS account. You can then access the EC2 instance using the public IP assigned to it.




