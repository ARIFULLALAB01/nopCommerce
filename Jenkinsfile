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
        stage('build') {
            steps {
                //sh 'dotnet publish -o published/ -c Release src/Presentation/Nop.Web/Nop.Web.csproj'
                dotnetPublish configuration: 'Release',
                   outputDirectory: 'published',
                   project: 'src/Presentation/Nop.Web/Nop.Web.csproj'

            }
            post {
                always {
                   echo 'I will always say Hello again!'
                }
            }
        }
       
    }
}