
# Deploy-React-App-In-Docker

This ts a demo project to Deploy a React Project in Docker And Upload in docker Hub


## First Create React App

To create this project run

```bash
  npx create-react-app my-app
```

![Screenshot from 2024-02-02 11-15-59](https://github.com/MdShafiqulSaymon/Portfolio/assets/68004638/c99296db-64fd-4001-a5fb-35feb6635b70)
```bash
  cd my-app
```
```bash
  npm start
```
After start the app Look like:
![Screenshot from 2024-02-02 11-46-15](https://github.com/MdShafiqulSaymon/Portfolio/assets/68004638/01ec5f5a-2008-4d43-b4f4-6a6395c1d450)


## Second of All We Deploy in Docker

First of all create Dockerfile in root directory like in (my-app) folder


## Steps

- Create Dockerfile file name will be (Dockerfile)
- Copy the Given Bash code and paste in Dockerfile
- To Build the Image Run Given Command
- To start The Image Run Given Command


```bash
# Use an official Node runtime as a parent image
FROM node:latest

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the entire application to the working directory
COPY . .

# Expose port 3000 to the outside world
EXPOSE 3000

# Build the React app for production
RUN npm run build

# Set environment variables
ENV NODE_ENV=production

# Run the application
CMD ["npm", "start"]

```
Build The Image
```bash
  docker build -t my-react-app-image .
```

Run The Image
```bash
  docker run -p 5000:3000 my-react-app-image
```
You can now view my-app in the browser.

  Local:            http://localhost:5000
  On Your Network:  http://172.17.0.2:5000


Running On Docker:

![Screenshot from 2024-02-02 16-42-59](https://github.com/DevOps-With-Poridhi-io/Deploy-React-App-In-Docker/assets/68004638/5d4b5942-7233-4efc-8c06-b99e87172780)

