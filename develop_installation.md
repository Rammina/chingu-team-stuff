# Develop Branch Installation

**To ensure that you get the latest update from develop branch, follow the instructions below in order:**

- `git clone https://github.com/chingu-voyages/v30-bears-team-07.git` in your preferred directory
- after cloning, `git checkout develop`
- `npm install --save` and `npm install --save-dev` in / and /client

  <br>

- add .env files in both / and /client

  - / .env file should contain:
  - MONGO_URL=mongodb://dbBearsTeam:Bears07@cluster0-shard-00-00.hqsyu.mongodb.net:27017,cluster0-shard-00-01.hqsyu.mongodb.net:27017,cluster0-shard-00-02.hqsyu.mongodb.net:27017/go-on-db?ssl=true&replicaSet=atlas-13xswp-shard-0&authSource=admin&retryWrites=true&w=majority
  - JWT_SECRETKEY=1cantbearitanymore!
  - STRIPE_SECRETKEY=sk_test_51IxJ2SIxV9qIAWAEGmoQPjDZpnttRSuoDJskYjfiZlNUCfuqeftvxNtN85ucyWyz8GsNLpWKUuH0XIkt2miWL20T00Odi5yAF4
  - STRIPE_ENDPOINT_SECRET=whsec_Nc8lZAOCsS35Q5ELpEX82wsaVfTyoGEA


  <br>

  - /client .env file should contain:
  - REACT_APP_GOOGLE_AUTH_CLIENT_ID=269391989927-jtmcdqeo0h2l3t4q8gvpieamjkm8a4he.apps.googleusercontent.com

- (going to do this tomorrow)
- follow the instructions here for Stripe webhook installation (THERE IS ONE STEP THAT IS DIFFERENT):
  - https://stripe.com/docs/payments/checkout/fulfill-orders
  - (...under construction. ) 
