# Setup Steps
 * copy `.env` into the `app` folder
 * run `./bin/setup`. deal with any errors you get, see [here](#common-errors) for common errors
 * run `rails dev:prime`
 * run `rails db:seed`
 * run `yarn install`
 * run server with `rails server`


# common errors
### Yarn not found
install yarn with `npm install yarn --global`, might have to do this with sudo
### sprockets ~> version
run `bundle update` then precede with `bin/setup`
### node errors
error `The engine "node" is incompatible with this module. Expected version ">=12.0.0". Got "10.19.0"`, upgrade node
### postgresql
Make sure you database configuration matches with `config/database.yml`
### bad credentials
check your env file for support account creds. other wise check database for user names and try `password` as the pssword
