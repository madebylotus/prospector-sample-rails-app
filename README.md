# Prospector Sample Rails App
This project shows a sample Rails 4 app integrated with the [prospector](http://www.gemprospector.com) ruby client to provide analytics and insight into your project's dependencies.

## Deploying to Heroku

The easiest way to test out the prospector service with a Rails app, is to deploy straight to Heroku and provision the addon.  Be sure you've installed the [Heroku Toolbelt](https://toolbelt.heroku.com/) and logged into the service before proceeding.

Heroku Dev Center Documentation for Prospector can be [found here](https://devcenter.heroku.com/articles/prospector?preview=1).

Once the addon is provisioned, you're able to login to the Heroku dashboard, view the resources for your project and use SSO (single sign on) to easily login to Prospector and view details about the application.


### Clone the example app

Clone this sample Rails app to your computer.

```
git clone https://github.com/madebylotus/prospector-sample-rails-app.git
cd prospector-sample-rails-app

```

### Create app on Heroku

Now create a random app on Heroku, and provision a PostgreSQL database.

```
heroku create
heroku addons:add heroku-postgresql:dev
```

### Deploy sample app

Deploy the sample app to Heroku and setup the empty database.

```
git push heroku master
heroku run rake db:migrate
```

### Provision the Prospector Addon

Provision the Prospector addon itself to set ENV variables and restart the app.

```
heroku addons:create prospector
```
