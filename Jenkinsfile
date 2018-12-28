node {
    checkout scm
stage('Compile_and_package')
{
bat 'mvn clean package -DskipTests'
}
stage('Unit_Test')
{
bat 'mvn surefire:test'
step([$class: 'Publisher'])
}
stage('Code_analysis')
{
withSonarQubeEnv {
bat 'mvn sonar:sonar'
}
}
}