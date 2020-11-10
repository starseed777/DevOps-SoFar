This is a summary of core devops we've been practicing so far. 

- In essence devops is defined by the way we use these tools NOT by the tools alone. Using one of these tools individually is basically useless however when leveraging these different tools when one begins reaching its limitations is what really matters because after all devops is a practice / methodology. Even though devops culture is enabled by these tools, it still heavily depends on how we use them. Here is how we have leveraged these tools in a devops fashion.

- We utilize the cloud (AWS) for our computing resources such as EC2 instances to be able to provide an environment 
for our tools to be used. AWS has the necessary networking / security components that we can configure to satisy to our security needs (VPC,security groups,pem file, etc..).

- On a code level we are using Github for version control: our code is able to be stored in an easily accessible repository and allows for us to track changes made to our code and to be able to rollback to previous versions of the code base incase of any issues. This enables us to work with a team of multiple people on the same code base. 

- With AWS being our underlying infrastructure and Github as our version control tool, this is when our Jenkins CI/CD pipeline ( continous integration / continous delivery / continous deployment ) comes into action. With Jenkins we are now able to take the code that is being pushed to our Github repo and test / build / deploy the code everytime new code is pushed to our repository. Here's how the process goes:

- Developers push their code to the repository, a build trigger takes place via Jenkins. This code goes through our pipeline and is automatically tested + built (made operational with Maven). In the case of any issues with the code during these stages, developers can quickly debug their code with the help of the output in the Jenkins GUI. With the now operational / executable code (.war file) it gets deployed. 

- So our web application is up and running using our webserver (EC2- tomcat) but we want to have our application to be easily deployable and scalable. This is where Docker containers come in. We can now take our application with its necessary components needed to run and put it into a container that runs isolated from the host. This gives a significant performance boost and reduces the size of the application as opposed to running the application on the traditional VM. 

- Now comes time for when our application gets introduced new functionality and needs to be upgraded. This is where our previous tools used are at their limitation, for this purpose this is where ansible comes in. We use Ansible to satisfy our fresh installation and upgrade needs for our application by using the ansible playbooks. 