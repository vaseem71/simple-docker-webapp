

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn -B -ntp clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn -B -ntp test'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts(
                    artifacts: 'target/*.jar,target/*.war',
                    allowEmptyArchive: false
                )
            }
        }
    }
