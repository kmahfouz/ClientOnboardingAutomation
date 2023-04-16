# index
 * [Setup](#setup-steps)
 * [running tests](#running-tests)
 * [common errors](#common-errors)
 * [Replicating via Docker](#Replicating-via-Docker)
 * [structure of changed files/folders](#Onboarding-automation-folder-structure)

# Setup Steps
 * clone the repo `git clone <repo name>`
 * install rails
 * copy `.env` into the repo folder (message team member to get env)
 * run `./bin/setup`. deal with any errors you get, see [here](#common-errors) for common errors
 * run `yarn install`
 * run server with `rails server`
 * connect to `http://localhost:3000/admin` and login with user `admin@example.com` and password `password` to ensure its runnning
### populating DB
if running setup doesnt populate the db run this
 * run `rails dev:prime`
 * run `rails db:seed`
# running tests
tests are run view rails provided testing
 * `rails test` will run all tests
 * `rails test <path to specific test file>` will run a specific file
 * visit rails testing documentation for more, [link here](https://guides.rubyonrails.org/testing.html)
 * to run coverage report, run rspec and it will generate the report as a file named index.html in the coverage folder

# Quickbooks
For Quickbooks functionality the developer needs to make an Intuit developer account,[link here](https://developer.intuit.com/app/developer/homepage)
* When accepting the authorization code you will be given a Realm ID
* Add the field "INTUIT_REALM_ID" to env file and past the Realm ID
* You will also need to generate and add a refresh token to the database 'intuit_accounts' column

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

# Replicating via Docker

 * navigate into `docker-posgress-multi-compose-file`
 * run docker command `docker build --tag=multidb_postgres .` to build the docker file into an image named `multidb_postgres`
 * run `docker-compose up` to start the containers 

# Onboarding automation folder structure
```
.
├── app/
│   ├── admin/
│   │   └── provider.rb
│   ├── models/
│   |    └── provider.rb
|   ├── controllers
|       └── onboarding_tokens_invitations_controller.rb
|
├── lib/
│     └── onboarding_automation_helper_functions
│       ├── automatic_quickbooks
│       │   ├── CustomerFactory.rb
│       │   ├── InvoiceFactory.rb
│       │   ├── QuickBooksAutomaton.rb
│       │   └── TokenHandler.rb
│       └── providers_functions.rb
├── docker-postgres-multi-compose-file/
│   ├── docker-compose.yml
│   ├── create-multiple-postgresql-databases.sh
│   ├── dockerfile
│   ├── LICENSE
│   └── setup.md
└── test/
    ├── helpers
    ├── integration
    │   └── onboarding_tokens_test.rb
    ├── lib
    │   └── automatic-quickbooks
    │       ├── customer_factory_test.rb
    │       ├── invoice_factory_test.rb
    │       └── token_handler_test.rb
    ├── mailers
    ├── models
    │   └── onboardin_tokens_test.rb
    ├── system
    └── test_helper.rb

```

# Linting

* run 'gem install rubocop'
* run 'rubocop [directory/file name] [different directory/file (optional)] [different directory/file (optional)]' etc...
