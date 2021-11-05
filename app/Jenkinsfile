node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'docker_hub_cred') {

        def customImage = docker.build("glitch2k46/containerize_app")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}