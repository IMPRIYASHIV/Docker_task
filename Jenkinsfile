pipeline
{
    agent any
    stages
    {
        stage("Clone")
        {   
            steps
            {
                sh ' rm -rf /var/lib/jenkins/* '
                sh ' git clone https://github.com/IMPRIYASHIV/Docker_task.git '
            }
        }
        stage("Build")
        {
            steps
            {
                sh ' docker build -t app /var/lib/jenkins/Docker_task  '
            }
        }
        stage("Run")
        {
            steps
            {
                sh ' docker run -it -d app '
            }
        }
    }
}
