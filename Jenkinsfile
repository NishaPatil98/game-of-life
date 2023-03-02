pipeline{
  agent{
    label{
      label "built-in"
    }
  }
  stages{
    stage(clone){
      steps{
        rm -rf *
        git clone https://github.com/NishaPatil98/game-of-life.git
      }
    }
  }
}
