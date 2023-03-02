pipeline{
  agent{
    label{
      label "built-in"
    }
  }
  stages{
    stage(clone){
      steps{
        sh rm -rf *
        sh yum install git -u
        git clone "https://github.com/NishaPatil98/game-of-life.git"
      }
    }
  }
}
