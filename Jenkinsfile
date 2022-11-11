pipeline{
    agent {
        label 'MacOS';
    }
    stages{
        stage('Get Code from Git'){
            steps{
                echo 'Fetching files from git repo';
                git branch: 'main', credentialsId: '651b9be6-0619-4cc4-b03c-17f1c899347d', url: 'https://github.com/adak-jrnd/JenkinsPipelineMonitoring.git';
            }
        }
        stage('Compile'){
            steps{
                echo 'Compiled Successfully';
                bat 'build.bat';
                bat 'batch2.bat'
            }
        }
        stage('Build Compiled Code'){
            steps{
                echo 'Build Successfully';
            }
        }
        stage('Unit Testing'){
            steps{
                echo 'Unit Test Successfully';
            }
        }
        stage('Sonar Check'){
            steps{
                echo 'Sonar Check Successfully';
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deployment Successfully';
            }
        }
    }
    post{
        always{
            echo 'This will always run'
        }
        success{
            echo 'This will run only if success'
        }
        failure{
            echo 'This will run only if failed'
        }
        unstable{
            echo 'This will run only if the run was marked as unstable'
        }
        changed{
            echo 'This will run only if when the state of pipeline is changed'
            
        }
    }
}
