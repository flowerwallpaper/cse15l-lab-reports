# Create your grading script here


      rm -rf student-submission
      git clone $1 student-submission


      cd student-submission

      if [ -f "ListExamples.java" ]
      then 
          echo "File submitted!"
      else 
          echo "ListExamples.java not submitted" 
      fi

      cp ListExamples.java ..



      cd ..

      javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

      if [ $? -ne 0 ]
      then
          echo "Compiler Error"
          exit
      fi

      java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples

      cat TestListExamples
      
   <img width="734" alt="image" src="https://user-images.githubusercontent.com/103080777/204367718-6e2c0bde-083c-48d5-8c0e-ab76c625abc1.png">

<img width="825" alt="image" src="https://user-images.githubusercontent.com/103080777/204367914-bb4c6ea0-7da8-4844-8065-5d98236874ef.png">

<img width="898" alt="image" src="https://user-images.githubusercontent.com/103080777/204368028-358d8b8f-0559-4395-b261-aab565c551e8.png">


For List-methods-compiler-error:

      rm -rf student-submission
      git clone $1 student-submission


      cd student-submission

      if [ -f "ListExamples.java" ] //true--there is a ListExamples.java
      then 
          echo "File submitted!" //echoes "File submitted"
      else 
          echo "ListExamples.java not submitted" 
      fi

      cp ListExamples.java ..



      cd ..

      javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

      if [ $? -ne 0 ] //since there's a compiler error, this doesn't return 0, and instead we get a compiler error message
      then
          echo "Compiler Error"
          exit
      fi

      java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples

      cat TestListExamples




