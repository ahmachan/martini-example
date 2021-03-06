# Martini-Example


## System dependencies

### Installing Go

* Install Go `brew install go`
* Setup your `Go` environment:

  ```
  export GOPATH=<Your Go working directory here>
  export PATH="$PATH:$GOPATH/bin"
  ```

### Installing Postgres

* Install Postgres `brew install postgres`

  Alternatively, use [postgres app](http://postgresapp.com).

## Configuration

* Create the database `createdb example_app_dev`

* Populate it using the example `db/seeds.sql` file:
  `psql -d example_app_dev < db/seeds.sql`

* Create `.env` file:
  ```
  DATABASE_URL="dbname=example_app_dev sslmode=disable"
  API_USERNAME=<username>
  API_PASSWORD=<password>
  ```
  See [lib/pq](http://godoc.org/github.com/lib/pq) docs
  to see more details about connection parameters

* Run `go get` to install app dependencies

* Run app `go run main.go`

## Tests

None :cry:

## Deployment

Deployment instructions for heroku.

### Setup

* Make sure to have the [heroku toolbelt](https://toolbelt.heroku.com/)
  installed.

* Then run:
  ```bash
  heroku create <app-name> -b https://github.com/kr/heroku-buildpack-go.git
  ```

* Add the heroku git repository to your git remotes

* Install `Godep` to manage app dependencies by running:
  `go get github.com/tools/godep`

### Before pushing

* Every time that you add a new a dependency, make sure run `godep save`
  and add changed files inside `Godeps` directory.

### Release

* `git push <heroku-remote>` or `git push <heroku-remote> <feature-branch>:master`


