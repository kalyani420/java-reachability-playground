node{
def mvnHome
stage('SetEnv') {
git 'https://github.com/kalyani420/java-reachability-playground.git'
mvnHome = tool 'MAVEN_HOME'
}

stage('CompileandPackage') {
withEnv(["MVN_HOME=$mvnHome"]) {
bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
}
}
stage('Snyk'){
snykSecurity failOnIssues: true, organisation: '10f085ff-6dfa-4802-906b-22f4e6e3fde4', snykInstallation: 'SnykSec', snykTokenId: 'SnykAPI_KP'

}
}
