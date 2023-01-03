FROM node:12-alpine3.9

# Créer un répertoire de travail
WORKDIR /app

# Installer les dépendances
COPY package*.json ./
RUN npm install --production

# Copier le code de l'application
COPY src .

# Exposer le port sur lequel l'application écoute
EXPOSE 3000

CMD ["node", "src/index.js"]

