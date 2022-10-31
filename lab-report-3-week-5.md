# less

## less -N filename

<img width="467" alt="Screenshot 2022-10-30 at 7 52 28 PM" src="https://user-images.githubusercontent.com/68624067/198921106-688dbe15-e4ac-4d0d-8f8f-dd704ebc65a2.png">

output:

<img width="304" alt="Screenshot 2022-10-30 at 7 52 13 PM" src="https://user-images.githubusercontent.com/68624067/198921080-ea3ba897-7e7b-4e4c-ba03-13980606cba7.png">

```
"less -N filename" displays line numbers at the beginning of each line 
inside the "temp.txt" file. i think it is useful to see how many files 
are listed
```

## less -X filename

<img width="468" alt="Screenshot 2022-10-30 at 8 00 06 PM" src="https://user-images.githubusercontent.com/68624067/198922021-46fe1f58-12c6-4977-b12e-0935ba5e1573.png">

```
"less -X filename" is listing all the contents of the file "temp.txt" file 
but it will stay inside your terminal after quiting. i think it is useful
for refering back to in your terminal without rerunning the less command
```

## less -M filename

<img width="466" alt="Screenshot 2022-10-30 at 8 08 57 PM" src="https://user-images.githubusercontent.com/68624067/198922987-e86ebdae-5a74-4b2b-a78b-3993eb736506.png">

output:

<img width="280" alt="Screenshot 2022-10-30 at 8 08 04 PM" src="https://user-images.githubusercontent.com/68624067/198922889-e6fe4b8c-3060-4e71-9c9d-4ff62a32cc45.png">

```
"less -M filename" shows what range of files you scrolled to, 
how many files in total, and the percentage of the file "temp.txt" file. 
i think it is useful to have some metrics to where you are. it feels
overwhelming where the file is thousands of lines long
```

# find

## find filename -empty

<img width="453" alt="Screenshot 2022-10-30 at 8 25 09 PM" src="https://user-images.githubusercontent.com/68624067/198924726-8c1a5192-177d-4160-9baf-95566a3bcc29.png">

NO OUTPUT ABOVE

output (after adding an empty folder):

<img width="447" alt="Screenshot 2022-10-30 at 8 29 33 PM" src="https://user-images.githubusercontent.com/68624067/198925208-5bb9953b-4a62-4e4b-b96a-f96b40af24e8.png">

```
"find filename -empty" will output every folder or file that is empty.
in the example using terminal, all the folders and files are filled, but
if you add a random empty folder inside terminal, it will display that folder
name. i think it is useful to find folders or files that are not used. it is 
a useful command to cleanup your file system
```

## find filename -type f -name "*.txt" -exec grep '{STRING}'  {} \;

<img width="468" alt="Screenshot 2022-10-30 at 8 35 45 PM" src="https://user-images.githubusercontent.com/68624067/198925877-61594c3d-638c-4073-a6a1-8ac621ff60a9.png">

output:
<img width="727" alt="Screenshot 2022-10-30 at 8 36 15 PM" src="https://user-images.githubusercontent.com/68624067/198925917-a7c02d32-f067-43fd-8991-5c3c6f0d4d28.png">

```
"find filename -type f -name "*.txt" -exec grep '{STRING}'  {} \;" 
will print lines which have ‘backward’ in them and ‘-type f’ specifies the input type is a file. 
i think this is useful to find how many times a certain word is referenced.
```

## find filename -name *.txt 

<img width="465" alt="Screenshot 2022-10-30 at 8 39 05 PM" src="https://user-images.githubusercontent.com/68624067/198926224-c740febd-5a9f-4252-bb5a-594afd9dfe87.png">

output:

<img width="728" alt="Screenshot 2022-10-30 at 8 38 48 PM" src="https://user-images.githubusercontent.com/68624067/198926189-f0f04610-0ca7-4186-b867-5edac52c9d77.png">

```
"find filename -name *.txt" will give all files which have ‘.txt’ at the end. 
i think this is useful to find a specific file type inside a directory
```

# grep

## grep -i "{STRING}" filename

<img width="468" alt="Screenshot 2022-10-30 at 8 43 26 PM" src="https://user-images.githubusercontent.com/68624067/198926707-dad9f819-8f47-40bf-b916-2622b442ef10.png">

```
"grep -i "{STRING}" filename will search for a string case in the given file.
this command is not case sensitive. i think this is useful to narrow down
a huge file using an inputed string
```
## grep -c "{STRING}" filename

<img width="466" alt="Screenshot 2022-10-30 at 8 49 21 PM" src="https://user-images.githubusercontent.com/68624067/198927252-feb2f399-37f9-4604-a05b-65084430e52c.png">

```
"grep -c "{STRING}" filename" will find the number of lines that matches the given 
string. i think this is useful to find out how many files matches the inputed string
```

## grep -n "{STRING}" filename

<img width="471" alt="Screenshot 2022-10-30 at 8 52 02 PM" src="https://user-images.githubusercontent.com/68624067/198927520-77b76090-c551-4574-aa47-91c9e3707044.png">

```
"grep -n "{STRING}" filename" will show the line number of file with the line that
matches with the inputed string. i think this is useful for immediately finding
which line has a particular file you are looking for
```

