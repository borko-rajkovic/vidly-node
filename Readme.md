[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <h1 align="center">Vidly node</h1>

  <p align="center">
    Backend for video rental store built with NodeJS, Express and MongoDB
    <br />
    <a href="https://github.com/borko-rajkovic/vidly-node/issues">Report Bug</a>
    ·
    <a href="https://github.com/borko-rajkovic/vidly-node/issues">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [About the Project](#about-the-project)
  - [Built With](#built-with)
- [Demo](#demo)
- [Getting Started](#getting-started)
  - [Prerequisites](#Prerequisites)
  - [First run](#first-run)
  - [TDD](#tdd)
- [Routes](#routes)
  - [Users](#users)
  - [Auth](#auth)
  - [Genres](#genres)
  - [Customers](#customers)
  - [Movies](#movies)
  - [Rentals](#rentals)
  - [Returns](#returns)
- [Contributing](#contributing)
- [Contact](#contact)

<!-- ABOUT THE PROJECT -->

## About The Project

The Vidly is a video rental store backend built with NodeJS, Express and MongoDB. Developed in TDD, using Jest. For Authentication, JWT and bcrypt are used. Application is hosted to Heroku.

### Built With

- Node.js
- Express.js
- MongoDB
- Jest

<!-- GETTING STARTED -->

## Getting Started

### Prerequisites

These are prerequisites that must be set up prior to running this project:

- Node version 10.16.0 or greater
- MongoDB installed on localhost
- Python (optional, for building bcrypt package)

### First run

To get a local copy of the project up and running, follow these simple steps:

1. Clone the repo

```sh
git clone https://github.com/borko-rajkovic/vidly-node
```

2. Install Node packages

```sh
npm install
```

3. Set up config variables.

    In **config** folder you will find 3 files. There is **default.json** configuration for running **npm start** script, **test.json** configuration for running **npm run test** script and **custom-environment-variables.json** which holds mapping between environment variables and actual variable names in config.
    
    Because there is no value defined in **default.json** for **jwtPrivateKey**, you can either:

    - set up **jwtPrivateKey** in **default.json**, or
    - set up environment variable **vidly_jwtPrivateKey**

    **jwtPrivateKey** will be used for creating json web tokens.

    You can find more on JWT [here](https://jwt.io)

    Similarly, if you want to change connection to your database, you can either:

    - set up **db** in **default.json**, or
    - set up environment variable **vidly_db**

4. Move to project folder & start node server

```sh
npm start
```

### TDD

Since this project was build using TDD (Test Driven Development), it should be started in test watch mode, so whenever you do some changes, it goes through tests and check if everything is fine.

To run in test mode, do simply:

```sh
npm run test
```

This will simply run Jest in watch mode.

## Demo

Application is hosted on heroku.

You can try it by yourself. Following cURL command will try to login with email and password and get back JWT if correct. As this is test database, feel free to run http requests.

``` sh
curl -X POST   https://borko-vidly-node.herokuapp.com/api/auth   -H 'Accept: */*'   -H 'Cache-Control: no-cache'   -H 'Connection: keep-alive'   -H 'Content-Type: application/json'   -H 'Host: borko-vidly-node.herokuapp.com'   -H 'accept-encoding: gzip, deflate'   -H 'cache-control: no-cache'   -H 'content-length: 62'   -d '{
    "email": "borko@test.com",
    "password": "p@ssw0rd!"
}'
```

## Routes

Here is the list of all the routes:

### Users

	GET /api/users/me
	POST /api/users/

### Auth

	POST /api/auth/

### Genres

	GET /api/genres/
	POST /api/genres/
	PUT /api/genres/:id
	DELETE /api/genres/:id
	GET /api/genres/:id

### Customers

	GET /api/customers/
	POST /api/customers/
	PUT /api/customers/:id
	DELETE /api/customers/:id
	GET /api/customers/:id

### Movies

	GET /api/movies/
	POST /api/movies/
	PUT /api/movies/:id
	DELETE /api/movies/:id
	GET /api/movies/:id

### Rentals

	GET /api/rentals/
	POST /api/rentals/
	GET /api/rentals/:id

### Returns

	POST /api/returns/


<!-- CONTRIBUTING -->

## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- CONTACT -->

## Contact

Borko Rajkovic - [LinkedIn](https://linkedin.com/in/borko-rajkovic) - rajkovicborko@gmail.com

<!-- MARKDOWN LINKS & IMAGES -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/borko-rajkovic/
