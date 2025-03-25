pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven_3_8_7"
    }

    // stages {
        // stage('CompileandRunSonarAnalysis') {
            // steps {
            //     // Sonar credentials on jenkins
            //     withCredentials([string(credentialId:'sonar_token',variable:'sonar_token')])

            //     // 
            //     sh "mvn clean verify sonar:sonar -Dsonar.login=$tech563token -Dsonar.organization=tech563 -Dsonar.host.url=https://sonarcloud.io -Dsonar.projectkey=tech563"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            // }

//             post {
//                 // If Maven was able to run the tests, even if some of the test
//                 // failed, record the test results and archive the jar file.
//                 success {
//                     junit '**/target/surefire-reports/TEST-*.xml'
//                     archiveArtifacts 'target/*.jar'
        //         }
        //     }
        // }



        stage('BuildDockerImage') {
            steps {
                // add comment here
                withDockerRegistry([credentialId: "dockerlogin", url:])
                    script{
                        app = docker.build("tech365app")


                    }
            }
        }

        stage('PushDockerImage') {
            steps {
                //  add comment here
            script{


                docker.withRegistry('https://393937407747.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:aws-credentials')
                    app.push("lastest")



            }

            }

        }
