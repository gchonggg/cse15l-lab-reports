# Lab Report 1

## How to log course-specific account on `ieng6`


## Step 1: Setting up CSE15L Account
First, before we set anything up, we need to create a CSE15l account. The account essentially allows us to remotely host our website on UCSD's servers. When hosted online, anyone in the world can access our website and see the many beautiful lab reports we will be writing up for CSE15l. 

First, you must first look up your course-specific account on: https://sdacs.ucsd.edu/~icc/index.php
Your course specific account should be in a blue box and inside the box will contain something along the line of cs15lsp23zz, where zz is replaced with the letter and numbers that uniquely identify you. Remember this, because we will use this to set up a password, and to access the remote servers. 

When we reached here, we must then click on the highlighted link "UC San Diego Active Directory (AD) Password Change Tool" to set up a password for remotely accessing UCSD's servers: 
    ![Image](https://gchonggg.github.io/cse15l-lab-reports/img/Screenshot%202023-04-10%20at%209.05.08%20PM.png)
UCSD wants to make sure that no one else is making malicious changes to your remote server, thus, they require you to first create a password as an additional measure when we attempt to access or change our remote server. 

Next, we will click on the highlighted link "Proceed to the Password Change Tool" as shown below: 
    ![Image](https://gchonggg.github.io/cse15l-lab-reports/img/Screenshot%202023-04-10%20at%208.58.09%20PM.png)
    
Now, we will type in your course-specific account username into the "AD Password Change Tool" box and press continue. For example, type in cs15lsp23zz is that is your course-specific account. We will then create a password for course specific account and press enter. 


## Step 2: Download Visual Studio Code
Throughout this course, we will write code in a code editor. One code editor that I highly recommend is VSCode, the code editor developed by Microsoft. To download this code editor, if you haven't already from a previous CS course, click on the following website: [VSCODE Link](https://code.visualstudio.com/)

There, you will need to click on the big blue download button and download the VSCode that matches with your computer's specs. After that, when you open the downloaded file, you will be prompted to answer numerous questions, and accept the terms of service. 

Here, I attached a youtube tutorial of someone else doing this if you are stuck.
[Youtube Tutorial](https://www.youtube.com/watch?v=JPZsB_6yHVo)


## Step 3: Connect to remote servers 

* run `ssh cse15lsp23zz@ieng6.ucsd.edu` but replace `zz` with the letters in your course-specific account
* Type yes and hit enter if the following message shows up: 

```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
You will then be prompted to type in your password. 
* Type in your full password and https://github.com/gchonggg/cse15l-lab-reports.githit enter. 
You should see something like the following: 
![Image](https://gchonggg.github.io/cse15l-lab-reports/img/Screenshot%202023-04-10%20at%208.51.08%20PM.png)

## Step 4: Run commands
Now that you are connected to the remote servers in UCSD, you can execute commands within the remote server. 
For example, you can run `cd <path>` or `ls <directory>` to navigate through the files within the remote server.


## Step 4: Creating a website with Github Pages 
https://www.youtube.com/watch?v=GZqizez1Dzs&embeds_euri=https%3A%2F%2Fucsd-cse15l-s23.github.io%2F&source_ve_path=MjM4NTE&feature=emb_title
