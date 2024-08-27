pipeline{
      agent any
           triggers {
                     pollSCM '* * * * *'
                     }
    
            stages{
                  stage(checkout){
                        steps{
                            checkout scm
                              }
                        }
               stage(build){
                     steps{
                       sh 'mvn install'
                        }
                       }
                  stage(Deployment){
                        steps{
                              sh 'cp target/job1.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
                        }
                  }
    }
}

