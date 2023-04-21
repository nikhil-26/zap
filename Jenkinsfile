def ret
pipeline{
    agent any
    stages{
        stage('Run DAST'){
            steps{
                script{
                     ret = sh(script:"""
                     pwd
                     ls 
                     //docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable zap-baseline.py -t http:// -g newfull.conf -r testreport.html 
                     
                     //web  fail_on:"medium" --timeout=10000 --log-level=info --verbose \
                     //--config=/tmp/flexUAT_scan.yaml 
                     //--fail-on medium \
                     //--output /tmp/output \
                    
    
                     sh "echo \"exit code is : ${ret}\""
                    // if(ret !=0){
                         //currentBuild.result = 'ERROR'
                    //     error("DAST Severity policy failed...")
                        //return
                     }
                     
                }
            }
        }
    }
    
    post{
        always{
            archiveArtifacts artifacts: 'output/'
        }
    }
}
