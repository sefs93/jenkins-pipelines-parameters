library identifier: 'parameterLibrary@day-4', retriever: modernSCM(
  [$class: 'GitSCMSource',
   remote: 'https://github.com/sefs93/jenkins-parameters-shared-library.git'])

properties([
    parameters([
        params_COUNTRY(),
        params_ENVIRONMENT(),
        params_REGION(),
        params_SERVICE_NAME(),
        params_SERVICE_VERSION(),
        params_RELOAD_PARAMETERS()
    ])
])

reloadParameters()

mainPipeline(service: SERVICE_NAME, version: SERVICE_VERSION, country: COUNTRY, env: ENVIRONMENT, region: REGION)