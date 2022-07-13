---
layout: post
title: Ruby on Rails
category: Programming Language
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/13/Ruby-On-Rails/
---

### WebPage and MVC Overview

Gem File :  What gem file does it allows us to install differrent things into the apps, like third-party things are added into the gem file.

Rails are known as MVC Architecture-(Model View Controller).
1. Models : Databases
    In Rails you can use any kind of databases and nothing on the app changes, no need to change the code, because Rails abstract the databases. Just need to change the gem in the gem file.
2. Views: Webpages
3. Controller: Controller is basically the brain behind the scene. Like Django we have view.py file it's something like that.

To write something for rails we need git bash terminal
To create a webpage we need generator. 
 > rails g controller home index

- '.erb' extension helps us to use embedded ruby on the html web pages.

 > rails s
*To start the server*

now to check whether the server has started or not properly,
we can check on the webpage by typing **localhost:3000/home/index**

now to change anything, we have to head back to the VSCode or Sublime text, and check the app folder, in which we have views folder, and then home folder.

To change the URL *localhost:3000/home/index* to *localhost:3000*, we just have to have to change the route.
1. To change the route go to config directory and look for routes.rb file and you will see
```rb
Rails.application.routes.draw do
    get 'home/index'
end
```

change it to

```rb
Rails.application.routes.draw do
    root 'home#index'
end
```

To check all the routes, go to terminal
 > rails routes

