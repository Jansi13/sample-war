pipeline {
  

  agent { label 'master' }
	  tools {
	  maven "M2_HOME"
	  jdk "Java_8"
			}
  
  stages {

   stage("cloning from the GIT") {
		steps {
		
		git credentialsId: '62fcb9a7-d903-475b-9f9c-5cac940cc8a8', url: 'https://github.com/Jansi13/sample-war.git'
		
		}


   }

   stage("build using maven")
   {
		steps {
		bat(/"%M2_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
			  }
		  		
   }

   stage("results")
   {
		steps {
		archiveArtifacts 'target/*.war'
		deploy adapters: [tomcat8(credentialsId: '9152681d-b7af-4d82-8d69-c2dfebec463c', path: '', url: 'http://localhost:8080/')], contextPath: null, war: 'samplewebapp.war'
			}
	   }

}
  } 
