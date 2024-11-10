FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

ENV REACT_APP_MACHINE=ec2-44-204-17-137.compute-1.amazonaws.com

CMD [ "npm", "start" ]
