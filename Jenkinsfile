pipeline {
        agent any
            stages {
                stage('Clone Repository') {
                /* Cloning the repository to our workspace */
                steps {
                checkout scm
                        git branch: 'main', url: 'https://github.com/kuruvasubhashini/salary_pred_docker.git'
                }
           }
           stage('Build Image') {
                   steps { 
                           sh 'chmod +x gui_salary.py'
                sh 'docker build -t salarypredapp:v2 .'
                }
           }
           stage('Run Image') {
                steps {
                sh 'docker run -d -p 8000:8000 --name salarydemo salarypredapp:v2'
                }
           }
           stage('Testing'){
                steps {
                    echo 'Process Complete..'

                    }
           }
    }
}
