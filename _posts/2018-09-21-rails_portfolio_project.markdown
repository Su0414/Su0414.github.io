---
layout: post
title:      "Rails Portfolio Project"
date:       2018-09-21 19:12:28 +0000
permalink:  rails_portfolio_project
---


My rails CRUD application is a **Project management ** application, 

Main purpose of building this application was to help small or medium size software companies to manages their client projects and associate their employees to their client projects.

Initially I was very excited to do a full fledge application with many interesting features but 
when I started to put things on paper they were getting very complex.

So I decided to go with only 3 models Project, Task and User and bring it to a working phase. 

Basically, right now application manages project tasks for different types of users like owner and employees.

Users can view their list of pending tasks and work on it and mark them completed.

Rails is very broad and this project touched many complex topics like Omniauth, Helper methods, 

many to many associations, Activerecored Scope methods, Nested Resources, and ..list goes on...

**Two major features** that took time for me to get comfortable was

**Omniauth Authentication** 

Most part I enjoyed was successfully implementing Omniauth authentication.

User sign up and login through social media was complex as I had to provide admin rights to some users.

I experimented with different Omniauth strategies like twitter and github. 

Following links were very useful read...

https://developer.twitter.com/en/docs/basics/authentication/overview/3-legged-oauth.html

https://github.com/omniauth/omniauth-github

**Nested Routes**

We need to create minium 2 nested routes for this project 

I used generators to create my models. 

```

class User < ActiveRecord::Base

    has_many :tasks
    has_many :projects, through: :tasks
		
end 

class Task < ActiveRecord::Base

    belongs_to :project
    belongs_to :user
		
end 

class Project < ActiveRecord::Base

    has_many :tasks
    has_many :users, through: :tasks
		
end 

```


This explains **has_many through associations**, and nested resources 

```
resources :users do 
      resources :tasks, only: [:index]          
  end 
  
  resources :projects do 
      resources :tasks do 
        member do 
          patch :complete
        end 
      end
  end
```

Run **rails routes** into rails console to see more detail route paths. 
Example of nested routes

1. users/1/tasks, 

2. projects/1/tasks/1/complete etc...


For example , If you create 
```
 resources :articles
```

[Creates 7 HTTP action verbs for you ](https://guides.rubyonrails.org/routing.html)

You are not limited to the seven routes that RESTful routing creates by default. 

I added a new route eg  "complete" as new member/action verb.


With nesting, Keeping code DRY was also a challenge.

Here is  [Github link for project :](https://github.com/Su0414/project_management)

In conclusion,

Rails projects was all magic but any custom changes behind that magic can be a bit challenging. 

I still have a chance to scale this project by adding more models and more features. 

And I would be continuing working on this rails project. 



**Happy Coding !**










