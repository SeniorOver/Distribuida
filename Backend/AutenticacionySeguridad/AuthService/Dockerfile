FROM node:18
WORKDIR /app

COPY package*.json ./
RUN npm install

# Copia el resto de archivos, incluyendo schema.prisma
COPY . .

# Ahora sí generar el cliente Prisma
RUN npx prisma generate

EXPOSE 3001
CMD ["npm", "start"]
