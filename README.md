## GIT - homework 1 - JSON
This is a part of GIT homework 1. To see all the GIT homeworks, click [here](https://github.com/ida-que/GIT-homeworks).</br>
_Note: To work with GIT repos, I used some of these necessary tools:_
- _a GitHub account_
- _GitBash (for Windows) to write commands_
- _Git installed to operate Git repos_
- _folders for keeping local repos (I used `mkdir` Bash command to create those in terminal)_

### Contents
1. Create a remote repository called _JSON_.
2. Clone the JSON repository to the local computer.
3. Create a _new.json_ file inside the local JSON.
4. Add the file to Git.
5. Commit the file.
6. Send the file to a remote GitHub repository.
7. Edit the content of the file _new.json_ - write information about yourself (full name, age, number of pets, future desired salary). Write everything in JSON format.
8. Send the changes to a remote repository.
9. Create a _preferences.json_ file.
10. In the _preferences.json_ file, add information about your preferences (favorite movie, favorite series, favorite food, favorite time of year, country you would like to visit) in JSON format.
11. Create a _skills.json_ file, add information about skills that are going to be learned at the course in JSON format.
12. Send two files at once to remote repository.
13. Create the _bug_report.json_ file on the web interface.
14. Save the changes at the web interface.
15. At the web interface, modify the _bug_report.json_ file and add the bug report in JSON format.
16. Save the changes at the web interface.
17. Synchronize remote and local JSON repository.

## STEPS
#### 1. Create a remote repository called _JSON_.
To make this first step, I go to my GitHub account, then go to the _"Repositories"_ tab and click on _"New"_ button.
#### 2. Clone the JSON repository to the local computer.
To clone the repo JSON, firstly I don't exit GitHub and copy the link to for a command in terminal.</br>
Then I go to GitBash CLI and create a folder e.g. _GIT_ with `mkdir` command, this is where I'm going to clone the repo.</br>
I clone the remote repo to the working directory by typing a command and pasting the link:
```
$ git clone https://github.com/ida-que/JSON.git
```
Now, we have a repository cloned locally and can add files.
_Note: this command creates a separate directory e.g. JSON where keeps the local repo._
#### 3. Create a _new.json_ file inside the local JSON.
Now, let's go to CLI:
```
$ touch new.json
```
#### 4. Add the file to Git.
To prepare the content for the commit to the remote repo, I typed:
```
$ git add .
```
and checked if the changes are added with a `git status` command. The terminal showed as follows:
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   new.json

```
#### 5. Commit the file.
The next step is a commit. A commit is a kind of snapshot of changes, it has a special identifier, so you can come back and see.
When you commit (`git commit`), you also add a message that helps you to summarize the changes we added (`-m`)
```
$ git commit -m "blank new.json added"
```
```
[main (root-commit) 6928ae8] blank new.json added               # here we can see the commit identifier 6928ae8
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.json
```
#### 6. Send the file to a remote GitHub repository.
We use `git push` command for sending the commit to the remote repo at GitHub and get the answer that the process is successfully done:
```
$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 221 bytes | 221.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/JSON.git
 * [new branch]      main -> main
```
#### 7. Edit the content of the file _new.json_ - write information about yourself (full name, age, number of pets, future desired salary). Write everything in JSON format.
I am using here the `vim new.json` to open vim editor and write the info e.g.:
```json lines
{

    "full name":"Ida Que",
    "age":25,
    "number of pets":0,
    "future desired salary":10.000
    
}
```
#### 8. Send the changes to a remote repository.
As we have only 1 file to send to the remote repo, we can use either `git add path/to/file` command or just `git add .` to add all changes to prepare for a commit.
```
$ git add .                                                         # adding the changes to Git, preparing for the commit

On branch main      
Your branch is up to date with 'origin/main'.               

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   new.json                                        # notification about file modification
```
Then:
```
$ git commit -m "added information about myself to new.json"        # committing with an appropriate message

[main e810d4d] added information about myself to new.json  
 1 file changed, 8 insertions(+)
```
Finally, uploading the changes to the remote repo:
```
$ git push                                                  

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 354 bytes | 354.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/JSON.git
   6928ae8..e810d4d  main -> main
```
#### 9. Create a _preferences.json_ file.
As we out information to the file in the very next step, I straightly used `vim` to create the file and add info:
```
$ vim preferences.json
```
Then press `Insert` to be able to modify our new json.
#### 10. In the _preferences.json_ file, add information about your preferences (favorite movie, favorite series, favorite food, favorite season, country you would like to visit) in JSON format.
Here, we use _vim_ editor to type into a file:
```json lines
{
        "favourite movie": "Inception",
        "favourite series": "Shameless",
        "favourite food": "shakshuka",
        "favourite season": "spring",
        "country I would like to visit": "China"
}

```
Then press `Esc` and `:wq` to save and quit.
#### 11. Create a _skills.json_ file, add information about skills that are going to be learned at the course in JSON format.
Let's try a `cat >` command here as an option to create a file and type info right in the terminal:
```
$ cat > skills.json
```
```json lines
{
    "skills": [
        "Writing Bash commands and simple scripts", 
        "Working with GitHub and Git",
        "Understanding the most popular test design techniques",
        "Understanding client-server architectire",
        "API testing with Postman",
        "Writing test documentation",
        "Web and mobile testing with devtools",
        "iOS/Android traffic monitoring with Charles and Fiddler",
        "SQL basics",
        "JMeter load testing basics",
        "Developing simple mobile apps with Xcode/Android Studio"
    ]
}
```
After typing the last line, press `Enter` and `Ctrl+C` to save and quit.</br>
_Note: I would recommend using `spaces` not `Tabs` here to feel more confident with managing the file structure._
#### 12. Send two files at once to the remote repository.
As I already new some bash hacks, I can probably add, commit and push these new 2 files by one-line command using `&&` operator.</br>
_Note: `&&` operator means "if the previous command has been successfully executed"_
```
$ git add . && git commit -m "adding preferences.json and skills.json" && git push
```
As a result, we have all three commands successfully executed.
```
[main 77bd9e0] adding preferences.json and skills.json
 2 files changed, 22 insertions(+)
 create mode 100644 preferences.json
 create mode 100644 skills.json
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 729 bytes | 182.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/JSON.git
   e810d4d..77bd9e0  main -> main
```
#### 12(a). Changing json files' keys to camelCase.
According to the [Google Json Styles Guide](https://google.github.io/styleguide/jsoncstyleguide.xml?showone=Property_Name_Format#Property_Name_Format), all the property names have to be camel-cased, so let's go back and try to change all our keys (example for _new.json_ file below):
```json lines
{

    "fullName":"Ida Que",
    "age":25,
    "numberOfPets":0,
    "futureDesiredSalary":10.000
    
}
```
Now, let's try to add and commit the changes of the files by another one-line command:
```
$ git commit -a -m "json change keys to camelCase"
[main 9aa97c8] json change keys to camelCase
 2 files changed, 8 insertions(+), 8 deletions(-)
```
_Note: `git commit -a -m` allows us to add the changes and commit them at once. However, we can use this command ONLY in case we already have the files in our remote repo._</br>
Now, we only have to do `git push` for uploading the changes to the remote repository.
#### 13. Create the _bug_report.json_ file at the web interface.
This step means going to GitHub page and creating the file from there. Just add a new json file and write into the text editor:
```json lines
{
  "id": "170",
  "severity": "minor",
  "priority": "low",
  "title": "Space character in img src URL of the 'CFD vs Aktien' image of [CFD vs share trading] sidebar item",
  "environment": [
    "Windows 10 Chrome 112",
    "iPhone 11 16.4.1 Safari"
    ],
  "stepsToReproduce": [
    "1. Navigate to capital.com",
    "2. Choose language DE",
    "3. Hover on menu section [Schulung] (EN: Education)",
    "4. Click menu item [CFD-Handel] (EN: CFD trading)",
    "5. Click sidebar item [Was ist der Unterschied zwischen Aktien und CFD?] (EN: CFDs vs share trading)",
    "6. Open devtools and look at the img src href"
    ],
   "precondition": "none",
   "expectedResult": "img src URL has no spaces so the image is displayed on the webpage",
   "actualResult": "img src URL has a space so the image is not displayed on the webpage",
   "attachment": "(URL to the video)",
   "postcondition": "none",
   "reproducibility": "n/a",
   "author": "ida-que"
}
```
#### 14. Save the changes at the web interface.
Under the editor section, we have a section called _"Commit new file"_ with a message and description input fields. I left the first input field as is, as it was proposed to have a message _"Create bug_report.json"._</br>
I also left the second input field empty as it is an optional extended description.</br>
Finally, there are radio buttons representing options of committing the file to `main` branch directly or creating a new separate branch for the JSON repo. I chose committing to the `main` branch.</br>
Then, just send this commit, and we're done :smile:
#### 15. At the web interface, modify the _bug_report.json_ file and add the bug report in JSON format.
What if I see that I provided an incorrect ID for this bug report and want to set it as an integer? We can go to the file at GitHub and modify by opening the file and clicking on pencil icon :pencil::
```json lines
"id": 171,            # changed id 170 to 171 and converted this value to integer
```
#### 16. Save the changes at the web interface.
Here, we do similar to the step 14. Commit message is also proposed: _"Update bug_report.json"_, I changed it to _"Update bug report ID in bug_report.json"_
#### 17. Synchronize remote and local JSON repository.
For this step, we go back to our terminal to type a `git pull` command. We mention which exact branch we want to be pulled to the local JSON repo:
```
$ git pull origin main
```
As a result, we have command successfully executed, with a notification that our new file _bug_report.json_ has been added.
```
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 1.83 KiB | 25.00 KiB/s, done.
From https://github.com/ida-que/JSON
 * branch            main       -> FETCH_HEAD
   9aa97c8..e97fe8d  main       -> origin/main
Updating 9aa97c8..e97fe8d
Fast-forward
 bug_report.json | 25 +++++++++++++++++++++++++
 1 file changed, 25 insertions(+)
 create mode 100644 bug_report.json

```
_Note: we can also make sure the file is added by using `ls` command (see the list of the files in working directory), or we can straightly open the new file by `cat` command.