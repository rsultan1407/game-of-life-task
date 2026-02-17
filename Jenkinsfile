pipeline {
    agent {label 'Node 1'}
    options {
         timeout(time: 1, unit: 'HOURS')
    }
    parameters {
        choice(name: 'ENVIRONMENT',
         choices: ['mvn clean install', 'mvn package'],
          description: 'Maven Goals')
    }
    triggers {
        pollSCM('* 1 * * *')
    }
    tools {
        jdk 'JDK-8'
        maven 'maven 3.9.12'
    } 

    stages {
         stage ('vcs git') {
            steps{ 
                git url: 'https://github.com/muthyalasaikiran/game-of-life.git',
                    branch: 'master'
            }
        }
        stage ('build and package'){
            steps{
                 echo "choice: ${params.ENVIRONMENT}"

            }
        }
    }
}
    
    
