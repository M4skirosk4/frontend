
FROM node:18 AS build

RUN npm install -g pnpm

WORKDIR /app

RUN npm install -g npm@8

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

RUN npm install -g serve

EXPOSE 3000

CMD ["serve", "-s", "dist", "-l", "3000"]
