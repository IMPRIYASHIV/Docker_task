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
                        image 'myfirstimage:tag' // Replace with your Docker image and tag
                        args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket for Docker inside Docker
                }
            }
            steps
            {
                // Checkout your source code repository
                git 'https://github.com/bhargavi1101gm/jenkins.git'  // Replace with your Git repository URL
                // Build using Dockerfile
                script 
                {
                    docker.build('myfirstimage:tag', '-f /Dockerfile .') // Replace image name, tag, and Dockerfile path
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
                        docker.image('myfirstimage:tag').inside 
                        {
                            sh 'docker run -it myfirstimage' // Replace with your test commands
                        }
                   }
              }
        }
    }
}
