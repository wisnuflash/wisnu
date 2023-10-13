pipeline {
    agent any
triggers {
                  upstream 'dev, '
            }
    stages {
        stage('Sendcode Dev server') {
            steps {
                echo 'check'
                sshPublisher(publishers: [sshPublisherDesc(configName: 'dev-ssh', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQKLp/lZ/y2VaMXfX9YHs2wD3CbvL5m4gUFwf/pktAMvM=}', key: '', keyPath: '', username: 'git'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'wisnu', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        
        stage('Test Web'){
            when {
                beforeInput true
                branch 'main'
            }
            input {
                message "Apakah tidak ada bug atau error ?"
                id "simple-input"
            }
            steps{
                echo 'amannn'
            }
        }
        stage('Deploy to Web Server') {
             when {
                beforeInput true
                branch 'main'
            }
            input {
                message "Deploy to production?"
                id "simple-input"
            }
            steps {
                
                // Use the "Publish Over SSH" plugin to copy files to the server
               sshPublisher(publishers: [sshPublisherDesc(configName: 'production-server', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQBBhbJGlh2a+PA60TsVI5ly4ecssXy08NjXpEhukuIC0=}', key: '', keyPath: '', username: 'root'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'wisnu', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
