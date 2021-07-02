pipeline{
    agent any
    stages {
stage("first stage"){
    steps{
        echo "This is first stage"
    }
}
    stage("second  stage"){
    steps{
        echo "This is second stage"
    }
    }
     stage("third  stage"){
         
    steps{
        input("proced for deployment")
        echo "This is second stage"
    }
     }
    stage("Testing"){
parallel {
stage("Unit testing"){
    steps{
        writeFile(file: 'zorg.txt', text: "this is automated file")
        echo "this is unit testing"
    }
}
stage("integration testing"){
    steps{
        archiveArtifacts 'zorg.txt'
        echo "this is integration testing"
    }
}
}
    }

}



    }
