node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/bumsol2/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("solbeom/web_count:v2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access2", url: "" ]) {
        dockerImage.push()
        }
    }
}
