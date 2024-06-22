pipeline{
    agent{
        label{
            label "built-in"
            customWorkspace "/mnt/pipe"
        }
    }
    stages{
        stage("on-master"){
            steps{
            sh """
            rm -rf *
            sudo yum install tree -y
            """
            }
        }
        stage("on-slave1"){
            agent{
            label{
                label "slave-1"
                customWorkspace "/mnt/pipe"
            }
            }
            steps{
            sh """
            rm -rf *
            sudo yum install httpd -y
            """
            }
        }
        stage("on-slave2"){
            agent{
            label{
                label "slave-2"
                customWorkspace "/mnt/pipe"
            }
            }
            steps{
            sh """
            rm -rf *
            sudo yum install docker -y
            """
            }
        }
    }
}
