pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                echo 'check'
                // Check out your source code from your repository
                // For example, using Git:
                // git branch: 'your-branch', url: 'your-repo-url.git'
            }
        }
        
        stage('Deploy to Web Server') {
            steps {
                // Use the "Publish Over SSH" plugin to copy files to the server
               sshPublisher(publishers: [sshPublisherDesc(configName: 'production-server', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQBBhbJGlh2a+PA60TsVI5ly4ecssXy08NjXpEhukuIC0=}', key: '', keyPath: '', username: 'root'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
