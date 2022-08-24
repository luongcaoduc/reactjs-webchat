FROM node:14.20.0-slim as builder
WORKDIR /app
COPY . .
RUN npm install 
RUN npm run build


FROM nginx:stable-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]