pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("test"){
            steps{
                sh "mvn test"
            }
            
        }
        stage("build"){
            steps{
                sh 'mvn install'
            }
            
        }
        stage("deploy on test"){
            steps{
                echo 'build'
            }
            
        }
        
        
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
