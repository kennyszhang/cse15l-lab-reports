# part 1

## In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.

```
/start<Enter>dwibase<Esc>ndwibase<Esc>ndwibase<Esc>:wq<Enter>
```

## /start

<img width="469" alt="Screenshot 2022-11-13 at 8 32 44 PM" src="https://user-images.githubusercontent.com/68624067/201575825-041f88ae-69cf-458a-ad17-a2ef123eda5b.png">

```
search for start; places cursor on the beginning on start
```

## dw

<img width="468" alt="Screenshot 2022-11-13 at 8 35 02 PM" src="https://user-images.githubusercontent.com/68624067/201576094-c910855a-b094-4fb7-b630-0603d75146f5.png">

```
delete the characters of the word from the cursor position to the start of the next word
```

## i base

<img width="468" alt="Screenshot 2022-11-13 at 8 36 36 PM" src="https://user-images.githubusercontent.com/68624067/201576267-29033b2e-0651-4e2d-ac6e-4aab55da8499.png">

```
enter into insert mode and type "base"
```

## esc n

<img width="466" alt="Screenshot 2022-11-13 at 8 38 22 PM" src="https://user-images.githubusercontent.com/68624067/201576422-b0391bfe-5ca1-41ea-ac06-9cf5db3e8a17.png">

```
exits insert mode and finds the next instance of "start"
```

## dw

<img width="470" alt="Screenshot 2022-11-13 at 8 40 48 PM" src="https://user-images.githubusercontent.com/68624067/201576686-69b75afa-3853-4b92-b1bb-c397664a705c.png">

```
delete the characters of the word from the cursor position to the start of the next word
```

## i base

<img width="469" alt="Screenshot 2022-11-13 at 8 41 36 PM" src="https://user-images.githubusercontent.com/68624067/201576775-f57d0a48-c04c-4b1d-a6e6-dd77344f75af.png">

```
enter into insert mode and type "base"
```

## esc :wq

<img width="469" alt="Screenshot 2022-11-13 at 8 42 19 PM" src="https://user-images.githubusercontent.com/68624067/201576856-459d26c6-1104-485b-a6d7-e6d5d39b20a7.png">

```
exits insert mode; save and quit
```

# part 2

```
Consider performing the edit task you chose and re-running the program 
when you have to run it remotely. Time yourself twice:

Once, start in Visual Studio Code and make the edit there, then scp the file 
to the remote server and run it there to confirm it works (you can just run bash 
test.sh on the remote to test it out). Consider having the appropriate scp command 
in your command history or easily copy-pasteable!

Second, start already logged into a ssh session. Then, make the edit for the task you 
chose in Vim, then exit Vim and run bash test.sh.

Report how long it took you to make the edit in seconds in both styles, and any difficulties 
or details that came up in doing so.
```

```
I did not measure exactly how long each process took but running the file after scping the 
file over to the remote server was way faster than editing inside the remote server using vim. 
This is just because I am slow using vim (because I was very careful on which key I pressed) 
and I constantly refered towards the group document where I performed the command. 
```

```
Which of these two styles would you prefer using if you had to work on a program that you were 
running remotely, and why?

- I would prefer working on a program locally and pushing the file using scp to the remote server.
This is just because I am still uncomfortable using vim. 

What about the project or task might factor into your decision one way or another? 
(If nothing would affect your decision, say so and why!)

- If the project required a minor edit or if the project is only available remotely, I may be
swayed to using vim.
```

