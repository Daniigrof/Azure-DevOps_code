FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV USER=Dani
ENV PASS=Dani3653

CMD ["npm", "start"]
