pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
      steps {
        echo 'Testing....'
        snykSecurity(
          snykInstallation: 'Synk',
          snykTokenId: 'svc-snyk-cli-devops-jenkins',
            failOnIssues: 'false',
            severity: 'Medium',
        )
      }
    }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                snykSecurity(
                    snykInstallation: 'Synk',
                    snykTokenId: 'svc-snyk-cli-devops-jenkins',
                    failOnIssues: 'true',
                    severity: 'Medium',
        )
            }
        }
    }
}
