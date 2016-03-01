# imas765probot

## About

This is the code that runs several of my Twitter bots, located at the following locations:

https://twitter.com/makomakorin_bot
https://twitter.com/harurunbot
https://twitter.com/yukipyon_bot
https://twitter.com/yayoicchi_bot
https://twitter.com/amimami_bot
https://twitter.com/ohimechin_bot

imas765probot runs on Python 3 and uses a modified version of the tweepy library to interact with Twitter. The script is hosted on Heroku and tweets every hour on the dot. In addition, the script checks for new followers every 20 minutes and will attempt to follow back new followers.

File assets are stored on Amazon S3 and are downloaded to the local filesystem at the time of tweeting. The Boto 3 API is used to access and interact with Amazon Web Services.

I used herokupostgres to store file queues instead of keeping the queues in memory. This is done because Heroku worker dynos are cycled every 24 hours. Using a persistent database allows the queues to be preserved in between cycles.