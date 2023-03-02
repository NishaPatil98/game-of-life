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
        sh "rm -rf *"
        sh "git clone https://github.com/NishaPatil98/game-of-life.git"
      }
    }
    stage("build"){
      steps{
        sh "mvn install"
      }
    }
  }
}
