FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY . .

FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app /app

EXPOSE 3001

CMD ["npm","start"] 