@Library('jenkinslib') _     

def mytools = new org.devops.tools()



String workspace = "/opt/jenkins"

pipeline{
    //指定运行此流水线的节点
     agent any
     tools {
         maven 'maven'
     }
     
    parameters {
        // string(name:'multi_project_names', defaultValue: 'sinhic-common-pom,sinhic-common-lib', description: '多个项目之间用逗号隔开')
        string(name:'mddd', defaultValue: 'staging', description: '项目groupId')
      
    }
    
    

    //流水线的阶段
    stages{
        
       
        
        stage("example"){
             when { environment name: 'test', value: 'abcd' }
            steps{
                sh 'mvn --version'
               // input submitter: 'admin', id: 'Test', message: '我们是否要继续', ok: '是，继续', parameters: [choice(choices: ['a', 'b'], description: '', name: 'test1')]
            }
        }
        //阶段1 获取代码
        stage("CheckOut"){
            steps{
                script{
                    println("获取代码")
                    println("*****"+"${test}")
                    
                    mytools.PrintMes("this is lib!")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    println("运行构建")
                }
            }
        }
    }
    post {
        always{
            script{
                println("流水线结束后，经常做的事情")
            }
        }
        
        success{
            script{
                println("流水线成功后，要做的事情")
            }
        
        }
        failure{
            script{
                println("流水线失败后，要做的事情")
            }
        }
        
        aborted{
            script{
                println("流水线取消后，要做的事情")
            }
        
        }
    }
}
