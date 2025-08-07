# Overview

Quickpoint corporate website based off of Shade Professional Theme done using React, Vite and Nunjucks.

# Installing Build Tools

- Install Node 22 using following commands:
```bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 22

# Verify the Node.js version:
node -v # Should print "v22.14.0".
nvm current # Should print "v22.14.0".

# Verify npm version:
npm -v # Should print "10.9.2".
```

# Setting Up React + Nunjucks from Scratch (Optional)

This is for future projects using same templating engine. Ignore this section if you are wanting to start with local development.

- Create boilerplate project.
```bash
npm create vite@latest react-nunjucks-app -- --template react
```
- Install dependencies.
```bash
npm install
```
- Install nunjucks.
```bash
npm install nunjucks
```

# Setting Up Local Dev Env

- Clone this git repo using the following command:
```bash
git@github.com:moraza/quickpoint-web.git
```
- Enter the cloned directory and install dependencies:
```bash
cd quickpoint-web
npm install
```
- Run Dev environment on local machine. Any updates done to code will be hot-swapped at runtime and will be visible on local server. If major code changes are done, local server will need to be restarted by killing the currently running server using `CTRL+C` and re-running `npm run dev`.
```bash
npm run dev
```
- Access local dev environment by going to http://localhost:5173

# Buiding for Prod Env

- Generate build artifact.
```bash
npm run build
```
- Generate docker image.
```bash
docker build -t quickpoint-web:latest .
```

# Run Prod Env
- Run docker image.
```bash
docker run -d -p 80:80 quickpoint-web:latest
```