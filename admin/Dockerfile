FROM node:18.15.0

EXPOSE 7000

WORKDIR /app/admin

COPY package*.json ./

RUN rm -rf node_modules

RUN apt-get update

RUN npm install -g npm@latest

COPY . .

RUN npm install --force

RUN npm run build &> /dev/null

COPY bootstrap.sh .

ENTRYPOINT ["./bootstrap.sh", "start"]