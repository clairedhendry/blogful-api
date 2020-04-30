# Express Boilerplate!

This is a boilerplate project used for starting new projects!

## Set up

Complete the following steps to start a new project (NEW-PROJECT-NAME):

1. Clone this repository to your local machine `git clone BOILERPLATE-URL NEW-PROJECTS-NAME`
2. `cd` into the cloned repository
3. Make a fresh start of the git history for this project with `rm -rf .git && git init`
4. Install the node dependencies `npm install`
5. Move the example Environment file to `.env` that will be ignored by git and read by the express server `mv example.env .env`
6. Edit the contents of the `package.json` to use NEW-PROJECT-NAME instead of `"name": "express-boilerplate",`

## Scripts

Start the application `npm start`

Start nodemon for the application `npm run dev`

Run the tests `npm test`

## Deploying

When your new project is ready for deployment, add a new Heroku application with `heroku create`. This will make a new git remote called "heroku" and you can then `npm run deploy` which will push to this remote's master branch.


## Migrations

Install driver (for Knex too) with npm i pg.
Set up folder "migrations"
Create files to start- 001.do.create<item>.sql
                     - 001.undo.create<item>.sql
In package.json, add to scripts - "migrate": "postgrator -- config postgrator-config.js"
postgrator-config.js should have
`require('dotenv').config()

module.exports = {
    "migrationsDirectory": "migrations",
    "driver": "pg",
    "connectionString": process.env.DB_URL
}`

npm run migrate -- <version of migration step>

** to seed a database use ** psql -U <username> -d <database name> -f <seed file name>