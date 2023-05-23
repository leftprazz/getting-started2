# syntax=docker/dockerfile:1

FROM node:18-alpine
WORKDIR /app

# Install nodemon globally
RUN yarn global add nodemon

# Copy package.json and yarn.lock separately
# This allows Docker to cache the dependencies installation step
COPY package.json yarn.lock ./

# Install all dependencies
RUN yarn install

# Copy the rest of the application code
COPY . .

# Set the command to run nodemon
CMD ["node", "./src/index.js"]
