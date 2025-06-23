FROM node:18
WORKDIR /app

# Copia los archivos de configuración
COPY package*.json ./
RUN npm install

# Copia todos los archivos del proyecto
COPY . .

# Copia el archivo .env (si tienes uno) para las variables de entorno
COPY .env ./

# Copia el archivo prisma.schema a la ruta esperada dentro del contenedor
COPY ./Backend/AutenticacionySeguridad/AuthService/src/config/schema.prisma ./prisma/schema.prisma

# Genera el cliente Prisma
RUN npx prisma generate

EXPOSE 3001
CMD ["npm", "start"]
