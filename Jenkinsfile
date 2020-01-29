node {

    stage('Checkout') {

        // Checkout files.
        checkout([
            $class: 'GitSCM',
            branches: [[name: 'jenkins-integration']],
            doGenerateSubmoduleConfigurations: false,
            extensions: [], submoduleCfg: [],
            userRemoteConfigs: [[
                name: 'github',
                url: 'https://github.com/NivethaSri/CITestApp.git'
            ]]
        ])

        // Build and Test
        sh 'xcodebuild -scheme "CITestProject" -configuration "Debug" build test -destination "platform=iOS Simulator,name=iPhone 6,OS=10.1" -enableCodeCoverage YES '

        // Publish test restults.
    }

     
}
