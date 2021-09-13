# Stage1 : Build 

FROM node:14 AS development

WORKDIR /sophie/frontEnd/src

COPY package*.json ./

RUN npm install
RUN npm install -g @angular/cli 

COPY . . 

