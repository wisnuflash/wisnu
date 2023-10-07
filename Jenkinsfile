pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                // Check out your source code from your repository
                // For example, using Git:
                git branch: 'your-branch', url: 'your-repo-url.git'
            }
        }
        
        stage('Deploy to Web Server') {
            steps {
                // Use the "Publish Over SSH" plugin to copy files to the server
                script {
                    def remote = [
                        name: 'Your SSH Server Name', // Give it a name
                        remote: '192.168.23.103',    // Server IP address
                        user: 'root',                // SSH username
                        password: 'wisnu',           // SSH password (consider using SSH keys)
                        sourceFiles: '**/*',         // Source files to upload
                        removePrefix: 'path/to/your/source/', // Optional: Remove this prefix from the source path
                        remoteDirectory: '/var/www/html/multibranch/' // Remote destination directory
                    ]
                    sshPublisher(publishers: [sshPublisherDesc(configName: remote)])
                }
            }
        }
    }
}
