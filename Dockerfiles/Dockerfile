FROM node:latest
WORKDIR /usr/src/swati_app
COPY package*.json ./

# Installing the packages while the image is building
RUN npm install

# Note: files & folders inside .dockerignore will not be copied.
COPY . .

# The app binds to port 3000, so exposing port 3000 to be used by the docker network
EXPOSE 3000

# Runtime command to be executed when the container is launched
CMD ["npm", "start"]