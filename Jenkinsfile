pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{

        stage('compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('clean and package'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        }
        failure {
            echo 'Please look again'
        }
    }
}
