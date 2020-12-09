# Use NodeJS base image
FROM node:13

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy app source
COPY ./www ./

# Get env vars
## I KNOW I SHOULD NOT DO IT THAT WAY BUT DO NOT KNOW HOW TO
ENV POSTGRES_USERNAME=udagramdomdev
ENV POSTGRES_PASSWORD=password
ENV POSTGRES_HOST=udagramdomdev.cxtuqsdx4e6a.us-east-2.rds.amazonaws.com
ENV POSTGRES_DB=udagramdomdev
ENV AWS_BUCKET=udagram-baibars-dev
ENV AWS_REGION=us-east-2
ENV AWS_PROFILE=default
ENV JWT_SECRET=helloworld
ENV URL=http://localhost:8100 

# Bind the port that the image will run on
EXPOSE 8080

# Define the Docker image's behavior at runtime
CMD ["node", "server.js"]