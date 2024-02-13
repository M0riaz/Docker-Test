# Используем базовый образ node:16-alpine
FROM node:16-alpine

# Задаем рабочую директорию внутри контейнера
WORKDIR /home/ilovedocker/app

# Копируем файлы package.json и package-lock.json из поддиректории packages в корень рабочей директории
COPY packages/package*.json ./

# Устанавливаем зависимости при помощи npm
RUN npm install

# Копируем исходники проекта из поддиректории src в корень рабочей директории
COPY ./src .

# Указываем используемый (экспозируемый) порт — 3032
EXPOSE 3032

# Изменяем команду запуска, чтобы в контейнере запускался файл main.js (в этом поможет команда node)
ENTRYPOINT ["node", "main.js"]
