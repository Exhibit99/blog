---
layout: post
title:  "Github Privacy Best Practices"
date:   2022-05-12 00:00:00 -0500
categories: privacy
image: img/blog/github-privacy.gif
author: Operation Privacy
featured: true
---

GitHub is a great platform to store and sync code. It's great to host a free static website or an open-source project to collaborate on. It also does **not** have great privacy.
<br/>
<br/>

Every time you push code to GitHub, it embeds a username and email in the commit. Every commit has a unique hash and everyone with access can see the details of each commit. This is to see who worked on it, to sync the code, or to roll back changes.
<br/>
<br/>

## Public vs Private Repos
These tips and techniques apply to both public and private repos. **Public** repos by definition can be viewed and copied (forked) by anyone. **Private** repos can only be accessed by you and whomever you put in as a collaborator. Sometimes we start off our code in a private repository, we temporarily add collaborators to make changes, or convert it to public for open source projects, blogs or websites which require public repos. Either way, being proactive in the following privacy best practices will help accidental exposure.
<br/>
<br/>
Some personal information, secret keys or comments can be exposed to the public if proper care is not taken.

## Extracting GitHub Usernames/Emails
To see a raw list of user names and emails for any public repository, enter the following URL in your browser, substituting `USERNAME/APP` with your target's GitHub username and repository name:

> https://api.github.com/repos/USERNAME/APP/commits

<br/>
You will get a dump of json formatted data. If you search for the keyword "@" or "email: ", you will find many entries (one per commit), each with a name/email pair.

<br/>

With lots of trial and error, I've cleaned up the output so that it only filters out the author names with emails. Enter the following into a terminal window, replacing `USERNAME/APP` with your specific github repo. I've put in Simple Login's repository for the follwing example:


```
curl -s "https://api.github.com/repos/simple-login/app/commits" | grep -Eio '([[:alnum:]_.]+@[[:alnum:]_]+?\.[[:alpha:].]{2,30})'
```

The result will be a clean list of only names and emails taken from each commit in order of newest to oldest.


![CLI output of curl command]({{"/img/blog/git-api-output.png" | relative_url  }} "CLI output of curl command" )

## Changing Defaults

By default, GitHub uses your registered username and email in the commit. But you can change that.<br/>
<br/>

### Offline
If you are using VSCode or any other code editor on your computer, you can see a hidden folder in your working folder called `.git`

While in your repository's folder enter the following command in your terminal to view the configuration file:

```
cd .git
cat config
```

<br/>
Under `[user]` you will see the email and name used. If you would like to edit this, enter the following commands in the terminal (you can be in any folder as they apply globally):

```
git config --global user.email "john@doe.com"
git config --global user.name "John Doe"
```

<br/>
Now every git repository on your machine will use that username/email. If you want to override certain folders to use a different email/name combination every time, you can run these commands in your projects top level folder where the hidden `.git` folder is:

```
git config --local user.email "john@doe.com"
git config --local user.name "John Doe"
```

### Online
If you are on the GitHub Website and make changes to the the code from their interface, then there is another place you need to configure these settings.

[https://github.com/settings/emails](https://github.com/settings/emails)

1. Click on your `profile` image on the top right corner.
1. Click on `Settings`.
1. Click on `Emails` on the left.
1. Check the box 
    
    &#9745; `Keep my email addresses private `

   This will generate a random email ending in `@users.noreply.github.com` for your committs.
1. While you're here, check the box below it as well for protection:

    &#9745; `Block command line pushes that expose my email`


## Fixing Past Mistakes

If you look at your own GitHub repo and see that you have accidentally exposed your email (or name) in the commits (by using the curl command previously mentioned), then you need to do one the following.

### a. Reset History

The quick and dirty way is to start over by destroying all git settings. This is done by deleting the hidden `.git` folder in your project folder. This folder holds all **history** and git **configurations** (like name/email to use). Don't worry, it will not destroy your project files. You won't be able to see past commits or the comments left on them. After you manually delete this folder (by revealing hidden files in your file explorer or through the command line), you will have to push the code out again to GitHub. (VSCode will make it easier)

> Warning: If you've set a `git config --local` command on that folder, that will be lost. You will need to set that again before you commit and push your code out. If you've set a global name/email with `git config --global`, then you should not worry

> If you have collaborators, it may screw things up a bit.

### b. Swap Branches

The prefered and cleaner method is to put your code in a **new** branch, **delete** the main/master branch and **rename** the new branch as main or master (whichever name you have used). This preserves the settings but destroys all commit history. I've found that I have very little issues with this method. Just enter the commands below in succession while on your primary branch, I'll assume it's called `main` (if it's `master` then change the name.)

You can start with cloning it if you don't have the folder locally. You can skip this if you already have a working folder:

```
git clone https://github.com/USERNAME/REPO.git
```
<br/>
Next, while in the main branch, create a new branch, add all the files to it, commit it, delete the main branch and rename this branch as the main. Then push it out to GitHub. 
```
git checkout --orphan latest_branch
git add -A
git commit -am "init"
git branch -D main
git branch -m main
git push -f origin main
```

### c. Edit Commits

If you do not want to lose history, then there is a more complicated and time-consuming way which **I do not recommend**. You will have to identify each commit with it's ID that you want to edit. If you have hundreds, then this is not feasible and prone to error. You can use the command `git rebase` for an interactive prompts to change anything.
A detailed tutorial is written [here](https://www.git-tower.com/learn/git/faq/change-author-name-email "Git - Rewriting History"). 
<br/><br/>
I have screwed it up every time and for small repos with up to 2 collaborators, it is just easier and faster to use the previous method of swapping branches. If you lose collaborators, just add them again.

## Other Considerations

Make sure to use common sense and not put any other private information in the **comments** of your code or any static **API keys**, test **credentials**, or private **environment variables**.
<br/>
<br/>

With these steps, you can keep your GitHub work private and prevent accidental exposure of information.
<br/>
<br/>

---

### Glossary Of Terms Used

| Term  | Description  |
|---|---|
|**repo**|Short for repository. That is the name of your project. You will have one fixed username and make custom project names.|
|**git**|A code version history management system.|
|**fork**|A copy of the code repository.|





