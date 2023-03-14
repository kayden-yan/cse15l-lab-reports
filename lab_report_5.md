# CSE 15L Lab Report 5
___
## For lab 6, finish the grading script and take screenshots that demonstrate it working on several files.
___
## Here is My Grading Script (Windows Version Only) (You can change the CPATH to work on mac as well)

```
CPATH='.;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar'

## Clears out the folders
rm -rf student-submission
rm -rf test-field

## clone the student submission to /student-submission
git clone $1 student-submission
echo 'Finished cloning'

## check the correct file submitted
FILE=student-submission/ListExamples.java
if test -f "$FILE"; then
    echo "$FILE exists."
else
    echo "Missing $FILE."
    exit
fi

## Copy the necessary files into one folder
mkdir test-field
mkdir test-field/lib
cp lib/hamcrest-core-1.3.jar test-field/lib
cp lib/junit-4.13.2.jar test-field/lib
cp $FILE test-field
cp TestListExamples.java test-field

## Complie
cd test-field
javac -cp $CPATH *.java &> compile_result.txt
found=$(wc -w  compile_result.txt | cut -c1)
if [[ $found > 0 ]]; then
    echo "Compile Error!"
    exit
else
    echo "Compile Success!"
fi

## Run Test
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit_result.txt
if grep -q "OK" junit_result.txt; then
  echo "All tests passed!"
  echo "Score: 100 %"
else
    grep -o "Tests run: [0-9,]*," junit_result.txt > test_run.txt
    num_test=$(sed -e 's/.*run: \(.*\),.*/\1/' test_run.txt)
    failure_str=$(grep -o "Failures: [0-9,]*" junit_result.txt)
    num_fail=$(echo $failure_str | tr -dc '0-9')
    echo "Test_run: " $num_test
    echo "Failures: " $num_fail
    echo "Score: " $((($num_test - $num_fail) / $num_test * 100)) "%"
fi

## Clears out the folders
cd ..
rm -rf student-submission
rm -rf test-field
```

___
## Here are All the Test Cases Provided from Lab 6

![image1](https://user-images.githubusercontent.com/122576038/224884556-99056e75-e2ca-459b-a47e-8b93e94f8b71.png)

![image2](https://user-images.githubusercontent.com/122576038/224884588-4d397826-b748-4bba-a148-c2b7e3b29bfa.png)

![image3](https://user-images.githubusercontent.com/122576038/224884620-bae005f1-e3ac-432e-87ca-8dfd1f6c5cb1.png)

![image4](https://user-images.githubusercontent.com/122576038/224884638-dcca1476-9ef8-4692-be01-c6d9a229b119.png)

![image5](https://user-images.githubusercontent.com/122576038/224884656-be6a029c-a120-48a4-b637-aa6a7399fd63.png)

![image6](https://user-images.githubusercontent.com/122576038/224884677-5d27ba66-b6d6-4dcf-8abd-eb10f02feb77.png)

![image7](https://user-images.githubusercontent.com/122576038/224884697-33710467-2811-47be-969b-2f3c5f09ebdd.png)

