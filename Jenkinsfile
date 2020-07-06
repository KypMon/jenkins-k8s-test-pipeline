// def pod_label = "nodejs-${UUID.randomUUID().toString()}"

pipeline {
  agent {
    kubernetes {
      label 'itm-test'
      defaultContainer 'node'
      yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    mainapp: node
spec:
  containers:
  - name: node
    image: node:latest
    command:
    - cat
    tty: true
"""
    }
  }


  // Main part - stages
  stages {
    stage('Install Dependencies') {
			steps {
        sh 'npm install'
			}
		}
  }
}

