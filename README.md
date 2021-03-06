### *Author: Manohar Endla*
### *Date: 3/28/18*

## Prerequisities 
Openshift signUp

## How to create Jenkins instance on OpenShift

1. Logon to https://manage.openshift.com
2. Open Webconsole
3. Click on Create Project(availble on Top Right corner of the page)
4. Click on thr created project -> Browse cataloug -> Search for Jenkins -> Select Jenkins image -> Click on next and create
5. Instance will be bought up in the background. Click on view now to follow the status of the instance
6. Go to Applications -> Deployments -> select jenkins -> History -> View log, to follow the logs
7. Once you see a success message in the log, click on Overview. Click on the Jenkins URL available on the right side of the page
8. Click on login with Openshift
9. Allow all permissions
10. That's all !! Jenkins is up and running and you can start playing with Jenkins Dashboard.

## Setting up Maven in Jenkins 
1. Go to Global Tool Configuration -> Maven -> Maven Installations -> Check automatic install and save. 

## Setting up Jenkins and Github Integration
### How to establish an ssh connection between Jenkins instance and Github ? 

1. Logon to Jenkins instance from terminal using below commands 
```
   * oc login http://manage.openshift.com
   * Provide with your username and password
   * oc get projects
   * oc project <project name>
   * oc get pods
   * oc rsh <podname>
 ```
2. Check if you ssh is already configured using `ls -la ~/.ssh/`
3. Generate ssh keys and add the ssh-agent using the link [Generate SSH Keys](https://help.github.com/enterprise/2.12/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux)
  
4. [Add the ssh public key in Github](https://help.github.com/enterprise/2.12/user/articles/adding-a-new-ssh-key-to-your-github-account/#platform-linux)

## Creating Global credentials for Git in Jenkins 
1. Logon to Jenkins
2. Click on credentials from the Left Menu
3. Provide the Github username, passowrd along with some ID and Description.


## Creating Sample Pipeline job using Github+maven to test the configuration
1. Click on new item
2. Give a name and Select Pipeline
3. Click on Ok
4. Scroll down to pipeline build step, and select try github+maven 
5. Modify the github url to point to the repo you require
6. Modify the credentails ID
7. Save and Build

## Saxon build error 

*In progres.....*



# Future Tasks
1. Script to automate the Github and Jenkins Integration
2. Automate Maven configuration in Global tool configuration
3. Automate the Github credentials creation in Jenkins
4. Creation of project in OpenShift client using expect scripting 
5. Webhooks configuration for automation build

 
## Analysis on Future Tasks:
### How to automate Github and Jenkins Integration in Openshift
1. Will be executed on OC client Machine
2. An expect script is required that takes servie account user name and password
3. oc login <login url>
4. oc new-project   


## How to Copy Jenkin jobs from One master to another master server.

### Using copy
1. Copy the Jobs folder located in JENKINS_HOME to new master server.
2. Reload the configuration from Jenkins->Manage Jenkins->Reload Configuration From Disk
3. Jobs should be visible in the new Jenkins

### Using Job Importer plugin


### Using CLI
1. java -jar jenkins-cli.jar -s http://<oldSever>:<oldSeverPort>/ list-jobs
2. java -jar jenkins-cli.jar -s http://<oldSever>:<oldSeverPort>/ get-job "NAME_OF_JOB" > job.xml
3. java -jar jenkins-cli.jar -s http://<newSever>:<newSever> create-job "NAME_OF_JOB" < job.xml

### Create  customized docker image with all available jobs



### Using Jenkins-Job-Builder
1. Create Job configuration in Yaml/Json format and store it on Github
2. Clone it to the new jenkins instance 
3. job-builder --conf ~/conf.ini --ignore-cache test ci/jobs "Jenkins-Jobs*"
4. job-builder --conf ~/conf.ini --ignore-cache update ci/jobs "Jenkins-Jobs*" -- To create the jobs on new jenkins instance



### Using DSL/Pipeline create dsl scripts for all jobs and store in github repo. 

