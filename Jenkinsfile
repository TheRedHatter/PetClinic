pipeline {
    agent any
    stages {
    stage('Install Gitleaks') {
  steps {
    sh '''#!/bin/bash
        curl -LO https://github.com/zricethezav/gitleaks/releases/download/v7.6.0/gitleaks-linux-amd64 && chmod +x gitleaks-linux-amd64 && sudo mv gitleaks-linux-amd64 /usr/local/bin/gitleaks && gitleaks --version
    '''
  }
}
stage('Run Gitleaks') {
  steps {
    dir('https://github.com/Linish2020/PetClinic.git') {
      sh '''#!/bin/bash
          sudo gitleaks detect -f json -r https://github.com/Linish2020/PetClinic.git -v --report=/home/ubuntu/gitleaks/gitleaks_petclinic.json
          exit 0
         '''
        }
    }
  }
    }
}
