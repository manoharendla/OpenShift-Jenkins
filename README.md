# OpenShift-Jenkins
Jenkins 

# Prerequisities 
Openshift signUp

# How to create Jenkins instance on OpenShift

1. Logon to https://manage.openshift.com
2. Open Webconsole
3. Click on Create Project(availble on Top Right corner of the page)
4. Click on thr created project -> Browse cataloug -> Search for Jenkins -> Select Jenkins image -> Click on next and create
5. Instance will be bought up in the background. Click on view now to follow the status of the instance
6. Go to Applications -> Deployments -> select jenkins -> History -> View log, to follow the logs
7. Once you see a success message in the log, click on Overview. Click on the Jenkins URL available on the right side of the page
8. Click on login with Openshift
9. Allow all permissions
10 That's all !! Jenkins is up and running and you can start playing with Jenkins Dashboard.

# Setting up Maven in Jenkins 
1. Go to Global Tool Configuration -> Maven -> Maven Installations -> Check automatic install and save. 

# Setting up Jenkins and Github Integration
### How to establish an ssh connection between Jenkins instance and Github ? 
