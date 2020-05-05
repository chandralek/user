pipeline{
  agent {
    label 'SLAVE'
  }

  stages{
    stage('Install npm dependencies')
            {
              steps{
                sh '''
                npm install
            '''
              }
            }
    stage('Create archive to upload')
            {
              steps{
                sh '''
                tar -czf user-service.tgz node_modules package.json server.js
            '''
              }
            }
    stage('Upload to NEXUS')
            {
              steps{
                sh '''
                curl -v -u admin:admin123 --upload-file user-service.tgz https://nexus.devops46.online/repository/user-service/user-service.tgz
            '''
              }
            }
  }
}