pipeline{
  agent any
  stages{
    stage("git repo"){
      steps{
        git url: "https://github.com/Ravina-Duggal/pythonBackend.git", branch: "main"
      }
    }
    stage("build"){
      steps{
        sh "docker build -t backend ."
      }
    }
    stage("validation"){
      steps{
        sh "docker stop backend-container || true"
        sh "docker rm backend-container || true"
      }
    }
     stage("run"){
      steps{
        sh "docker run -d --name backend-container -p 5173:5173 backend"
      }
    }
  }
}
