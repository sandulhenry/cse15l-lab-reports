# Lab Report 5 - Putting it All Together (Week 9)
## CSE15L WI24 - Sandul Henry
___
## Part 1 - Debugging Scenario

### Step 1:
![image](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/86771d19-4471-40c9-94ef-3ce83e27ae4a)

### Step 2:
*The TA says:* "Hi! You could be right. Could you post your bash autograder script and double check its behavior? make sure you follow the logical progression of events. 

### Step 3:
*The Student says:* Hi! OMG! You were right I made a mistake in my bash script! I forgot to remove the directory grading-area/ in the script. Here is the before and after:

![before](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/ed49cc8e-6ba8-408b-a3c9-033305a0587f)
![after](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/38d97f43-8ded-48b7-9836-4be250dbb903)

*The Student:* and here is the behabior after we make the change:

![behavior](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/f376285b-8bb3-4077-8d78-d99f608699c3)

### Step 4:

* The directory structure:
```
├── grader-review-sandulhenry
│   ├── grading-area
│   │   ├── IsMoon.class
│   │   ├── ListExamples.java
│   │   ├── TestListExamples.class
│   │   ├── lib
|   │   │   ├── hamcrest-core-1.3.jar
|   │   │   ├── junit-4.13.2.jar
│   │   ├── ListExamples.class
│   │   ├── StringChecker.class
│   │   ├── TestListExamples.java
│   │   ├── output.txt
│   ├── lib
│   │   ├── hamcrest-core-1.3.jar
│   │   ├── junit-4.13.2.jar
│   ├── student-submission
│   │   ├── ListExamples.java
│   ├── GradeServer.java
│   ├── Server.java
│   ├── TestListExamples.java
│   ├── grade.sh
```






