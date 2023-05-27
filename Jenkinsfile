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
                deploy adapters: [tomcat9(credentialsId: 'tomcatdetails1', path: '', url: 'http://192.168.1.39:80')], contextPath: '/app', war: '**/*.war'
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
