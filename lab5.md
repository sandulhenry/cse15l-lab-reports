# Lab Report 5 - Putting it All Together (Week 9)
## CSE15L WI24 - Sandul Henry
___
## Part 1 - Debugging Scenario

### Step 1:
![image](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/86771d19-4471-40c9-94ef-3ce83e27ae4a)

### Step 2:
*The TA says:* "Hi! You could be right. Could you post your bash autograder script and double check its behavior? make sure you follow the logical progression of events. In short, we want to make sure your bash script follows your intended behavior

### Step 3:
*The Student says:* Hi! OMG! You were right I made a mistake in my bash script! I forgot to remove the directory grading-area/ in the script. Here is the before and after of the relvant part of the script:

![before](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/ed49cc8e-6ba8-408b-a3c9-033305a0587f)
![after](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/38d97f43-8ded-48b7-9836-4be250dbb903)

*The Student:* and here is the behavior after we make the change:

![image](https://github.com/sandulhenry/cse15l-lab-reports/assets/154122103/4a2cea43-5d7e-486a-aab9-a77760abf8bf)

### Step 4:

* The directory structure:
```
├── grader-review-sandulhenry
│   ├── grading-area
│   │   ├── 
│   ├── lib
│   │   ├── hamcrest-core-1.3.jar
│   │   ├── junit-4.13.2.jar
│   ├── student-submission
│   │   ├── 
│   ├── GradeServer.java
│   ├── Server.java
│   ├── TestListExamples.java
│   ├── grade.sh
```

* The content of the relevant file is `grade.sh` BEFORE the changes:

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'
rm -rf student-submission
mkdir grading-area
git clone $1 student-submission
echo 'Finished cloning'

if [ -f "student-submission/ListExamples.java" ]; then
    echo "File found!"
else
    echo "ListExamples.java not found!"
    exit 1
fi

cp -r lib grading-area

cp student-submission/ListExamples.java grading-area/

cp TestListExamples.java grading-area/

cd grading-area
javac -cp $CPATH *.java
if [ $? -ne 0 ]; then
    echo "Compile Error!"
    exit 1
else
    echo "Compiled Successfully"
fi

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > output.txt
if [ $? == 0 ]; then
    echo "Perfect Pass"
    echo "Score: 100%"
    exit 0
else
    lastline=$(cat output.txt | tail -n 2 | head -n 1)
    tests=$(echo $lastline | awk -F'[, ]' '{print $3}')
    failures=$(echo $lastline | awk -F'[, ]' '{print $6}')
    successes=$(($tests -$failures))
    echo ""
    echo "Tests ran: $tests"
    echo "Tests failed: $failures"
    echo "Score is $(expr $successes / $tests)"
fi
```

* The content of the relvant file `grade.sh` AFTER:

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'
rm -rf student-submission
rm -rf grading-area
mkdir grading-area
git clone $1 student-submission
echo 'Finished cloning'

if [ -f "student-submission/ListExamples.java" ]; then
    echo "File found!"
else
    echo "ListExamples.java not found!"
    exit 1
fi

cp -r lib grading-area

cp student-submission/ListExamples.java grading-area/

cp TestListExamples.java grading-area/

cd grading-area
javac -cp $CPATH *.java
if [ $? -ne 0 ]; then
    echo "Compile Error!"
    exit 1
else
    echo "Compiled Successfully"
fi

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > output.txt
if [ $? == 0 ]; then
    echo "Perfect Pass"
    echo "Score: 100%"
    exit 0
else
    lastline=$(cat output.txt | tail -n 2 | head -n 1)
    tests=$(echo $lastline | awk -F'[, ]' '{print $3}')
    failures=$(echo $lastline | awk -F'[, ]' '{print $6}')
    successes=$(($tests -$failures))
    echo ""
    echo "Tests ran: $tests"
    echo "Tests failed: $failures"
    echo "Score is $(expr $successes / $tests)"
fi
```

* The lines we ran that demonstrated the bug:
`bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3`
and then
`bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`

* We changed the script so that `grading-area/` is removed so we don't see the unexpected behavior, and it is cleared for a good reset. That way we don't get the message that grading area already exists. 

## Part 2 - Reflection: 

* I liked learning about bash scripting, like in the week 6 lab. I didn't know bash scripts could have that much functinality. It was cool to think about how our own programming assignments are graded.


*Sources used: the script described in https://ucsd-cse15l-w24.github.io/week6/index.html*



