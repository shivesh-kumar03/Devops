To create an AWS EC2 instance with a security group, follow these steps:

1. **Log in to AWS Management Console**: Access your AWS account and navigate to the EC2 dashboard.
    
2. **Launch an EC2 Instance**:
    
    - Click on "Launch Instance" in the EC2 dashboard.
        
    - Give it a name
        
    - Choose an Amazon Machine Image (AMI). For ease, select Ubuntu Server.
        
3. **Configure Instance Details**:
    
    - Select the instance type (e.g., **t2.micro for free tier eligibility**).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738434500152/20715d60-29c0-4263-b037-cb878ea03f74.png?auto=compress,format&format=webp)

4. **Create Key-Pair if you don’t have one:**

- Give Key-Pair a name

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738435643994/48fc4dfc-b814-4f64-ae78-00775aaad7de.png?auto=compress,format&format=webp)

1. **Configure Networking**:
    
    - Ensure your VPC is set up correctly.
        
    - Create a new security group named "MySecurityGroup".
        
2. **Set Up Security Group Rules**:(Temp Allowed from Everywhere)
    

- Inbound rules:
    
    - SSH (TCP, Port 22) from 0.0.0.0/0.
        
    - HTTP (TCP, Port 80) from 0.0.0.0/0.
        
    - HTTPS (TCP, Port 443) from 0.0.0.0/0.
        

3. **Add Storage**: Accept the default storage configuration unless specific needs dictate otherwise.
    
4. **Launch the Instance**:
    
    - Review and launch the instance. Download the key pair for SSH access if prompted.
5. **Find the Public IP Address**: After launching, locate the public IP in the EC2 dashboard.
    
6. **Connect via SSH**:
    
    - Use an SSH client with the command: `ssh -i my-key-pair.pem ubuntu@public-ip`.
7. **Test HTTP/HTTPS Access**:
    
    - Open a web browser and navigate to [`http://public-ip`](http://public-ip/) and [`https://public-ip`](https://public-ip/).

**Notes**:

- Ensure your key pair permissions are set correctly (`chmod 400 my-key-pair.pem`).
    
- Consider security implications of allowing traffic from anywhere; restrict access if possible in production environments.
    
- Verify the security group rules post-creation to ensure they are as intended.