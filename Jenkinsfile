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
        rm -rf *
          dir("/mnt/test")
        sh yum install git -u
        git clone "https://github.com/NishaPatil98/game-of-life.git"
      }
    }
  }
}
