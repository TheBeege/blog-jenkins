node {
    stage('Clone') {
        git url: 'https://github.com/TheBeege/blog-jenkins'
    }

    stage('Build') {
        if (isUnix()) {
            sh './gradlew clean build'
        } else {
            bat 'gradlew.bat clean build'
        }
    }
    stage('Test'){
        if (isUnix()) {
            sh './gradlew test'
        } else {
            bat 'gradlew.bat test'
        }
    }
    stage('Deploy') {
        if (isUnix()) {
            sh 'java -jar build/libs/gs-spring-boot-0.1.0.jar &'
        } else {
            bat 'start /B java -jar build/libs/gs-spring-boot-0.10.jar'
        }
    }
}