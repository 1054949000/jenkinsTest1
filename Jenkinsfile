node {
    properties([disableConcurrentBuilds()])
    def app
    def rev_no = ""
    def build_arg = ""
    def registry_address = "https://registry.hub.docker.com"

    stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }

    stage("Pull GIT Repo") {
        checkout scm
        echo "pull repo"
        // dir('webrtc') {
        //     git branch: 'main',
        //         credentialsId: 'my_jenkins_private',
        //         url: 'git@github.com:sidgeek/webRTC.git';
        //     // ARES-1285 Create a version file in jenkins pipeline
        //     rev_no = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
        // }
    }

    stage("Build and start test image") {
        echo "Build"
        // build_arg += "-f ./Dockerfile --build-arg REV_NO=${rev_no} ."
        // app = docker.build "sidshi/testdemo", build_arg;
    }

    stage("push docker image to dockhub") {
        echo "push"
        // docker.withRegistry(registry_address, "docker-registry") {
        //     app.push()
        //     pushNginxImageSuccess = true
        // }
    }
    stage('deploy image on machinice') {
        echo "deploy"
        // sh 'docker stop mydemo || docker rm -f mydemo || true'
        // sh 'docker run -p 443:443 -p 80:80 -d --rm --name mydemo sidshi/testdemo'
    }
}
