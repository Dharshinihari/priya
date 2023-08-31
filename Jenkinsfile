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

    
        publishHTML target: [
            allowMissing: false,
            alwaysLinkToLastBuild: false,
            keepAll: true,
            reportDir: 'coverage',
            reportFiles: 'index.html',
            reportName: 'RCov Report'
          ]
      }
    }
  }
}
