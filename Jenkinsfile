pipeline {
  agent any  
  options {
    buildDiscarder(logRotator(numToKeepStr:'10')) 
  }
  stages {
    stage ('Build') { 
      steps {
        echo 'bundle install'

      
        echo 'bundle exec rake build spec'

        archive includes: 'pkg/*.gem'

    
     publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'tarket', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
      }
    }
  }
}
