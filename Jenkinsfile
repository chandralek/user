pipeline{
  agent {
    label SLAVE
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
  }
}