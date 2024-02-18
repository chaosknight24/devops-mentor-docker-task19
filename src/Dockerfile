# Используем аргумент для указания версии Node.js
ARG NODE_VERSION

# Используем базовый образ node с указанной версией
FROM node:${NODE_VERSION}

# Устанавливаем рабочую директорию
WORKDIR /usr/src/app

# Копируем только файл package.json внутрь контейнера
COPY package.json .

# Запускаем команду npm install
RUN npm install

# Копируем все остальные файлы внутрь контейнера
COPY . .

# Устанавливаем пользователя как node
USER node

# Устанавливаем переменную среды SERVER_PORT со значением по умолчанию 3000
ENV SERVER_PORT=3000

# Устанавливаем переменную среды ENV_NAME со значением по умолчанию test
ENV ENV_NAME=test

# Запускаем сервис командой node server.js
CMD ["node", "server.js"]
