# profile_app

Project Description: The project here aims at launching a HTML webapp using the nginx server. The server in the given case is being launched inside docker containers to provide better scalability, easier and faster deployment, faster failure recovery, etc. Here I am using my online resume html file to be launched on the web using the nginx server. Here RedHat Openshift Container Platform is being used for the automated management and scaling and failure recovery of the servers. 

Technologies and products used:
•	RedHat Enterprise Linux v7.5
•	Docker Enterprise edition
•	RedHat OpenShift Container Platform
•	HTML 5
•	Nginx Server

Steps: 

•	For launching the server in a single docker container from RHEL 7.5 :

1.	Install and setup the RHEL OS.
2.	Install docker community edition the OS.
3.	Create a new folder and name the folder for example “Resume_webapp” and then copy both the HTML file and the Dockerfile provided above into that folder.
4.	Open the terminal in the same folder and run the following commands:
	   >docker build -t Resume_webapp .
	   >docker container run --detach -p 80:80 Resume_webapp
5.	These commands will run the dockerfile present in the folder. The dockerfile will automatically install the latest nginx server, copy the html file mentioned to html folder of nginx, expose the port and will start the required services. 
6.	You can now open the browser and visit “http://your-system-ip” and view that the webapp has been launched.
7.	You can also verify that it has been lauched inside a docker container by typing the below command in the terminal. It will show you that a container is running and the details of the port being exposed.
     >	docker ps
 
•	For launching the webapp in the RedHat Openshift Container Platform:

1.	Signup to RedHat Openshift Container Platform via https://www.openshift.com/products/container-platform 
2.	Login to the platform. In the left hand side of the dashboard choose the developer option. 
3.	Create a new project, name it as per your wish and open the project.
4.	Select “Topology” from the left hand side of the dashboard. Select “From Git” option.
5.	Give the git url where you have put your files. Here I used my Github project url as: https://github.com/Vaibhav-Mehta-19/profile_app.git
6.	Select “Show advanced git options” and give the “Context Dir” as the name of the folder here ‘profile_app’.
7.	Select “Nginx” as the builder of the project from the options provided. 
8.	Give the name of the application and select the checkbox asking to “create a route to the application” and click on “Create”.
9.	Openshift will now deploy the whole application on the web within a few minutes and will provide a link for you to access the application from anywhere.  You can check the status by clicking on the icon of the application appearing on the screen or by redirecting to the link provide to see the launched application.
