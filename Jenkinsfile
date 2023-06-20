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
                echo "Hello, the server is stopped!"
                sh 'sudo - su
                /opt/tomcat/bin/shutdown.sh
                '
            }
        }
        stage ('Start') {
            when {
                // Only start server if a "start" is requested
                expression { params.REQUESTED_ACTION == 'start' }
            }
            steps {
                echo "Hello, the server is started!"
                sh 'sudo - su
                /opt/tomcat/bin/startup.sh
                '
            }
        }
        stage ('Restart') {
            when {
                // Only start server if a "restart" is requested
                expression { params.REQUESTED_ACTION == 'restart' }
            }
            steps {
                echo "Hello, the server is restarted!"
                	sh 'sudo su -
                    /opt/tomcat/bin/shutdown.sh
                    sleep 15;
                    /opt/tomcat/bin/startup.sh
                    '
            }
        }
    }
}