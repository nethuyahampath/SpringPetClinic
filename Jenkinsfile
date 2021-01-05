pipeline{
    agent{
        label 'master'
    }
    tools{
        maven 'M3'
    }
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url:'https://github.com/nethuyahampath/SpringPetClinic.git'
                
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        //deploye the application in here we deploythe same server but in real world you need to develop your application inside a production server.
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclaratorPipeline/target/*.jar'
            }
        }
    }
}
