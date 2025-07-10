# Deploy-SpringBoot-Application-in-AWS
Deploy SpringBoot Application in AWS



======================================
# How to SpringBoot App in AWS Cloud
======================================

# @@ Step-1 : Create EC2 Linux VM and Connect with that VM using SSH client

		ADMIN@DESKTOP-O04I6QM MINGW64 /c/keypairsaws
		$ ssh -i "myec2kp.pem" ec2-user@ec2-18-233-225-116.compute-1.amazonaws.com
		[ec2-user@ip-172-31-89-79 ~]$ whoami
		ec2-user

# @@ Step-2 : Install git client s/w

		$ sudo yum install git -y

		$ git -v
		$ git --version

# @@ Step-3 : Clone project git repo (springboot app)

		$ git clone https://github.com/ashokitschool/spring-boot-docker-app.git

# @@ Step-4 : Install Maven s/w

		$ sudo yum install maven -y

		$ mvn -version or mvn -v

		$ java -version

# @@ Step-5 : Package project as jar file

		$ cd spring-boot-docker-app

		$ ls -l

		$ mvn clean package

		$ ls -l target

# @@ Step-6 : Run the jar file

		// run app in interactive mode
		$ java -jar target/spring-boot-docker-app.jar

		// run the application in background (detached mode)
		$ nohup java -jar target/spring-boot-docker-app.jar &

		// check logs of the application
		$ tail nohup.out

# @@ Step-7 : Enable Embedded server port (8080) in security group inbound rules

# @@ Step-8 : Access Our Application URL in browser

		URL : http://public-ip:8080/
    in our testing case: http://18.233.225.116:8080/

============================
# How to stop the application
============================

=> Identify the running process of our application based on port number

		$ sudo lsof -i:8080

=> Kill that process using process id (PID)

		$ kill -9 <PID>		

		$ sudo lsof -i:8080
