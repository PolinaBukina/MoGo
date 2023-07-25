https://parceljs.org/getting-started/webapp/
https://nodejs.org/en/

1. Скачать и установить NodeJS
https://nodejs.org/en/

2. Проверить установлено ли nodeJS
node -v
npm -v

3. создаём папку
4. заходим в папку и в рабочую область этой папки
5. выполняем команду npm init -y
6. Проверяем наличие файла package.json
7. npm install --save-dev parcel
9. npm install --save-dev sass
10. npm install --save-dev @parcel/transformer-sass
11. В package.json удаляем всё внутри раздела scripts и удаляем раздел main
12. В раздел scripts записываем следующие строки

  "start": "parcel src/index.html --open",  
  "build": "parcel build ./src/index.html --public-url ./ --no-source-maps"

3. Переименовать ключ main -> source

  "source": "src/index.html"

  "start": "parcel serve --open", 

14. в папке проекта создать папку src
15. зайти в src
16. создать файл index.html
17. В терминале запустить команду npm run start
    Или команду npm run build
18. Внутри src создать папку sass
19. внутри папки sass создать файл style.scss
20. В файле index.html подключаем 
    <link rel="stylesheet" href="./sass/style.scss">
21. вызываем команду npm start
22. Оставить движок с помощью клавиш Ctrl + C
23. в репозитории git, возле скрытой папки .git (или возле файла package.json) создать файл .gitignore 
В файлике .gitignore прописываем пути, которые не должны попать в коммиты гит

node_modules

либо 

<название паки проекта>/node_modules


24. чтобы очищать dist нужно выполнить следующее

npm install rimraf --global

npm install rimraf --save-dev

И изменить скрипты следующим образом

25. А также изменить скрипты

"clean": "rimraf dist",
"build": "npm run clean && parcel build ./src/index.html --public-url ./ --no-source-maps"

Т.е. добавить скрипт на очистку и его в билд подсунуть