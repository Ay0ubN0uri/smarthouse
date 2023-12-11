FROM node:18-alpine AS builder

WORKDIR /front

COPY . .

RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=builder /front/dist/smart-home /usr/share/nginx/html
