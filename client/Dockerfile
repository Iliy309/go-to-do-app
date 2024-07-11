# Используем Node.js официальный образ
FROM node:14

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем package.json и package-lock.json и устанавливаем зависимости
COPY package*.json ./
RUN npm install

# Копируем остальные файлы
COPY . .

# Экспонируем порт
EXPOSE 3000

# Запускаем приложение
CMD ["npm", "start"]
