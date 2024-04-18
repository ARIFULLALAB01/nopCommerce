pipeline {
    agent {
        label 'nop'
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages { 
        stage('scm') {
            steps {
                git url: 'https://github.com/ARIFULLALAB01/nopCommerce.git',
                   branch: 'develop'
            }

        }
    }
    stages { 
        stage('build') {
            steps {
                sh 'dotnet publish -o published/ -c Release src/Presentation/Nop.Web/Nop.Web.csproj'
            }

        }
    }
        
}