# stage 1
FROM node:21 AS backend-builder

WORKDIR /app

COPY . .

# run the node instal command
RUN npm i


# stage 2
FROM node:21-slim

WORKDIR /app

COPY --from=backend-builder /app .

# copy the environment file

COPY .env.sample .env

# expose the port

EXPOSE 5000

CMD ["npm", "start"]
