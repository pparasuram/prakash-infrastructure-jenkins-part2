
node {
  stage('checkout sources') {
        // To avoid needing to set up permissions to your private repo, leave this url set to the assignment repo.  
        //For an extra challenge, try setting up the Jenkinsfile to pull from your repo instead
        // NEVER commit secrets (like credentials) to GitHub!!!
        git url: 'https://github.com/ColumbusStateWorkforceInnovation/infrastructure-jenkins-part2.git'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
    withMaven (maven: 'maven3') {
          sh "mvn package"
        }
    echo "hello ended maven"
  }
  // you should add a test report here
  echo "before Test"
  junit "target/surefire-reports/*.xml"
  // stage('Test') {
  finally {
    echo "testing"
    junit "target/surefire-reports/*.xml"
    echo "tested"
  }
 }
