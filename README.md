# Flaskapp

This project is meant to serve as template for new projects. To create a new app from `flaskapp` first clone the repository and remove the `.git` directory:

```bash
$ git clone git@github.com:muicss/flaskapp.git
$ rm -rf flaskapp/.git
```

Then, do a search-replace on the string `flaskapp`:

```bash
$ find flaskapp -type f | xargs sed -i'' -e 's/flaskapp/myapp/g'
$ find flaskapp -type f | xargs sed -i'' -e 's/Flaskapp/Myapp/g'
$ mv flaskapp myapp
$ mv myapp/flaskapp myapp/myapp
```

Now you have your own flask seed project.

## Config Variables

flaskapp can be configured using the following environment variables:

Name          | Description                 | Default | Required
------------- | --------------------------- | ------- | -------
DEBUG         | Flask debug variable        | "False" | no
SECRET_KEY    | Flask cookie encryption key | null    | yes
MAIL_PORT     | SMTP port                   | null    | yes
MAIL_SERVER   | SMTP hostname               | null    | yes
MAIL_USERNAME | SMTP username               | null    | yes
MAIL_PASSWORD | SMTP password               | null    | yes

## Quickstart

These instructions assume you've already checked out the repository and you're using Python/Node virtual environments.

1. Install dependencies

    ```bash
    (flaskapp-env)$ cd /path/to/flaskapp
    (flaskapp-env)$ pip install -r requirements.txt
    ```

1. Setup database

   ```bash
   (flaskapp-env)$ python scripts/create_db.py
   ```

1. Environment variables

   In order to configure flaskapp it is recommended that you create an environment file with the required variables listed above. To add the variables to your environment you can source the file as part of your normal workflow:

   ```bash
   (flaskapp-env)$ source /path/to/env-vars.sh
   ```

1. Run unittests

    ```bash
    (flaskapp-env)$ nosetests
    ```

1. Run development server

   ```bash
   (flaskapp-env)$ python wsgi.py
   ```

   View at http://127.0.0.1:5000

1. Frontend build scripts

   Install node dependencies:

   ```bash
   (flaskapp-node-env)$ cd /path/to/flaskapp/static-src
   (flaskapp-node-env)$ npm install
   ```

   Run gulp:

   ```bash
   (flaskapp-node-env)$ ./node_modules/.bin/gulp build
   ```

## Unittests ##

To run all tests:

```bash
(flaskapp-env)$ nosetests
```

To run an individual test:

```bash
(flaskapp-env)$ nosetests tests/views/test_content.py
```

## Development ##

Dependencies:

 - nodejs
 - npm

1. Install nodejs dependencies

   ```bash
   $ cd flaskapp/static-src
   $ npm install
   ```

1. Run frontend build scripts

   ```bash
   $ ./node_modules/.bin/gulp build
   ```
