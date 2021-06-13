# MongoDB Atlas Setup

After creating an account, click `New Project` and follow the instructions.

<img src="https://res.cloudinary.com/rammina/image/upload/v1619599174/new-project_syllhh.png" alt="New Project" height="100"/>

After creating a project, click `Build a Cluster` and follow the instructions for free tier.

<img src="https://res.cloudinary.com/rammina/image/upload/v1619599175/build-cluster_zjgjz4.png" alt="Build a Cluster" height="200"/>

After creating a cluster, go to `COLLECTIONS` and then choose `Add My Own Data` to create a new database for the server to use.

<img src="https://res.cloudinary.com/rammina/image/upload/v1619599174/add-my-own-data_gwxwba.png" alt="Add My Own Data" height="200"/>

After creating a database, click `CONNECT`, follow the instructions, choose `Connect your application` as the connection method, and then retrieve the following information to put on the .env file:

- MONGO_URL

<password> is the password of the user that will connect to MongoDB Atlas.

<img src="https://res.cloudinary.com/rammina/image/upload/v1619599174/connect_auxyi2.png" alt="Connect"/>
