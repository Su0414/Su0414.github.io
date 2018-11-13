---
layout: post
title:      "AMS and Rails/JS project"
date:       2018-11-13 01:49:57 +0000
permalink:  ams_and_rails_js_project
---


Javascript was one of the biggest section of cirriculum and took me closer to real world applications. 

This project would help Project managers monitor project tasks for his/her team. She/He could assign tasks and manage completed and peneding tasks for user. I built this project on top of my rails CRUD application. 


**Understanding Active Model Serializer **

The main purpose of serialisation is to save the state of our objects, so that we can recreate it when needed. 
We serialized our objects in our controllers in JSON format, so that objects could be recreated in our Javascript files.

JSON (JavaScript Object Notation) is a lightweight data-interchange format. 

The JSON serialization process consists of two stages: 
data preparation 
and transformation to the JSON format.

Data preparation consists of transforming Ruby objects into a hash map.

```
User Model - JSON
{
	"id" => "1"
	"email" => "john@doe.com",  
 	"name" => "John Doe"
 }
```

The **ActiveModel::Serializer(AMS)** implementation is very popular although there are other data preparation tools like  FastJSON, JBuilder, JSONAPI-RB etc...

Start with adding the gem into our Gemfile and then run bundle install

```
gem 'active_model_serializers'
```

Generate the serializers for our Project and Task model:
```
rails g serializer project
rails g serializer task
```

Our serializers are generated in the app/serializers directory. 
```
# app/serializers/project_serializer.rb

class ProjectSerializer < ActiveModel::Serializer
  has_many :tasks

  attributes :id, :name, :description
end

# app/serializers/task_serializer.rb

class TaskSerializer < ActiveModel::Serializer
  attributes :id, :content, :comments
end

```


You can custom build your JSON objects to include attributes you want , here are some examples

Lets say , you don't want all the attributes of TaskSerializer you can write multiple serializers for same model

```
class SimpleTaskSerializer < ActiveModel::Serializer
  attributes :id, :content
end
```

Lets say, you want to filter your post comments created by current user

```
class TaskSerializer < ActiveModel::Serializer
   attributes :id, :content
	 
	 // scope recent comments to those created_by the current user
    has_many :comments do
      object.comments.recent.where(created_by: current_user)
  end
	
end
end 

```


Lets say you want to add edit links to only admin users

```
class UserSerializer < ActiveModel::Serializer

  attributes :id, :name, :email, :admin
	
  attribute :edit_link, if :current_user_is_admin
  
  def edit_link
    edit_user_path(object)
  end 
  
  def current_user_is_admin
    scope == object
  end
	
end
```

This link gives more details on defining associations and other types.
[Rails Serializers guide](https://github.com/rails-api/active_model_serializers/blob/v0.10.6/docs/general/serializers.md)

**Seeing JSON Data Come Back**

You can type the url in browser and add .json to view the retrived JSON object. 

Javascript Objects can be recreated using **ES6 classes or prototypes**.

An important point to note that:
**JS class declarations are NOT hoisted. **

That means, you first need to declare your class and then access it.

This is example of named class with special method **constructor** and a prototype method.

```
class User{
        constructor(userJSON){
            this.id = userJSON.id
            this.name = userJSON.name;            
            this.email = userJSON.email;
            this.admin = userJSON.admin;           
        }

	render(user){
		// display user	
		$("div.user").append(user);
	}
}

```

**Submitting a form in AJAX is simple**

1. Capture the form submit button so that the default action doesn't take place
2. Get all of the data from our form using jQuery. 
3. You can access attributes from serializer as part of your data object.
4. Submit using AJAX
5. Show errors if there are any

```
$('#create_task').on('submit', function(e){   

        e.preventDefault();
				
				// retrieves the url for form submission 
        var url = this.action;
				
				// retrieves  the **serializable_hash ** which is a JSON object 
        var data = $(this).serialize();
             
        let posting = $.post(url, data);
        
        posting
				.done(function(response){
        
				// on success render your DOM elements

                let data = new User("1", "John", "Doe", "john@doe.com", "Admin");
                data.render(data);
        })
				
				// handle errors here
				
        .fail(function() {
            alert( "error" );
        });
        
    });    


```

**Promise Callbacks:** 

You can use the **.done** callback to handle a successful **AJAX** request.  

And your final step is to display your data into DOM elements. ............................**Thats It !!**

Above example explains recreating Javascript objects using AMS, JSON and
your project flow from controller to your views. 

I really enjoyed doing this project, hope this was fun and helpful too. 

**Happy Coding !! **





