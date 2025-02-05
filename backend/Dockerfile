# Node.js kullan
FROM node:18-alpine

# Çalışma dizini
WORKDIR /app

# Bağımlılıkları yükle
COPY package.json package-lock.json ./
RUN npm install

# Proje dosyalarını kopyala
COPY . .

# Sunucu portunu tanımla
EXPOSE 5000

# Uygulamayı başlat
CMD ["npm", "start"]
