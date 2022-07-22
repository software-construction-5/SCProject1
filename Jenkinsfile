pipeline {
    
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}
  
    stages {
    
      stage("build") {
    
          steps {
            echo "building the application..."
              sh "docker build -t anthonygfrn/software-construction-group5:latest ."
          }
       } 
        
       stage("login") {
    
          steps {
              sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USER --password-stdin"
          }
       } 
      
      stage("test") {
    
          steps {
            echo "testing the application..."
          }
       } 
      
       stage("push") {
    
          steps {
              sh 'docker push anthonygfrn/software-construction-group5:latest'
          }
       } 
        
      stage("deploy") {
    
          steps {
            echo "deploying the application..."
          }   
      }    
        
      stage("update-issue") {
    
          steps {
            jiraComment body: 'Integrated wih Jira, Update Issue G5-2', issueKey: 'G5-2'
          }
       } 
    }
    post {
        always {
            sh 'docker logout'
        }
    }
}
