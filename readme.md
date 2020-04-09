# Тестовое. Фронт-енд разработчик. HTML/CSS/Webpack/Git #
## Описание для ревьюера ##

**Студенту была дана задача сверстать адаптивную страницу поисковика новостей, 
используя HTML/CSS и сборщик - Webpack. Проект ведется под Git. Сверстанная страница:**
* Должна корректно отображаться в последних версиях следующих браузеров: GC, FireFo , Safari.
* Страница должна корректно отображаться на мобильных, планшетных и десктопных устройствах разных OC.
* Не должна иметь горизонтальный скролл на разрешениях от 320p .
* Проект должен билдиться, инициализироваться и деплоится GitHub скриптами

*Прокомментируйте верстку, структуру репозитория и инфраструктуру проекта.*

## Комментарии необходимо оставлять под соответствующим критерием, а также зачесть/не зачесть критерий, отметив чекбокс. ##
*Укажите не только места ошибок, но и ее объяснение, а также способ исправления. А также места, где студент хорошо справился с заданием. 
Для выполненных критериев отметьте чекбокс*

*Вы можете включать ссылки на ресурсы, абстрактные примеры кода*

## Инфраструктура и Git
- [x] Вебпак настроен:
    - [x] собирает проект.
    - [x] деплоит сайт на GitHub Pages. 
    - [x] переменные окружения запрещены, проект собирается и запускается на любой OC после установки необходимых npm-зависимостей.
    - [ ] Локальный сервер установлен и настроен.
          Ошибка в команде вызова dev-бандла:    		  
      > "scripts": {
      > "build": "rimraf dist && webpack --mode production",
      > "dev": "~~NODE_ENV=development~~ webpack-dev-server --mode development --open --watch",
      > "pages": "gh-pages -d dist"
      > },    		  
    - [x] Хеши проставляются и настроено автоматическое обновление страницы (*hot reload*). 
    - [x] `webpack.config.js` не содержит ошибок и корректно оформлен.
          Серьёзных ошибок нет. Но есть небольшие помарки в оформлении:
      > const path = require('path')
      > const HtmlWebpackPlugin = require('html-webpack-plugin')
      > const WebpackMd5Hash = require('webpack-md5-hash')
      > const MiniCssExtractPlugin = require('mini-css-extract-plugin')
      > ~~const OptimizeCssAssetsPlugin = require('optimize-css-assets-webpack-plugin')~~
      > const webpack = require('webpack')
      
      При объявлении переменных в конце строки следует ставить знак ";"
      Переменная объявлена, но не использыется
      > module.exports = {...}
    
      В конце объявления условий module.exports также же следует ставить знак ";"
- [ ] Настроен Babel
- [ ] PostCSS установлен и настроен для минификации CSS-кода и простановки вендорных префиксов. 
- [ ] Плагины корректно устанавливаются.
- [ ] Устранена проблема с нижними подчеркиваниями при публикации на github.
- [ ] Продакшн-бандл должен деплоиться на Github Pages скриптом вебпака. (Все необходимые данные должны быть указаны)
- [ ] Работа с Git
  - [ ] `Package.json` содержит всю необходимую информацию
  - [ ] `.gitignore` содержит все необходимые каталоги и файлы
  - [ ] Gh-pages
- [ ] Исходники проекта хранятся в каталоге `src/`, итоговый билд - в каталоге `dist/`.
- [ ] Бандлы хранятся в отдельной директории каталога `dist/`
- [ ] У каждого установленного плагина зафиксирована версия.

## HTML и CSS
- [ ] Именование классов и структура файлов сделаны по БЭМ. Отсутствуют ошибки в БЭМ-нейминге сущностей.
- [ ] БЭМ файловая структура не содержит ошибок.
- [ ] Мета-элементы не содержат ошибок.
- [ ] Проект адаптирован под различные разрешения экрана. Горизонтальный скролл не должен возникать на разрешениях от 320 пикселей и больше. Скрывать полосу прокрутки свойством `overflow: hidden` нельзя.
- [ ] Отзывчивая вёрстка, которая корректно тянется на всех промежуточных разрешениях.
- [ ] Корректно работают ссылки на внешние ресурсы: ни одна ссылка не ведёт в пустоту или на якорь, внешние ссылки открываются в новой вкладке. 
- [ ] В коде используется семантическая разметка: применяются семантические теги, выбор элементов при вёрстке корректен (параграф должен быть параграфом, список — списком); структура DOM-дерева состоит не только из контейнеров div.
- [ ] Нету лишних DIV-оберток.
- [ ] Кнопки, инпуты и ссылки реализованы во всех состояниях 
- [ ] Элементы формы должны выделяться, когда на них установлен фокус.
- У формы должны быть:
    - [ ] заданы плейсхолдеры;
    - [ ] валидированы обязательные поля.
- [ ] Шрифты подключены через @font-face.
- [ ] Для каждого шрифта указаны альтернативные варианты из системных шрифтов.
- [ ] Для позиционирования элементов выбран верный подход, описанный корректным синтаксисом. 
- [ ] Для изображений задан атрибут alt с подходящий значением.
- [ ] Каркас макета реализован на Flex-layout или Grid-layout;
- [ ] Растровые и векторные изображения оптимизированы;
- [ ] Контентные и декоративные изображения выделены корректно
- [ ] Графика оптимизирована для мобильных и планшетных устройств


## Доп. Комментарии:
