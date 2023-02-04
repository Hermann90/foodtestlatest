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
                    sh 'chmod +x -R ${env.WORKSPACE}'
                    sh 'mvn verify -DskipTests=true -X'
                    // withSonarQubeEnv('sonarQube') {
                    //     sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Hermann90_foodtestlatest -DskipTests=true'
                    // }
                }
            }
        }
    }
}