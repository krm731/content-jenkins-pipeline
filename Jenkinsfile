pipeline {
 agent any
   stages {
     stage('build') {
       steps {
 	sh 'javac -d . src/*.java'
 	sh 'echo Main-Class: Rectangulator > MANIFEST.MF'
	sh 'jar -cvmf MANIFEST.MF rectangle.jar *.class'
        sh 'echo Thanks'
 	}
      }
     stage('run') {
	steps {
        sh 'java -jar rectangle.jar 12 17'
        }
     }
   }
  post {
    success {
     achiveArtifacts artifacts: 'rectangle.jar', fingerprint: true
		}
	}
}
