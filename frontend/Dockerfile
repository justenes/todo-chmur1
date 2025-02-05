# Node.js kullan
FROM node:18-alpine

# Çalışma dizini
WORKDIR /app

# Bağımlılıkları yükle
COPY package.json package-lock.json ./
RUN npm install

# Proje dosyalarını kopyala
COPY . .

# React uygulamasını build et
RUN npm run build

# Nginx kullanarak sun
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html
RUN ls -lah /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
