Udagram Project!

Using cloudFormation to deploy a high-availability web app:

- Created network infrastructure template can be found in "Network.yml" file, and parameters are located in "Network-parameters.json" file
- Servers cloudformation template is called "Servers.yml" and the parameters are in "Servers.json-parameters" file

- Bastion Host has been created with configuration to SSH servers and can be accessed throguh SSH from my IP Address ONLY.
- Web App servers has read only access role on S3 buckets.
- LaunchConfiguration has been configured to launch at minmum 4 servers with Ubuntu 18 image each with 2 vCPUs and 4GB of RAM and 10 GB Storage.
- Servers are located in private subnets and website is accessible through the load balancer.
- Load balancer URL is located in the outputs section in template.
