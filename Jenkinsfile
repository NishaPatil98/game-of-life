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
        
        sh "git clone https://github.com/NishaPatil98/game-of-life.git"
      }
    }
  }
}
