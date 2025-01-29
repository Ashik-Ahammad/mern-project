FROM node:23.6.1 AS builder

WORKDIR /app

COPY package.json package-lock.json* ./

RUN npm install

COPY . .

RUN npm run build




FROM node:23.6.1 AS runner

WORKDIR /app

COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package.json ./
COPY --from=builder /app/dist ./dist

EXPOSE 5173

RUN useradd -m appuser
USER appuser

CMD ["npm", "run", "preview"]
