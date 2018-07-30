node{
  stage ('cloning the repository'){
	git 'https://github.com/endangeredspecies/SimpleIOT-Maven.git'
  }
  stage ('Build') {
	withMaven(jdk: 'jdk8', maven: 'maven_default') {
      bat 'mvn clean install'
    } 
  }
  stage ("running appscan on cloud"){
      appscan application: '18f3c3ca-a689-e811-ad5d-00259057d989', credentials: 'stage_asoc', name: 'test_scm_0730', scanner:static_analyzer('C:\\Users\\anurag-s\\.jenkins\\workspace\\test_pipeline_scm'), type: 'Static Analyzer'
  }
}
