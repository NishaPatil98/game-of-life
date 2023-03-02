pipeline{
  agent{
    label{
      label "built-in"
      customWorkspace "/mnt/t1"
    }
  }
  stages{
    /*stage(clone){
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
    }*/
    stage("tomcat"){
      agent{
        label{
          label "dev"
          customWorkspace "/mnt/t2"
        }
        
      }
      steps{
       sh "sudo rm -rf /mnt/t2/*"
        sh "chmod -R 777 /mnt/t2"
        sh "sudo yum install git -y"
        sh "sudo yum install docker -y"
        sh "sudo systemctl start docker"
        dir("/mnt/t2/"){
          sh "sudo git clone https://github.com/NishaPatil98/tomcat.git"
          sh "sudo docker build -t tomcat:1.0 . "
          sh "sudo docker run -itdp 8080:8080 tomcat:1.0 "
          
        }
        
      
      }
    }
  }
}
