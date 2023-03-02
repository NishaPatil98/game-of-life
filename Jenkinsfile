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
          customeWorkspace /mnt/t1
        }
        
      }
      steps{
        dir("rm -rf /mnt/t1"){
          sh "git clone"
        }
        
      
      }
    }
  }
}
