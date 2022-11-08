# Setup Steps
 * clone the repo `git clone <repo name>`
 * copy `.env` into the repo folder
 * run `./bin/setup`. deal with any errors you get, see [here](#common-errors) for common errors
 * run `rails dev:prime`
 * run `rails db:seed`
 * run `yarn install`
 * run server with `rails server`
 * connect to `http://localhost:3000/admin` and login with user `admin@example.com` and password `password` to ensure its runnning

# running tests
tests are run view rails provided testing
 * `rails test` will run all tests
 * `rails test <path to specific test file>` will run a specific file
 * visit rails testing documentation for more, [link here](https://guides.rubyonrails.org/testing.html)

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


# Onboarding automation folder structure
```
.
├── app/
│   ├── admin/
│   │   └── provider.rb
│   └── models/
│       └── provider.rb
├── docker-postgres-multi-compose-file/
│   ├── docker-compose.yml
│   ├── create-multiple-postgresql-databases.sh
│   ├── dockerfile
│   ├── LICENSE
│   └── setup.md
└── test/
    └── models/
        └── provider_test.rb
```
