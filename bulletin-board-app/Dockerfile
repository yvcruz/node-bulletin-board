FROM node:6.11.5

WORKDIR /usr/src/app
COPY package.json .
RUN npm config set proxy http://172.17.0.1:3128
RUN npm config set https-proxy http://172.17.0.1:3128
RUN npm install

EXPOSE 8080
CMD [ "npm", "start" ]

COPY . .

HEALTHCHECK --interval=5s \
  CMD curl --fail http://localhost:8080 || exit 1  
