pipeline {
  agent any

  stages {

    stage('Build') {
      steps {
        sh 'dotnet build eShopOnWeb.sln'
      }
    }

    stage('Unit Tests') {
      steps {
        sh 'dotnet test tests/UnitTests --no-build'
      }
    }

    stage('Integration Tests') {
      steps {
        sh 'dotnet test tests/IntegrationTests --no-build'
      }
    }

    stage('Functional Tests') {
      steps {
        sh 'dotnet test tests/FunctionalTests --no-build'
      }
    }

    stage('Deployment') {
      steps {
        sh 'dotnet publish eShopOnWeb.sln -o /var/aspnet'
      }
    }

  }
}
