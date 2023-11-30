pipeline
{
    agent any
    stages
    {
        stage("Clone")
        {   
            steps
            {
                sh ' sudo rm -rf /var/lib/jenkins/* '
                sh ' sudo git clone https://github.com/IMPRIYASHIV/Docker_task.git '
            }
        }
        stage("Build")
        {
            steps
            {
                sh ' sudo docker build -t app /var/lib/jenkins/Docker_task  '
            }
        }
        stage("Run")
        {
            steps
            {
                sh ' sudo docker run -it -d app '
            }
        }
    }
}
