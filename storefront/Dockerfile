FROM node:18.15.0

EXPOSE 8000

WORKDIR /app/storefront

COPY package*.json ./

RUN rm -rf node_modules

RUN apt-get update

RUN npm install -g npm@latest

RUN npm install -g next-cli

COPY . .

RUN npm install

RUN npm run build &> /dev/null

COPY bootstrap.sh .

ENTRYPOINT ["./bootstrap.sh", "develop"]