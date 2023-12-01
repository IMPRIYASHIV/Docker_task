pipeline
{
    agent any
    
    stages
    {
        stage('Build')
        {   
            agent
            {
                 docker 
                {
                    // Use Docker with a specific image
                        image 'imageone:v1' // Replace with your Docker image and tag
                        args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket for Docker inside Docker
                }
            }
            steps
            {
                // Checkout your source code repository
                git 'https://github.com/IMPRIYASHIV/Docker_task.git'  // Replace with your Git repository URL
                // Build using Dockerfile
                script 
                {
                    docker.build('imageone:v1', '-f /Dockerfile .') // Replace image name, tag, and Dockerfile path
                }
            }
        }
       stage('Test') 
        {
            steps 
               {
                // Run tests or any other tasks within the Docker container
                script 
                   {
                        docker.image('imageone:v1').inside 
                        {
                            sh 'docker run -it imageone' // Replace with your test commands
                        }
                   }
              }
        }
    }
}
