# ---------- Etapa 1: Instalación de dependencias ----------
FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install --production

COPY . .

# ---------- Etapa 2: Imagen de ejecución ----------
FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app .

EXPOSE 3001

CMD ["node", "server.js"]
