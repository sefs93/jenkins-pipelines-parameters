library identifier: 'parameterLibrary@day-6', retriever: modernSCM(
  [$class: 'GitSCMSource',
   remote: 'https://github.com/sefs93/jenkins-parameters-shared-library.git'])

properties([
    parameters([
        example_params('COUNTRY'),
        example_params('ENVIRONMENT'),
        example_params('REGION'),
        example_params('SERVICE_NAME'),
        example_params('SERVICE_VERSION'),
        example_params('RELOAD_PARAMETERS'),
        example_params('TEST_NON_EXISTING')
    ])
])

reloadParameters()

mainPipeline(service: SERVICE_NAME, version: SERVICE_VERSION, country: COUNTRY, env: ENVIRONMENT, region: REGION)
