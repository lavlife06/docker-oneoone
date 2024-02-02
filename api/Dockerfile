FROM node:16.14.0-slim

# Install deps
RUN apt-get install -y apt-transport-https
RUN apt-get -y update
RUN apt-get -y install git curl unzip build-essential

WORKDIR /app

#this is done to cache this layer and not run npm install every build of image
COPY ./package*.json ./
#COPY ./.npmrc ./
#COPY ./.npmrc /root

RUN npm install

COPY ./ ./
RUN rm -f .env*

EXPOSE 4004

CMD ["node", "app"]
