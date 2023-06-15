pipeline {
    agent any
    parameters {
        choice(
            choices: ['stop' , 'start' , 'restart'],
            description: '',
            name: 'REQUESTED_ACTION')
    }

    stages {
        stage ('Stop') {
            when {
                // Only stop server if a "stop" is requested
                expression { params.REQUESTED_ACTION == 'stop' }
            }
            steps {
                echo "Hello, bitwiseman!"
            }
        }
    }
}