# Usa una imagen base de Node.js
FROM node:18

# Establece el directorio de trabajo en el contenedor
WORKDIR /app

# Copia primero los archivos de dependencias para aprovechar la caché de Docker
COPY package*.json ./

# Instala las dependencias del proyecto
RUN npm install

# Copia el schema de Prisma a la ubicación que Prisma espera por defecto
# La ruta de origen es relativa al contexto de build (la carpeta AuthService)
COPY src/config/schema.prisma ./prisma/schema.prisma

# Genera el cliente de Prisma. Ahora sí encontrará el schema.
RUN npx prisma generate

# Copia el resto de los archivos de tu aplicación
COPY . .

# Expone el puerto que usará tu aplicación
EXPOSE 3001

# El comando para iniciar tu aplicación
CMD ["npm", "start"]