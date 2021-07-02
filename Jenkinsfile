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
    stage("Testing"){
parellel{
stage("Unit testing"){
    steps{
        echo "this is unit testing"
    }
}
stage("integration testing"){
    steps{
        echo "this is integration testing"
    }
}
}
    }

}



    }
}


    }
        
}
