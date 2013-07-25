HootSuite-Rails-Demo-App
========================

In the directory of your choice, run

`git clone https://github.com/HS-adrianz/HootSuite-Rails-Demo-App`

##Hosting the App on Heroku:

1. If you have not used Heroku before, go to [http://devcenter.heroku.com](http://devcenter.heroku.com) and follow the quickstart steps (Sign up, Install the Heroku Toolbelt, and Login).

2. Inside the cloned repository, run `heroku create APPNAME` where APPNAME is an optional field; Heroku will generate a name for you if it is left blank. Note the URL near the end of the output of the format **http://APPNAME.herokuapp.com**. Save this URL for later.

3. Run `git push heroku master`.
    * If you get a permissions error, follow these steps.
    * If the file **~/.ssh/id_rsa.pub** does not exist, create one by running `ssh-keygen -t rsa`.
    * Run `heroku keys:add ~/.ssh/id_rsa.pub`.

4. Go to your App at [http://hootsuite.com/developers](http://hootsuite.com/developers) to find your **API Key** and **sharedSecret**.
    * If the **sharedSecret** field does not exist, that means that the **Authentication Type** is not **SSO**. Set it to **SSO** and the **sharedSecret** field should appear.

5. Run `heroku config:add HOOTSUITE_SHARED_SECRET="SHARED_SECRET_VALUE"` and `heroku config:add HOOTSUITE_API_KEY="API_KEY_VALUE"`, replacing **SHARED\_SECRET\_VALUE** and **API\_KEY\_VALUE** with the values found in Step 4.

6. Run `heroku run rake db:migrate`.

7. Create a new stream for the demo app.

8. Go to your App Stream and set the **&lt;iframe&gt;d URL** field to **http://APPNAME.herokuapp.com** that you saved from Step 2.

9. Install your app and add the new stream to a tab.

##Hosting the App on your Local Machine:

1. Make sure that the version of Ruby you are using is **1.9.3** by running `ruby --version`. Then, run `bundle install` inside the cloned repository location.

2. Run `rake db:migrate`.

3. Go to your app at [http://hootsuite.com/developers/my-apps](http://hootsuite.com/developers/my-apps) to find your **sharedSecret** and **API Key**.
    * If the **sharedSecret** field does not exist, that means that the **Authentication Type** is not **SSO**. Set it to **SSO** and the **sharedSecret** field should appear.

4. Edit the **config/initializers/dev_environment.rb** file to set the correct values for **HOOTSUITE\_SHARED\_SECRET** and **HOOTSUITE\_API\_KEY**.

5. Create a new stream for the demo app.

6. Go to your App Stream and set the **&lt;iframe&gt;d URL** field to **https://localhost:3000**.

7. To run your app in localhost with ssl follow these instructions http://www.railway.at/2013/02/12/using-ssl-in-your-local-rails-environment/

8. Install your app and add the new stream to a tab.
