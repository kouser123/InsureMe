pipeline {
  agent any
    tools{
      maven 'M2_HOME'
          }
   stages {
    stage('Git checkout') {
      steps {
         echo 'This is for cloning the gitrepo'
         git branch: 'main', url: 'https://github.com/kouser123/InsureMe.git'
                          }
            }
    stage('Create a Package') {
      steps {
         echo 'This will create a package using maven'
         sh 'mvn package'
                             }
            }
     stage('Publish the HTML Reports') {
      steps {
          publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/InsureMeProject/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
                        }
            }
   }
}
