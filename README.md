# ifttt
Fake a wordpress application and forward IFTTT request to an external application

1. Sign up for IFTTT
  - http://ifttt.com/join

2. Download reddit_to_twitter application
  - git clone https://github.com/zgallup/reddit_to_twitter.git
  - cd reddit_to_twitter
  - heroku create

3. Add app to twitter profile
  - https://dev.twitter.com/apps
  - Create New App
    - name: reddit_to_twitter
    - desc: whatever you want
    - website: heroku_URL_for_reddit_to_twitter_application i.e. https://pacific-eyrie-9417.herokuapp.com/
    - callback url: leave blank
  - Save application
  - Select application
    - Change Permissons to Read and Write
    - Update reddit_to_twitter application with your twitter secret keys

4.  Push reddit_to_twitter to Heroku
  - git add .
  - git commit -m 'adding my twitter keys'
  - git push heroku master
  
5. Download ifttt application
  - git clone https://github.com/zgallup/ifttt.git
  - cd ifttt
  - change url to the heroku url for reddit_to_twitter_application in app.js Line #27
  - heroku create
  - git push heroku master

6. Open IFTTT profile
  - Go to Channels
  - select WordPress
  - Edit channel
    - Blog URL: heroku_URL_for_ifttt_application
    - username: your_first_name
    - password: whatever_you_want (this isn't important it just needs to not be blank)
  - Activate Channel

7. Add IFTTT Recipe
  - Go to My Recipes
  - Create a Recipe
  - Choose Reddit
    - Any new post in a subreddit
    - ruby
  - Click 'That'
    - select WordPress
    - Create a post
      - Title: whatever_you_want # THIS IS WHAT YOU WILL TWEET
      - Body: whatever_you_want
      - Categories: ifttt_application_heroku_url
    - Create Recipe

8. Manually Trigger IFTTT 
  - Select "check" in your My Recipes Page of IFTTT