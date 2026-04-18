FROM node:25-alpine

WORKDIR /app

# Primero solo copiamos las dependencias, para crear capas de Docker mas eficientes
COPY package*.json ./

# Instalamos solo las dependencias de produccion. Tambien podriamos haberlo hecho con --only=production
RUN npm install --omit=dev

# Copiamos el resto del codigo (server.js en este caso)
COPY . .

# Exponemos el puerto 3001
EXPOSE 3001

# Arrancamos el backend
CMD ["node", "server.js"]