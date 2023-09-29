pipeline {
    agent any
    stages {
        stage('GIT Pull') {
            steps {
                    echo "pulled scuccessfully from GIT!!";
                    git branch: 'main', url: 'https://github.com/alok080205/FirstJenkinsPipeline.git'
            }
        }
        
        stage('Compile') {
            steps {
                echo "Compiled successfully!!";
                bat 'Build.bat'
            }
        }
        
        stage('Junit') {
            steps {
                    echo "Junit Passed Successfully!";
                    bat 'Unit.bat'
            }
        }
        
        stage('Quality-Gate') {
            steps {
                    echo "Sonarqube qulity gate passed Successfully!!";
                    bat 'Quality.bat'
            }
        }
        
        stage('Deploy') {
            steps {
                    echo "Pass!!";
                    bat 'Deploy.bat'
            }
        }
        
    }
    
    post {
        always {
            echo "This will always run"
        }
        
        success {
            echo "This will run only on success"
        }
        
        failure {
            echo "This will run only on failure"
        }
        
        unstable {
            echo "This will run only if the run was marked as unstable"
        }
        
        changed {
            echo "This will run only if the state if pipeline has changed"
            echo "For example, if the pipleine was previously failing but is now successful"
        }
    }
}
