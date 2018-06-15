---
layout: post
title:      "10 steps process for CLI Data GEM Project "
date:       2018-06-15 11:53:29 -0400
permalink:  10_steps_process_for_cli_data_gem_project
---



Implementing this first project was very good experience. Learned a lot in the process. 

I made three new project partners, Google search , Github and STACKOVER FLOW and they were very helpful. 

You can have them too..

So, Lets get started.


**1. Follow Avi's videos and examples to understand how to build the project with bundler. **

Read and understand the CLI Data Gem Project requirements before starting the project.  

Join Kenlyn's study groups, she is one of the best instructor for CLI and very helpful. 



**2. Start with Scraping a Website** 

Selecting a website for scrapping is most important part of this project. 

Use builtwith https://builtwith.com/ - to find out available websites with HTML and CSS, 

Use local websites which are NOT heavily loaded with javascript. Go for sites with simple scripts

If you are using API for your website, https://www.programmableweb.com/apis is a good resource.

Work on scraper class separately and ensure your data is scraping as you expected it to be. 

I scrapped many websites before deciding final working website for me, 

Also, previous scraping labs were my reference point.

**3. Repeat Steps 1, 2, 3** before designing your project. 

   Repeating these steps actually helped me understand the project flow.

**4. Create your Gem using bundler. **

   http://bundler.io/v1.12/guides/creating_gem.html

Next step most people find it difficult is to use - Github,

but it is not that bad, just start using it more and more to get the flow of commands.

Follow these steps below......

Goto Learn , Use sandbox or OPEN IDE,  I started building my gem in folder,  
	 
```
   mkdir projectname - this is optional 
   
   bundle gem project_name
```
   
   Follow the prompt and get a successfully created gem.
   
   You can check the *ReadMe.md file* which provides the details like Installation, Usage, Development 
	 
	 and license information etc . 
	 
   You can also see the file structure it created for you. This is also explained in Avi's Video.
   
   Use following commands in your Learn IDE , 
   
  ```
  git init              - Creates an empty Git repository or reinitialize an existing one
	 
  git status       - Shows the working tree status
	 
  git add .          - Add file contents to the index
	 
  git commit -m "first commit"    - Record changes to your current repository
   
	git status
   
```
	 
https://git-scm.com/doc - have this GIT documentation link handy 
	 
	 
**5. Create Repository on Github**
	 
Login to Github account  	
	 
Set up a new remote repository on Github to store this in.
	 
Open a new browser tab and go to github.com and make sure you are signed in.
	 
 **Create a new repository with same project_name**
   
   In our case, we need the commands for **pushing an existing repository**
   
   To push up your local work to this new remote repository, 

  ```
 git remote add origin https://github.com/..........................................
   
 git push -u origin master - to push your local changes to your online repository.
   
 git status
```
   
   Now your current working directory and master branch on Github is up-to-date and 
	 
	 you can  now  make changes and update your changes to repository.

   You can also create a  branch and work on it
   
   To create a new branch and add some files to this repository. 
   
   ```
git checkout -b project_development_branchname

	 
touch newfile.rb 
```
	 
	   
   and add and commit changes to project_development_ branchname using above commands.
	 
	 One the code of your branch is working you can merge with master branch.
	 
	 I generally like to merge master into the development (project_development_ branchname) first 
	 
	 so that if there are any conflicts, 
	 
	 I can resolve in the development branch itself and my master remains clean.
	 
	 (on branch development)
	 
```
	$ git merge master
	 
(resolve any merge conflicts if there are any)

git checkout master

git merge development   (there won't be any conflicts now)
```



**6. OO Design patterns**

After this step you can either start with your CLI class, with messages you want to interact with user or 

start with Designing Object classes. Follow Avi’s video for setting cli starting point.
   
 Use your favorite screen capture for recording a 30 min coding session and 
 
 5 min video session of project

   Vimeo - https://vimeo.com/
	 
   JoinMe - https://www.join.me/
	 
   WebEx - https://collaborationhelp.cisco.com/article/en-us/nifdygr
	 
   Few others -https://elearningbrothers.com/top-10-screen-recording-software-for-windows/
   
**7. Make frequent commits** 

Frequent Commits to your code changes,  will help you keep track of every working class or feature of your project.

**8. Share completed project link**

*Fill out the checklist form*, Have a fully completed project on Github, and share this link 

**9. Submit a blog and Video **

You also need to submit a blog post, and Share link for blog.
    
Create a video explaining in short the flow of your project, and Share link for video. 

**10. Your project is now complete for review. **

If you wish, you can take mock assessment with section leads or 

pair up for mock and project support on **#slack group #cli-data-gem-project. **
	

**Hope you find this 10 steps process for CLI GEM Project useful. 
**		
    
**Wish you good luck on your project adventure !**








