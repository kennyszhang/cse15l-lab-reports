## grade.sh code block
```
err() {
    echo $1
    exit 1
}

CP=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

test ! -z "$1" \
|| err "no github repo submitted"

rm -rf student-submission
git clone $1 student-submission

echo "github repo cloned sucessfully"

test -e "student-submission/ListExamples.java" \
|| err "ListExamples.java not found"

cp TestListExamples.java student-submission/
cd student-submission/

echo "cd student-submission"

if [[ ! -f "ListExamples.java" ]]
then 
    echo "file name does not match"
    exit 1
fi

echo "file name matches"

echo "num of filter methods detected: "
grep -c "static List<String> filter" ListExamples.java > temp.txt
while read line; do echo $line; done < temp.txt

echo "num of merge methods detected: "
grep -c "static List<String> merge" ListExamples.java > temp.txt
while read line; do echo $line; done < temp.txt

javac -cp $CP *.java \
|| err "file failed to compile"
echo "complied file"

java -cp $CP org.junit.runner.JUnitCore TestListExamples 2> output.txt
echo "report saved to student-submission/output.txt"
``` 

## output of https://github.com/ucsd-cse15l-f22/list-methods-lab3
<img width="360" alt="Screenshot 2022-11-28 at 11 40 00 AM" src="https://user-images.githubusercontent.com/68624067/204366085-ba236e34-5501-4433-8c9e-b63d41d41449.png">

## output of https://github.com/ucsd-cse15l-f22/list-methods-corrected
<img width="355" alt="Screenshot 2022-11-28 at 11 40 55 AM" src="https://user-images.githubusercontent.com/68624067/204366236-6733558f-f6ff-47d6-a5aa-69621fcb6510.png">

## output of https://github.com/ucsd-cse15l-f22/list-methods-compile-error
<img width="329" alt="Screenshot 2022-11-28 at 11 41 40 AM" src="https://user-images.githubusercontent.com/68624067/204366379-fd862c61-eb50-478c-afd5-f64ce62813ae.png">

# trace of https://github.com/ucsd-cse15l-f22/list-methods-compile-error
<img width="244" alt="Screenshot 2022-11-28 at 11 42 41 AM" src="https://user-images.githubusercontent.com/68624067/204366531-dea07c58-565e-44d4-8198-e0980fe90802.png">

```
return code is 0 because we have provided a github repo link
```

<img width="356" alt="Screenshot 2022-11-28 at 11 43 53 AM" src="https://user-images.githubusercontent.com/68624067/204366749-d7508970-27d7-496f-8c73-56e51486e38d.png">

```
return code is 0 because the file ListExamples.java is found
```

<img width="262" alt="Screenshot 2022-11-28 at 11 44 47 AM" src="https://user-images.githubusercontent.com/68624067/204366868-5ed065fe-e729-4923-8bbd-c1bfe704664a.png">

```
return code is 0 because the file name matches
```

<img width="230" alt="Screenshot 2022-11-28 at 11 45 37 AM" src="https://user-images.githubusercontent.com/68624067/204367011-f5433195-58b8-4276-a020-05e10532a025.png">

```
return code is 1 because the file failed to compile
```
