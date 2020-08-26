pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven"
    }

    stages {
        stage('Build') {
            steps {
                sh "mvn clean compile"
            }
        }
        
    }

    post {
        failure {
            discordSend description: "Commit : ${env.GIT_COMMIT} - ${env.BUILD_URL}", 
            footer: 'Gaëlle', 
            result: currentBuild.currentResult, 
            title: env.JOB_NAME, 
            webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
        }

        success {
            script {
                discordSend description: "Commit : ${env.GIT_COMMIT} - ${env.BUILD_URL}", 
            footer: 'Gaëlle', 
            result: currentBuild.currentResult, 
            title: env.JOB_NAME, 
            webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
            }
            when {
                branch 'master'
            }
        }

    }
}