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
        bat "\"${tool 'MSBuild-default'}\" C:\\TesteProjeto\\TesteWeb\\TesteWeb.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER} /p:PrecompileBeforePublish=true"
      }
    }
    stage('Arquive') {
      steps {
        archive 'ProjetoExemplo/bin/Release/**'
      }
    }
  }
}
