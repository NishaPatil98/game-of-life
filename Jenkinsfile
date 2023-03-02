pipeline{
  agent{
    label{
      label "built-in"
      customWorkspace "/mnt/test"
    }
  }
  stages{
    stage(clone){
      steps{
        sh rm -rf *
         dir("/mnt/test")
        sh yum install git -y
        git clone "https://github.com/NishaPatil98/game-of-life.git"
      }
    }
  }
}
