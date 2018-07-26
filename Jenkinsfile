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
      appscan application: '4a66c9fa-5375-e811-871a-002590731623', credentials: 'stage_asoc', failureConditions: [failure_condition(failureType: 'total', threshold: 3)], name: 'test_2607', scanner: static_analyzer('E:\\work\\SimpleIOT-Maven\\SimpleIOT-Maven'), type: 'Static Analyzer'
  }
}
