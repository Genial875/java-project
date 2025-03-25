pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven_3_8_7"
    }

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
}