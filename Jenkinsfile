pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/saikiranganesuni/SpringPetClinic.git'
            }
        }
    
        stage('build'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('package'){
            steps{
                echo    'mvn package'
            }
        }
        stage('deploy'){
            steps{
                echo 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
