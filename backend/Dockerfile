FROM node:18-alpine AS base 

WORKDIR /app

COPY package*.json ./

# for development
FROM base as dev 

# install dependencies
RUN npm install

# copy source code
COPY . .

EXPOSE 3000

# start application
CMD npm run start:dev

# for production
FROM base as prod

ENV NODE_ENV production

RUN npm install

COPY . .

# create dist folder with the production build
RUN npm run build

# start server using production build
CMD node dist/main.js