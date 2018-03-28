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
