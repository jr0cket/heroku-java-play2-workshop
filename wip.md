---

<link href="index.css" rel="stylesheet" type="text/css">

# Heroku Workshop - Java Play Workshop - WIP

- Pre-dowload Play Framework for Mac, Linux, MS Windows

# Play 




# Postgres Features
  
## dataclips
  
## backups 
  
## Replication & database migration   
  
  You can configure one postgres database to follow another.  This gives you a backup of your original data but in a seperated database
 
   This is useful for
   
   - analytics and reporting
   - testing your application with live data before deployment
   

[TODO: rollbacks and database ?  What are the best practices in managing data when you rollback ?]

 
??
heroku logs:drains              -- manage syslog drains


# Using multiple accounts for Heroku

  Sometimes you have one account on Heroku for billing purposes and another for developing applications with.  
  
  The simplest way to manage this is to create your apps with your billing heroku account and for each app you create you add the email address of your developer account as a collaborator.
  
## Hacking your project git config  

  A more technical approach to multiple accounts is to hack the git configuration in a specific project.
  
  In your ~/.ssh/config file, create a specific host definition for one of your heroku accounts, in this case we are creating a host for an heroku account used for billing (rather than app development)
  
    Host heroku.billing
      HostName heroku.com
      IdentityFile ~/.ssh/id_heroku_billing_rsa
      IdentitiesOnly yes
  
  Then edit the git remote url in your project **.git/config** file in your local repository for the project. Change the file to look like:

    [remote "heroku"]
      url = git@heroku.billing:<appname>.git

  The updated url should point to the host you have defined in the ssh config file and the app name is the usual app name that was generated by heroku create.

## Other Alternatives
* [Managing multiple heroku accounts](http://martyhaught.com/articles/2010/12/14/managing-multiple-heroku-accounts/)
* [Heroku accouts](https://github.com/ddollar/heroku-accounts)

# Using Heroku Labs


# Heroku Clone

[Q: is this a lab or new feature ?]

  If you want to create a complete copy of an existing Heroku application, you can use the `heroku clone` command.

    
  
  Cloning an existing app could be useful if you want to develop a similar app and use the existing app as a base.  You could also create an application template from which you want to create all your apps.
  
https://devcenter.heroku.com/articles/git-clone-heroku-app  


## Heroku fork

  Make a complete copy of an application, including the add-ons and data migration.
  
  

[Back to Workshop home](index.html)








<link href="index.css" rel="stylesheet" type="text/css">

# Using Mongodb

[Back to Workshop home](index.html)


<link href="index.css" rel="stylesheet" type="text/css">


# 12 factor app - creating scalable apps
 


# Scaling apps
There are often questions about auto-scaling of apps (competitor services offer this directly).  I relate auto-scaling with auto-billing, emphasising the importance of understanding how well your app scales on one instance, before investing in more.


## Perfomance Monitoring
Test the performance of you java app with jmeter

see how well it scales with one dyno, then scale it up to several dynos and increase the load.  This helps you figure out how much your app will scale based on the number of requests.

Drilling deeper you can measure the performance of different types of requests.  You can use services like New Relic to gather data and visualise it to help you understand what is going on.



[Back to Workshop home](index.html)








# Options on this workshop


* Adding Twitter bootstrap to the project to create some great UI designs for the site.  It will make the end result more interesting to talk about and allow some more creativity into the workshop.  See the [Twitter Bootstrap site](http://twitter.github.com/bootstrap/)


Other workshop ideas
--------------------
- Open Source project
  ¦-- using github for collaboration, pull request, using travis-ci for running tests with link to pull requests to know that they are safe to merge, using github for issue management, markdown for wiki, creating a markdown site on Heroku



Talks
-----
- polyglot developer, polyglot deployment - most developers are becomeing polyglot developers whether by design or neccessety.  With applications spreading over multiple server, devices, languages and technologies, often the most effective way is to use different tools for different jobs.  So what happens when it comes to deploy all this.  How do you manage to keep it all simple and part of the natural deployment workflow?

Enter the polyglot platform


PDF generation
--------------
Create a bash script that grabs the ruby gem and installs it, then calls the gem to generate the PDF




Resources

http://developer.force.com


forcedotcom developer user groups
http://bit.ly/fdc-dugs

Twitter accounts & hashtags
#forcedotcom
#askforce




In this chapter you will learn how to instantly deploy an application on Heroku using the Heroku Toolbelt.  You will also learn how to run the new application locally, make changes, and synchronize the changes with Heroku.  Then you will learn how to instantly scale your application, set configuration parameters through environment variables, and view your application's log entries.