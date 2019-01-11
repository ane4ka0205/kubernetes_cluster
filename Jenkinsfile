pipeline {
    agent any
    parameters{
      string(defaultValue: "plan",  name: "action",  description: "Do you want plan/apply/destroy")
    }
        stages{
            stage("Pull repo"){
                steps{
                    git 'https://github.com/ane4ka0205/kubernetes_cluster.git'
                }
            }
            stage("terraform init"){
                steps{
                    sh 'cd /var/lib/jenkins/workspace/kubernetes_cluster'
                        sh 'terraform init'
                    }
                }
            stage("terraform plan"){
                steps{
                    sh 'cd /var/lib/jenkins/workspace/kubernetes_cluster'
                        sh "terraform ${action} -auto-approve"
                
            }
        }
    }
}
