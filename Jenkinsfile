pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/PATRICIAJUNQUEIRA/Pandas-Dataset-Titanic.git'
            }
        }

        stage('Set up Environment') {
            steps {
                script {
                    // Instalando dependências
                    sh 'python -m pip install notebook nbconvert'
                    // Adicionar mais comandos para instalar outras dependências, se necessário
                }
            }
        }

        stage('Execute Notebook') {
            steps {
                script {
                    // Executar o notebook usando nbconvert
                    sh 'jupyter nbconvert --execute --to notebook --inplace path/to/your/notebook.ipynb'
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    // Comandos de limpeza, se necessário
                    echo 'Cleanup stage completed.'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed successfully.'
        }
    }
}