# Placement Cell

Placement Cell is a Full Stack application built using MongoDB, ExpressJS, NodeJs and ReactJS. This app maintains a record of students and interviews, which is exclusively maintained by the employee,

Employee can perform following actions:

- Employee can create a new account or login using an existing account.
- Employee can create, update and delete student entries.
- Employee can create, update and delete interviews.
- Employee can allocate students to interview or deallocate for an interview.
- Employee can view report containing all students and interview details and download it in .csv format

## Environment Variables

To run this project, you will need to add the following environment variables to your .env file on server root directory.

`MONGODB = "<your mongodb connection string>"`

`COOKIE_SECRET = "<Secret key to encrypt cookie>"`

Add `CORS_ORIGIN = "<your frontend base address>"` only if hoasting the frontend. To run on localhost no need to add `CORS_ORIGIN`.

For using job api generate `APP_KEY` and `APP_ID` by regestering on [https://developer.adzuna.com/](https://developer.adzuna.com/)

`APP_ID = "<Your app id>"`

`APP_KEY = "<Your app key>"`

## API Reference

API calls are validate using passport session cookie. Employee should be Loggedin to make api calls.

### Employee:

#### Create new Employee

```http
    POST /employee/create
```

#### Create employee session

```http
    POST /employee/create-session
```

#### Destroy employee session

```http
    GET /employee/destroy-session
```

### Students:

#### Get all Students

```http
  GET /student
```

#### Add new student details

```http
  POST /student/create
```

contains url-encoded-form-data containing all the students details.

#### Update student details

```http
  POST /student/update/${id}
```

| Parameter | Type     | Description                                          |
| :-------- | :------- | :--------------------------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch and update student |

contains url-encoded-form-data containing all the students details.

#### Delete student

```http
    DELETE /student/delete/${id}
```

| Parameter | Type     | Description                                          |
| :-------- | :------- | :--------------------------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch and delete student |

### Interview:

#### Get all interviews

```http
    GET /interview
```

#### Create a new Interview

```http
    POST /interview/create
```

#### Update interview details

```http
  POST /interview/update/${id}
```

| Parameter | Type     | Description                                            |
| :-------- | :------- | :----------------------------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch and update interview |

#### Delete interview details

```http
  DELETE /interview/delete/${id}
```

| Parameter | Type     | Description                                            |
| :-------- | :------- | :----------------------------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch and delete interview |

## Run Locally

Clone the project

```bash
  git clone https://github.com/RaghavendraPatel/Placement-Cell.git
```

Go to the project directory

```bash
  cd my-project
```

#### To start the server

Go to server directory

```bash
    cd server
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```

#### To start the client

On a seperate terminal

Go to client directory

```bash
    cd client
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```
