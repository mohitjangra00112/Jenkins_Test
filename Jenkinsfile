pipeline {
    agent any

    parameters {
        string(
            name: 'PR_NUMBER',
            defaultValue: '1',
            description: 'Enter Pull Request Number'
        )
    }

    stages {
        stage('Show PR Number') {
            steps {
                echo "Building PR #${params.PR_NUMBER}"
            }
        }

        stage('Checkout PR') {
            steps {
                git branch: "refs/pull/${params.PR_NUMBER}/head",
                    url: 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}