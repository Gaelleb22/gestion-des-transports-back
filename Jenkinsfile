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
        always {
            discordSend description: '', 
            footer: 'Gaëlle', 
            image: '', 
            link: env.BUILD_URL, 
            result: currentBuild.currentResult, 
            thumbnail: '', 
            title: env.JOB_NAME, 
            webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
        }

    }
}