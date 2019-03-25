FROM node:latest

RUN mkdir /usr/src/app
WORKDIR /usr/src/app

ENV PATH /usr/src/app/node_module/.bin:$PATH

COPY package*.json ./
RUN npm install react-script@latest -g --silent
RUN npm install --silent

COPY . .

EXPOSE 3000
CMD ["npm", "start"]