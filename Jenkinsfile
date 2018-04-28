pipeline {
   agent any
   stages{
      stage ('Unit Tests') { 
            steps {
      
          /*Jenkins will initiate unit tests using ant and create a junit report.
            The shell command to run ant tests is ant -f test.xml -v
            The junit report source data is located in reports/result.xml*/
            
            sh 'ant -f test.xml -v'
            junit 'reports/result.xml'
           }
      }
      stage ('Build') {
            steps {
      
          /*Jenkins will compile the Java application using ant.
            The shell command to compile the application is ant -f build.xml -v*/
            
            sh 'ant -f build.xml -v'
           }
      }
      stage ('Deploy') {
            steps {
      
          /*- Jenkins will copy the build output jar file into an S3 bucket 
          (use an existing S3 bucket or create a new one for this assignment).
           -  The name of the output jar file will look something like rectangle-2.jar, 
           where the number represents the current Jenkins build number.
           -  You can use the AWS CLI to copy files from Jenkins to the S3 bucket. Don’t 
           worry about access credentials for this step because the Jenkins server has a 
           proper role attached which allows it to access the S3 bucket.*/
            
            sh  'cd /workspace/java-pipeline/dist/ .'
            sh 'pwd'
           }
      }
      
      }
}
