properties([
    parameters([
        choice(name: 'COUNTRY', choices: ['USA', 'AUS', 'MEX']),
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'uat']),
        choice(name: 'REGION', choices: ['us-east-1', 'sa-west-1', 'au-north-1']),
        string(name: 'SERVICE_NAME'),
        string(name: 'SERVICE_VERSION')
    ])
])

def environment_properties = [
    'USA': [
        'dev': [
            'us-east-1': [
                'project_id': 'some-dev-us-east-1-project',
                'creds': 'some-dev-us-east-1-creds'
            ]
        ],
        'qa': [
            'us-east-1': [
                'project_id': 'some-qa-us-east-1-project',
                'creds': 'some-qa-us-east-1-creds'
            ]
        ],
        'uat': [
            'us-east-1': [
                'project_id': 'some-uat-us-east-1-project',
                'creds': 'some-uat-us-east-1-creds'
            ]
        ]
    ],
    'AUS': [
        'dev': [
            'au-north-1': [
                'project_id': 'some-dev-au-north-1-project',
                'creds': 'some-dev-au-north-1-creds'
            ]
        ],
        'qa': [
            'au-north-1': [
                'project_id': 'some-qa-au-north-1-project',
                'creds': 'some-qa-au-north-1-creds'
            ]
        ],
    ],
    'MEX': [
        'uat': [
            'sa-west-1': [
                'project_id': 'some-uat-sa-west-1-project',
                'creds': 'some-uat-sa-west-1-creds'
            ]
        ],
    ]
]

node {
    stage ('Deploy') {
        println '=========================================================================================='
        println "[INFO] Deploying service:\t${SERVICE_NAME}:${SERVICE_VERSION}"
        println "[INFO] Country:\t\t\t${COUNTRY}"
        println "[INFO] Environment:\t\t${ENVIRONMENT}"
        println "[INFO] Region:\t\t\t${REGION}"
        println "[INFO] Credentials:\t\t${environment_properties[COUNTRY][ENVIRONMENT][REGION]['creds']}"
        println "[INFO] Project ID:\t\t${environment_properties[COUNTRY][ENVIRONMENT][REGION]['project_id']}"
        println '=========================================================================================='
    }
}
