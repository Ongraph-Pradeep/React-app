pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
          stage("Create-react-app") {
               steps {
                    sh "npm install -g create-react-app"
                    sh "create-react-app jenkins-react-app"
                    sh "cd jenkins-react-app"
                    sh "npm start"
               }
          }
    }
}
