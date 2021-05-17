 pipeline{
       agent { label 'master'} 
       stages {
          stage ("build") {
            steps {
                script {
          docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
          sh "pwd"
          def customImage = docker.build("rrqs12-appointy/${env.GIT_BRANCH}-${env.BUILD_NUMBER}", "-f Dockerfile .")
          /* Push the container to the custom Registry */
          customImage.push("${env.BUILD_NUMBER}")
         }
        }
        }
          }
       }
