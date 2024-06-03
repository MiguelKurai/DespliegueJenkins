pipeline {
    agent any

    stages {
        stage('Update Apache2 Configuration') {
            steps {
                script {
                    // Copiar el archivo actualizado index.html al directorio raíz de Apache2
                    sh 'sudo cp /var/jenkins_home/workspace/Primer\ Pipeline/index.html /var/www/html/'

                    // Reiniciar apache2 para aplicar los cambios
                    sh 'sudo /etc/init.d/apache2 restart'
                }
            }
        }
    }

    post {
        success {
            echo 'Configuración de apache2 actualizada exitosamente!'
        }
        failure {
            echo 'Error al actualizar la configuración de apache2.'
        }
    }
}
