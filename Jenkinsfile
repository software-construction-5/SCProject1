pipeline {
    
    agent any
  
    stages {
    
      stage("build") {
    
          steps {
            echo "building the application..."
          }
       } 
      
      stage("test") {
    
          steps {
            echo "testing the application..."
              sh './script.sh'
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
}
