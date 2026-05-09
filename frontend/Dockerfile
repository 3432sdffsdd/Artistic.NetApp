FROM node:22-alpine as builder

WORKDIR /app

COPY package*.json .

RUN npm install --legacy-peer-deps

COPY . .

RUN npm run build --prod

FROM nginx:alpine

COPY --from=builder /app/dist/angular-conduit/browser   /usr/share/nginx/html/

EXPOSE 80
