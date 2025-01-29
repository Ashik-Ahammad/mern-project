# Build stage
FROM node:23.6.1 AS builder

WORKDIR /app

COPY package.json ./

RUN npm install --only=production

COPY . .


# Run stage
FROM node:23.6.1 AS runner

WORKDIR /app

COPY --from=builder /app ./

EXPOSE 5050

CMD ["npm", "start"]





