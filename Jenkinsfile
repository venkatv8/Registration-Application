pipeline{
    agent{label "Jenkins-Agent"}
    tool{
        jdk "Java17"
        maven "Maven3"
    }

    stages{
        stage( "cleanup workplae"){
            step{
                cleanWs()
            }
    
        }
        stage("checkout from SCM"){
            steps{
                git branch: 'main', credentialsId: 'github' , url: 'https://github.com/venkatv8/Registration-Application.git'
            }
        }
        stage("Build Application"){
            step{
                sh "mvn clean package"
            }
        }
        stage("Test Application"){
            step{
                sh "mvn test"
            }
        }
        

    }
}


