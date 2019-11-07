node {
  try {
    stage('checkout') {
      checkout scm
    }
    stage('simple'){
      steps{
        input message: 'Please input your name!!', ok: 'Confirm',
          parameters: [string(defaultValue: 'rick',
            description: 'This should not be your real name.', name: 'name', trim: true)]
      }
    }
    stage('compile') {
      echo "nothing to compile for hello.sh..."
    }
    stage('test') {
      sh "./test_hello.sh"
    }
    stage('package') {
      sh "tar -cvzf hello.tar.gz hello.sh"
    }
    stage('publish') {
      echo "uploading package..."
    }
  } finally {
    stage('cleanup') {
      echo "doing some cleanup..."
    }
  }
}
