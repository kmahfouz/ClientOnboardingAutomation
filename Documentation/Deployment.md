# Server Needed
The only server needed is the ruby on rails server, the database is generated through docker, but only rails is needed server-wise
# Necesary Files
You will need to create an .env file with the necessary code and also the docker compose file, both just in the base level of the program
# Start/Stop System
To start it just cd into the project and run docker compose up to start up the database
Then open a new command prompt, cd into the directory, and run rails s to start the rails server
# Troubleshoot
Make sure database is populated and that you have ran db:seed
# Source Errors
No errors are logged, all are just displayed in the command prompt
# Critical Pieces
Database can sometimes clear itself with seemingly no reason
Timezone table that needs to be populated for testing
# API keys
fetch refresh token from intuit and insert it into the intuitaccount object <br>
fetch a api key from docusign and insert it into the docusignaccount object <br>
for each table (docusign_accounts, intuit_accounts) should only have 1 object <br>
