# Auction Point

Auction Point is a website where users can buy and sell items. My aim with this Full Stack project was the design and development of an online auction platform, similar to eBay. The implementation follows a REST-api architecture and some of the key features are:

- **Secure Authorisation and Authentication**
- **Role-based Access Control**
- **Mail Client within the Application** 
- **Recommendations using Matrix Factorisation**

## Requirements & Setup
### Back-end

1. create directory api/config/config.json

```js
{
  "development": {
    "username": "root",
    "password": null,
    "database": "auctionDB",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```

2. setup your local mysql

4. `npm install`

5. To connect sequelize to the database, run the command: `sequelize init`

6. The transactions are encrypted through the SSL/TLS protocol. To create the certificate locally you can use `mkcert` and then add the path in:

```js
const sslServer = https.createServer({
    key: fs.readFileSync('/yourpath/key.pem'),
    cert: fs.readFileSync('/yourpath/cert.pem')
}, app);
```
- When the server starts with a "clean" database, the tables are automatically created based on the object-oriented models defined in [models](api/models/).
- Also, a user with the administrator role is automatically created with the username: admin and initial password: 1234, which can be changed.
- Nodemon is also set up, so that the server automatically restarts every time the code of back-end is changed, while the server is running.

To start up the server simply run in the [api](api/) directory: 

```
npm start
```

### Front-end
For the front-end all the necessary dependencies are defined in the `package.json` file. To install them simply run in the [front](front/) directory: `npm install`

To start up the front-end in the [front](front/) directory run: 

```
npm start
```
