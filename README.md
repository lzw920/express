
## Repo Setup
Made copy of express-template-2022 app, cloned a copy of the repo onto our local Github (express)
Commands in Terminal:
  cd ~/Desktop/express
  npm install
  npm install nodemon -g

## Database Creation
We followed these the instructions to create a database: 
https://github.com/prof-rossetti/internet-technologies/blob/main/notes/databases/firestore/setup.md
https://github.com/prof-rossetti/internet-technologies/blob/main/notes/databases/firestore/setup.md

## Create .env file
Include an AlphaVantage API Key obtained from the professor ("OPEKNZB4Q8AUFTDY")
Added GOOGLE_CLIENT_ID ("539064605113-j6p16fue979gr5cst3mqs27jngsadu9k.apps.googleusercontent.com")
Added GOOGLE_CLIENT_SECRET ("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")
Added GA_TRACKER_ID ("G-X7Q22CWL0J")

## Checked Local Configuration
npm run start-dev
Visited http://localhost:3000/

## Deploying
Signed up for Heroku
Commands: 
  heroku login
  heroku express-app-jl
  heroku config:set ALPHAVANTAGE_API_KEY="OPEKNZB4Q8AUFTDY"
  heroku config:set GOOGLE_CLIENT_ID="539064605113-j6p16fue979gr5cst3mqs27jngsadu9k.apps.googleusercontent.com"
  heroku config:set GOOGLE_CLIENT_SECRET="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"
  heroku config:set GOOGLE_CALLBACK_URL=https://express-app-lj.herokuapp.com/auth/google/callback
  heroku config:set SESSION_SECRET="lj2022"
  heroku buildpacks:set heroku/nodejs
  heroku buildpacks:add https://github.com/s2t2/heroku-google-application-credentials-buildpack
  heroku config:set GOOGLE_CREDENTIALS="$(< google-credentials.json)"
  git push heroku main
