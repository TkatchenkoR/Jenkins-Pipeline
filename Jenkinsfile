pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building ..."
            }
            post{
                always{
                    mail to: "Robert.Tkatchenko@gmail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }
    }
}
