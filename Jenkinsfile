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
       script{
           def date=new Date()
           def data="toda's date is"+date
        writeFile(file: 'zorg.txt', text: data)
        echo "this is unit testing"
       }
    }
}
stage("Read file"){
    steps{
       script{
       def readfile = readFile(file: 'zorg.txt')
       println(readfile)
       }
        
    }
   
    
}


stage("integration testing"){
    steps{
        archiveArtifacts 'zorg.txt'
        echo "this is integration testing"
    }
    post{
    always {
            echo 'always section'
            
        }
        success {
            build job:'Android_Project_AzureRepo'
            echo 'I succeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
}
    }

}



    }
