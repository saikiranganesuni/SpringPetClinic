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
                ssh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                ssh 'mvn test'
            }
        }
        stage('package'){
            steps{
                ssh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
                ssh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
