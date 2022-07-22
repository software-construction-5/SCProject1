pipeline {
    
    agent any
  
    stages {
    
      stage("build") {
    
          steps {
            echo "building the application..."
            yarn build
          }
       } 
      
      stage("test") {
    
          steps {
            echo "testing the application..."
              cd /Users/anthony/Downloads/apache-jmeter-5.5/bin
              sh jmeter.sh -Jjmeter.save.saveservice.output_format=xml -n -t /Users/anthony/Downloads/apache-jmeter-5.5/bin/JmeterJenkinsIntegrationTest.jmx -l /Users/anthony/Downloads/TestResult1.jtl
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
