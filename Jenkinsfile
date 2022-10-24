node {
    stage('Clone code') {
        git 'https://github.com/ali1a11/Selenium_Grid_Demo_Project.git'
    }

    stage('Run tests'){
        if(isUnix()){
            sh "mvn clean test"
        } else {
            bat "mvn clean test -Dcucumber.filter.tags=\"@regression\" "
        }

    }

    stage('Generate report'){
           cucumber failedFeaturesNumber: -1,
            failedScenariosNumber: -1,
            failedStepsNumber: -1,
            fileIncludePattern: '**/*.json',
            pendingStepsNumber: -1,
            skippedStepsNumber: -1,
            sortingMethod: 'ALPHABETICAL',
            undefinedStepsNumber: -1
    }
}