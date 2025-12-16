pipeline {
<<<<<<< HEAD
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

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
=======
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
>>>>>>> e80db2cddb4f75c9c3836ce1993441090a1a9524

        stage('Functional Tests') {
            steps {
                sh 'dotnet test tests/FunctionalTests --no-build'
            }
        }

        stage('Publish Web App') {
            steps {
                sh '''
                  dotnet publish src/Web/Web.csproj \
                    -c Release \
                    -o /var/aspnet/web
                '''
            }
        }
    }
}
