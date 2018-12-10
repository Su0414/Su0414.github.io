---
layout: post
title:      "ShopDrop, ReactJS/Redux Application"
date:       2018-12-10 04:39:19 +0000
permalink:  shopdrop_reactjs_redux_application
---


**SHOPDROP - React JS / Redux / Rails Shopping Cart Application**

For my final portfolio project at Flatiron School, 

I built a shopping cart website using **React JS and Redux as front end and with Rails 5 as backend. **

The main motivation behind my website **SHOPDROP** was presenting a **catalog of Indian dresses**, 
designed by famous Indian fashion brands. These brands provide exclusive collections for customers to wear on special occassion like Wedding, Anniversaries, Birthday Parties and Festivals.
Customers can view a wide range of collection from traditional to Indo Western outfits.
Many of these poster dresses can be made available to customers outside India through this shopping website. 

This section of cirriculum was huge and 
here I shall talk only about the basic setup required for project.

**So lets dive into it....**

First,  I created Rails backend application and then created React client application 
and connected front end and back end with Rails CORS

So, there are several ways to create Rails application, you can either use **Rails Scaffold**,  
which refers to the auto-generation of a set of a model, views and a controller usually used for a single database table.

`rails generate scaffold app-name`

OR 

you could use 

`rails new app-name `

and use rails generators to build your models and controllers. 

Then, creating React application is very easy can be done with one command, 

`npx create-react-app my-app`

I use npx as it comes with npm 5.2+

**Rails CORS** is a gem

`gem 'rack-cors'`

It is used if have your frontend and backend on different domains you shall need to allow 

**CORS (cross-origin HTTP request).**

so that your server allows you to perform CRUD operations with your database.

Rails 5 with --api mode will prepare the setup for you. You just need to uncomment your cors.rb file

```
#config/initializers/cors.rb
Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins 'localhost:4200'
    resource '*',
      headers: :any,
      methods: %i(get post put patch delete options head)
  end
end
```

**Creating static pages for website using React MDL**

What is React MDL, **React-MDL** is a set of React Components for **Material Design Lite**, called “MDL”, it is maintained by Google

I used React MDL components in my project for designing page layouts and various components.
This helped me focus on building different features of the application rather than look and feel of the pages.

[React MDL github link ](https://tleunen.github.io/react-mdl/)



**Adding Redux Thunk**

The main role of Redux Thunk into our application is as a State container, managing the state of our application. 


[This link provides good explanation with reasons for using Thunk.](https://github.com/reduxjs/redux-thunk)


After this stage of setup of your application , 

you can play around and decide how you want to build your components and application workflow.

This was the time when I actually started working on feature building around my containers, actions, reducers and components. It was definitely challenging to put all the pieces of the puzzle together. 

But, I really enjoyed working through this application. 

And finally, I want to convey a **special thank you** note to **Flatiron instructors and learn.co instruction videos**.

**Keep Calm and Code Along**



