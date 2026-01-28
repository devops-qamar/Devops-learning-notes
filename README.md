<b>What is Docker ?</b>

Definition : Docker is a containerization platform which allow us to package application with all dependence into isolated environment called container.

Container : Container is running instance of image which  consist of application + Dependencies .

[abc =def](url)

               Problem without Docker

“It works on my machine   but not on yours”
“Application breaks when we move from development to production environment”

Solution ;

Now with the help of docker we packaged each and every thing inside in a Container to ensure consistency across all .   

When we package the application inside in a container the Application runs at any system with out worrying about OS version and libraries conflicts.


Faster Deployments ; Deployments become more faster because the container starts instantly as compared to traditional Vms.

Achieve loose coupling ;  by running multiple containers as a micro-services .

        Docker Images : 

Docker image is exit blueprint of a application  , docker image contain code + library +  dep/ version and tools used in application.

Docker images are immutable .  Once the image is build it can not update we create new image for update.

Docker images store in docker hub or private registry for reusing.

     Docker Containers : 

basically docker container is running instance  of docker images .

Docker containers is isolated and light weighted and portable environments where application runs 

    Base Image in docker :

Base image is the starting point for  building docker image , a docker file inherits from base image by using keyword FORM .

Nodejs Application = base image nodejs 
Python application = base image python

                                            base images can be official builtin





