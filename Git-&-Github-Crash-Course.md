1. Download and install Git on your system: https://git-scm.com/download

<br/>
<br/>

2. Configuring Git

After installing Git, you can also configure it - most importantly, you can set a username and email address that will be connected to all your code snapshots.

- This can be done via:
```
git config --global user.name "your-username"
git config --global user.email "your-email"
```
You can learn more about Git's configuration options here: https://git-scm.com/docs/git-config

Incase to check all the git global configurations, hit:
```
git config --list
```

And to know more about git commands or want to look into any specific git command, hit:
```
git help
```

<br/>
<br/>
<br/>
<br/>

<h1>Git Commands</h1>
<br/>
<br/>
<br/>
<br/>
3. When you have some new code repo on your local system , so as a first step you should open a terminal and set the location to the repo's folder and then hit

   ```
   git int # this will intiallize the project in git by creating invisble .git folder
   ```
   <img width="842" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/db6f3fb8-922d-4947-902e-0d960e6acf92">

<br/>
<br/>

4. Stagging files and creating commits
   <img width="1315" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/a7681c5d-ce70-4c59-bdeb-2c8431fe240a">

   - these commits are created so that you can anytime go back to any of these commits..
   -  from above image we learned
      - **git add <File(01) NAME> <File(02) NAME> <File(03) NAME>**: it will set the stage to commit
         - Another way to stage all files at ones is "**git add .**" or "git add *" . Downside of this approach is that it add all the files in the repo which may include any unwanted files..  and so you can add ".gitignore" file and mention files which you want git to ignore and Hence now you can use "git add ." and it will add only the required files and ignore the unwanted files(refere point # 9)
      - **git commit -m " ENTER YOUR MESSAGE HERE "**: it will commit the file(s) to github
      - **git status**: it provide current status like is the file in stagging or commited, what all files etc..
      - **git log**: it will provide you all the commits you have done so far, with date-time and Unique ID of that commit...


<br/>
<br/>
5. Multiple Commits and Checking out Snapshots

<img width="1315" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/c19bccb6-8267-439f-be34-43d3f6fd96cf">
   
   - **git checkout <Commit ID # >** : it will change the "code" to the snapshot of that "commit id only" from the "latest code base". And if you check status (git status) "head" directs to the "commit id" which we provide. By default git "head" directs to latest "commmit id".
     
   - **git checkout main** : By anytime if you want to restore and go back to the latest head, just checkout to "main"(means "main branch") will restore everything. and now you will see the "code base" is again back to the previous latest state and you can check all the commits or status by "git status" where "head" will direct to the latest commit..

      **NOTE** - the git checkout is not delete anything, but it was tempraray change in commits..


<br/>
<br/>
6. Undo Commits or Reverting changes with "Git revert" 

<img width="1300" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/db1dca3b-e62d-45c5-ad1f-9905f159fb79">

   - From above image, if you have to revert the commint "C6", then by using "git revert < id-of-C6 >" this will create new commit as "C7" as shown form above figure. Note - its not deleting "C6", instead just creating new "C7".

   - **git revert <Commit ID # >** - it will revert the changes of commit by creating new commit (which is just absent of revert code). In one word it Undo commit



<br/>
<br/>
7. Removing commits or Resetting code with "git reset"

- **git reset --hard <Commit ID # >**  : to will delete all the commits which are before mentioned commit ID..
- For we have commits C1,C2,C3,C4,C5,C6 and now if you run "git reset --hard <C3 ID # >". It will delete C4, C5,C6 and we have following commits: C1, C2, C3 available only...


8. All the above Key commands in Git
   <img width="1251" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/6de5942b-a687-4bc1-9224-ac190fcfbeb7">



9. Stagging Multiple files and ignoring with .gitignore
    <img width="1114" alt="image" src="https://github.com/BaliDataMan/github-actions-course-resources/assets/29046663/b73fb92a-da40-4fad-b5ea-e369c84d27d8">

    - Create ".gitignore" file in your repository and include all the files names which you wanted to be ignored by git and not pushed, as shown in above image, which is ".vscode" and ".DS_Store"
    - now you can use "git add ." that this will stack all the files at ones and ignores all the files which are mentioned in the .gitignore file.
    