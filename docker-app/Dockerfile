FROM node:18

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./

RUN npm install
RUN npm install --save-dev @types/react @types/react-native

COPY . .

# Installer le tunnel (ngrok) pour éviter les prompts
RUN npm install -g @expo/ngrok

# Installer la CLI Expo dans le projet
RUN npx expo install

# Exposer les ports utiles à Expo
EXPOSE 8081
EXPOSE 19000
EXPOSE 19001
EXPOSE 19002

# Démarrer le projet avec tunnel
CMD ["npx", "expo", "start", "--tunnel"]
