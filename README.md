# Commits.to
### a.k.a. [The I-Will System](https://github.com/beeminder/iwill/)

View the [Functional Spec](https://github.com/beeminder/iwill/wiki/).


## Development Setup

This guide assumes you have `postgresql` running on `localhost:5432`

#### Install Dependencies

Install node packages with `npm install`


#### Hosts File

Add the following line to `etc/hosts` (with whatever subdomains you want to be available):

```sh
127.0.0.1	commits-to.js www.commits-to.js chris.commits-to.js dreev.commits-to.js
```

#### Create `.env` File

Save the file in the root of the project directory

```sh
ENV_NAME=<yourname>-dev
PORT=8080
APP_DOMAIN=commits-to.js:8080
DATABASE_URL=postgres://iwill:iwill@localhost:5432/commitsto

# Optional
MAILGUN_KEY=
MAILGUN_DOMAIN=
MAILGUN_TO=
MAILGUN_FROM=
```

#### Run the application

Start the development server with `npm run start:dev`


#### Seed the database

Browse (or send a GET request) to `http://commits-to.js:8080/reset`, which drops all tables and inserts seed data from the `data/` folder


## Deployment

Merges to the `master` branch will be automatically deployed to our Heroku staging tier at `http://commitsto.review`


#### Pull Request Review App

Heroku will create a review app for a new pull request, available at `http://commitsto-dev.review`
