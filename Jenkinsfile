pipeline{
  agent{
    label{
      label "built-in"
      customWorkspace "/mnt/t1"
    }
  }
  stages{
    stage(clone){
      steps{
        sh "rm -rf /mnt/t1/*"
        sh "git clone https://github.com/NishaPatil98/game-of-life.git"
      }
    }
    stage("build"){
      steps{
        sh "yum install maven -y"
        dir("/mnt/t1/game-of-life/"){
        sh "mvn clean install -DskipTests"
        }
      }
    }
    stage("tomcat"){
      agent{
        label{
          label "dev"
          customWorkspace "/mnt/t1"
        }
        
      }
      steps{
        sh "rm -rf /mnt/t1/*"
        
        dir("/mnt/t1/"){
          sh "yum install git -y"
          sh "git init"
          sh "git remote add origin https://github.com/NishaPatil98/tomcat.git"
          sh "sudo git clone https://github.com/NishaPatil98/tomcat.git"
          sh "sudo yum install docker -y"
          sh "sudo systemctl start docker"
          sh "sudo docker build -t tomcat:1.0 . "
          sh "sudo docker run -itdp 8080:8080 tomcat:1.0 "
          
        }
        
      
      }
    }
  }
}
