pipeline {
    agent any
    
        stages {
           stage('----build code---'){
                steps {
                    sh "mvn clean install package"
                }
            }
            stage('----deploy to tomcat---'){
                steps {
                    sshagent(['jenkins_key']) {
                        scp "webapp/target/webapp.war ec2-user@54.79.165.40:/opt/apache-tomcat-10.0.14/webapps"
                        } 
                }
            }
        }
    }
