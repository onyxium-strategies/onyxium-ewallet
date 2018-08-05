# Ewallet
This wallet serves as a local ledger for the fake funds of users.

# Getting started
`docker-compose up`  
`docker exec -it ewallet env MIX_ENV=prod mix do ecto.create, ecto.migrate, seed`

A master account will be generate and the following data needs to be copied to a .env file in the strategy-worker service:  

* User ID  
* Email  
* Password  
* Access Key  
* Secret Key  


