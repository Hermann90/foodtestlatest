pipeline {
    triggers {
  pollSCM('* * * * *')
    }
   agent any
    tools {
  maven 'M2_HOME'
}
    stages {

        stage("build & SonarQube analysis") {          
            steps {
                dir('./fastfood_backend/'){
                    withSonarQubeEnv('sonarQube') {
                        sh 'mvn test verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Hermann90_foodtestlatest -DskipTests=true'
                    }
                }
            }
        }
    }
}