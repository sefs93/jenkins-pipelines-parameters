library identifier: 'parameterLibrary@day-2', retriever: modernSCM(
  [$class: 'GitSCMSource',
   remote: 'https://github.com/sefs93/jenkins-parameters-shared-library.git'])

properties([
    parameters([
        choice(name: 'COUNTRY', choices: ['USA', 'AUS', 'MEX']),
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'uat']),
        choice(name: 'REGION', choices: ['us-east-1', 'sa-west-1', 'au-north-1']),
        string(name: 'SERVICE_NAME'),
        string(name: 'SERVICE_VERSION'),
        booleanParam(name: 'RELOAD_PARAMETERS', defaultValue: false)
    ])
])

reloadParameters()

mainPipeline(service: SERVICE_NAME, version: SERVICE_VERSION, country: COUNTRY, env: ENVIRONMENT, region: REGION)
