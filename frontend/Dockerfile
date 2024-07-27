FROM node:22-alpine

# set working dir
WORKDIR /app

# copy package.json and package-lock.json
COPY package*.json ./

RUN npm install

# copy the rest of the file
COPY . .

EXPOSE 5173

CMD npm run dev