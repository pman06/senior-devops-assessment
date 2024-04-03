FROM node:20 as build
WORKDIR /app

COPY . .
RUN npm install && npm install -g @angular/cli

RUN ng build 

FROM nginx:alpine

COPY  --from=build /app/dist/frontend/browser /usr/share/nginx/html
EXPOSE 80
USER 5000
CMD ["nginx", "-g", "daemon off;"]