FROM node:alpine
WORKDIR /app
COPY ./package ./
RUN npm install
COPY ./ ./
CMD [ "npm", "run", "build" ]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default
COPY --from=0 /app/build /usr/share/nginx/html
