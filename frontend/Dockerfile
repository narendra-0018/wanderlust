# stage 1

FROM node:21 AS frontend-builder

WORKDIR /app

# copy the json file 

COPY package*.json ./

RUN npm install

COPY . .

# stage 2

FROM node:21-slim

WORKDIR /app

COPY --from=frontend-builder /app .

# copy the environmental file

COPY .env.sample .env.local

# expose the port 

EXPOSE 5173

# to run the command on the host 

CMD ["npm", "run", "dev", "--", "--host"]
