# Getting started 

Before you start working on the Germantown YWCA, you'll need a github account. To do that [Sign up for a Github Account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home). 

Once you have an account, open up the [germantown-y repository](https://github.com/digbmc/germantown-y). It looks like this 

![Screenshot of germantown-y repository](screenshots/getting-started-1.png)

Github works with a verison control system called Git, which allows for project collaboration. Instead of everyone working on the same version of the project, Git has a feature called branching (link?). Branches are copy of the main branch you can work on, without affecting the main branch/site. 

## create a new branch 

1. Click on branches to navigate to the page. 
![a screenshot of the repository menu, with a circle around the branches button](screenshots/getting-started-2.jpeg)
Once you click that button, you'll arrive on the branches page
![a screenshot of the branches page, with arrows pointing to the pull requests section, defualt branch, and commits tracker](screenshots/getting-started-3.jpeg)
This is where you'll find all the information you need to know about the branches you're working on. 
2. Click on the new branch button
3. Enter the name of your new branch. It can be anything, but it's helpful to name it after what you're planning to work on. Unless you're trying to work off someone else's branch, leave the source as main. Click the create new branch button
![Screenshot of the create new branch fourm, with test written as the branch name](screenshots/getting-started-4.png)
4. Under the your branches section, your new branch should appear. Click on it. 
Now, with your branch created, you have an exact copy of the main site to work with. 
![a screenshot of the repository home page, with the test branch circled](screenshots/getting-started-5.jpeg) Make sure to check what branch you're working on before you start changing things. 
5. Make changes (we'll get into this later, but for now this is just an outline of what your workflow will look like)
## Merging your work with the site 
After you've finished making your changes in the branch, you can create a pull request to merge them into the main site. A pull request sends a request to github to merge your branch into main. Merge meaning your changes will move from the branch you're working in into the main branch, becoming visable on the site. When you create a pull request, a site administrator will look at to make sure none of the code conflicts with the main branch. Once there are no conflicts, your branch will be merged, and your changes will be live on the site.

1. Click on the pull request button from the main menu
![screenshot of the menu bar, with pull request circled](screenshots/getting-started-6.jpeg)
2. On the pull requests page, click on the button titled new pull request. 
3. change the compare branch to the branch you want to merge
Note: The pull request page will load with the files you're trying to change and if the branch can automatically merge. If your branch can't automatically merge, you can still create a pull request. A site administrator can fix the conflict. 
4. Click, the create pull request button
5. You've created a pull request! Assuming there are not major issues, your changes to the site should be live soon. 



## The guide for interns and other people who want to work with the source code

Before you start working on the Germantown-YWCA website, here are the major tools used on the site. 
- [Git](https://git-scm.com/) is an open-source version control tool that allows people to work with different versions of a project together.  
- [Github](https://github.com/) is a platform for hosting projects that use Git. The Germantown YWCA Website is hosted and deployed using Github
- [Jekyll](https://jekyllrb.com/) is a static site generator that works with Github to generate the site. 
- [CollectionBuilder](https://collectionbuilder.github.io/) is a Jekyll-based framework for hosting digital achives. It's used as the template for this site. 

This guide will set up with all the software you need to start working with the site. 

## Terms to know 

Technical terms can be a lot. Here are some that you may see in our documentation.

- Open-source: Software that is free to use, with accessible source code. 
- Hosting: Where files are stored. A text file on your computer is hosted locally. A google doc is hosted on Google's servers. The Germantown YWCA site is hosted on Github
- Deployment: To make a site live. Github uses Github pages/actions to deploy (explain this better)
- Static-Site: A static site is one with pages that don't change depending on the user (get a better definition). Static sites load faster, and are more eviormentally friendly than dynamic sites (define dynamic!)
- Remote: The repoisotry stored on Github
- Local: The repository stored on your computer

## Software to install 

- [Create a Github Account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home). You need a Github account to add and edit riles on the remote repository. 

- [Download VSCode](https://code.visualstudio.com/). VS code is a text editor that will allow you to edit and create files for the site. You can use another text editor, but VS Code is useful because of the active support and extensive library of add-ons.

- VSCode Extensions 
    - 

- [Install Git](https://collectionbuilder.github.io/cb-docs/docs/software/git/) Git will allow you to communicate with the remote repository (explain better)

- [Install Ruby](https://collectionbuilder.github.io/cb-docs/docs/software/ruby/). You need to have Ruby downloaded to run

- [Install ImageMagick and Ghostscript](https://collectionbuilder.github.io/cb-docs/docs/software/optional/). This software processes files in the archive


## Creating your local repository

To create your local repository, we're going to be using VS Code's interface. You can also do this in terminal. 

### Using VS Code
1. Open an empty VS Code Window 
2. Under the start menu, select "Clone Git Repository" 
3. In the bar asking for a link to the remote repository, copy and paste this link: https://github.com/digbmc/germantown-y.git
4. When prompted, decide where you want to store your repository. 

### Using terminal
1. Open your terminal (Git Bash on Windows/Linux, Terminal for Mac) 
2. Navigate to folder you want to keep your local copy of the repository in. For example, if you wanted to store the site in your documents folder you would enter in the terminal...
``` cd Documents ```
cd stands for "change directory" 
3. Once in that folder, input ``` git clone https://github.com/digbmc/germantown-y.git ``` and press enter
4. Now in documents, there will be a folder titled germantown-y. Open it in VSCode 