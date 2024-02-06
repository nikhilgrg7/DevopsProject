node {
  stage("Clone the project") {
    git branch: 'master', url: 'https://github.com/nikhilgrg7/DevopsProject.git'
  }

  stage("Compilation") {
    sh "./mvnw clean install -DskipTests"
  }

  stage("Tests and Deployment") {
    stage("Runing unit tests") {
      sh "./mvnw test -Punit"
    }
    stage("Deployment") {
      sh 'start ./mvnw spring-boot:run -Dserver.port=8001'
    }
  }
}
