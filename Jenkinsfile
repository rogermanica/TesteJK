pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        bat("\"${WORKSPACE}\\tools\\nuget\\nuget.exe\" restore ${WORKSPACE}\\TesteProjeto\\ProjetoExemplo\\ProjetoExemplo.sln)
        bat "\"${tool 'MSBuild'}\" ProjetoExemplo.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
      }
    }
    stage('Arquive') {
      steps {
        archive 'ProjetoExemplo/bin/Release/**'
      }
    }
  }
}
