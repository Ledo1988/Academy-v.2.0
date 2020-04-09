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
    
        *Ошибка в команде вызова dev-бандла:    		  
      >     "scripts": {       
	  >         "dev": "~~NODE_ENV=development~~ webpack-dev-server --mode development --open --watch",
      > 	   },    		  
    - [x] Хеши проставляются и настроено автоматическое обновление страницы (*hot reload*). 
    - [x] `webpack.config.js` не содержит ошибок и корректно оформлен.
          
      *Серьёзных ошибок нет. Но есть небольшие помарки в оформлении.
     
      При объявлении переменных в конце строки следует ставить знак ";"
        Переменная объявлена, но не используется
      >     const path = require('path')
      >     const HtmlWebpackPlugin = require('html-webpack-plugin')
      >     const WebpackMd5Hash = require('webpack-md5-hash')
      >     const MiniCssExtractPlugin = require('mini-css-extract-plugin')	  >
      >     //const OptimizeCssAssetsPlugin = require('optimize-css-assets-webpack-plugin')
	  >     const webpack = require('webpack')
      
      В конце объявления условий module.exports также же следует ставить знак ";"
      >     module.exports = {...}    
      
- [x] Настроен Babel
- [x] PostCSS установлен и настроен для минификации CSS-кода и простановки вендорных префиксов. 
- [x] Плагины корректно устанавливаются.
- [x] Устранена проблема с нижними подчеркиваниями при публикации на github.
      
  *Проблема не возникает, так как в ``/dist`` отстутсвуют файлы с нижними подчёркиваниями.
      Всё же желательно разместить в корне пустой файл ``.nojekyll``.
- [x] Продакшн-бандл должен деплоиться на Github Pages скриптом вебпака. (Все необходимые данные должны быть указаны)
- [x] Работа с Git
  - [x] `Package.json` содержит всю необходимую информацию
        
    *Для оптимизации дальнейшего использования package.json желательно не оставлять пустых полей
    >       "repository": {
    >             "type": "git",
    >             "url": ""
    >           },
    >
    >       "bugs": {
    >           "url": ""
    >       }
        
	Подробнее в спецификации https://docs.npmjs.com/files/package.json    
  - [ ] `.gitignore` содержит все необходимые каталоги и файлы
    
    *Необходимо включать в `.gitignore` логи, неиспользуемые системные файлы (например,``.DS_Store``), зависимости, которые подгружаются программами разработки (например, ``.idea``)
          Статья на тему: https://www.pluralsight.com/guides/how-to-use-gitignore-file
          Пример `.gitignore` https://gist.github.com/octocat/9257657
        
    При написании ``/папка/`` `.gitignore` будет искать папку относительно своего местоположения.
        Это может быть неэффективно при сложной структуре проекта. Поэтому лучше писать ``папка/`` 
        Подробнее в спецификации https://git-scm.com/docs/gitignore   
        
  - [x] Gh-pages
- [x] Исходники проекта хранятся в каталоге `src/`, итоговый билд - в каталоге `dist/`.
- [ ] Бандлы хранятся в отдельной директории каталога `dist/`
    
    *Бандлы лежат в родительском каталоге `dist/`, а не в отдельной директории
- [x] У каждого установленного плагина зафиксирована версия.

## HTML и CSS
- [ ] Именование классов и структура файлов сделаны по БЭМ. Отсутствуют ошибки в БЭМ-нейминге сущностей.
    
    *Отсуствует блок `"root"`, поэтому элемент `"root__section"` использовать нельзя.
    Лучше сменить нейминг и переименовать `"root__section"` в `"root"`.
    Элементы переминованного блока `"root"` необходимо связать  с ним дополнительными классами (например, `"root__header"`).
    >
		<div class="root__section">
		   <header class="header">
	
	Блок и элемент не связаны классом
	>
           <header class="header">
             <div class="menu">	 
    
    `"header__title-wrapper"` обёртка только для элемента `"header__title"`, необходимо переименовать, так как внутри `"header__title-wrapper"` содержатся и другие элементы.         
	>  
        <div class="header__title-wrapper">
                <h1 class="header__title">Что в мире творится?</h1>
                <h3 class="header__subtitle">Находите самые свежие статьи на любую тему
                  и сохраняйте в своём личном кабинете.     
    `"circle-preloader"` нейминг не связывает элемент с блоком
    >   
        <section class=preloader>
         <div class="preloader__message" id="preloader-searching">
           <i class="circle-preloader"></i>
           
    Блок и элемент не связаны классом
    >   
        <div class="results__news">
          <a href="#" class="card">           
    
    Неверный нейминг (одно нижнее подчёркивание вместо двух)
    >   
        <div class="card_image-wrapper">
    
    Неверный нейминг в блоке `card_wrapper` (одно нижнее подчёркивание вместо двух, взаимосвязь элементов) 
    >   
       <div class="card_wrapper">
           <p class="card_date">2 августа, 2019</p>
			...
		</div>
		
    У ссылок нет класса
    >   
        <ul class="footer__menu">
          <li class="footer__menu-item"><a href="./">      
    Неверный нейминг элементов относительно блока
    >   
        <p class="footer__links">
           <a href="#" class="footer__social-icon" target="_blank">        
- [ ] БЭМ файловая структура не содержит ошибок.
    
    *В блок не могут быть вложены другие блоки (блок `main`).
    
    Папка для модификатора `menu__logout-black` названа неверно
- [x] Мета-элементы не содержат ошибок.
    
    *Нежелательно ограничивать действия пользователя свойством `user-scalable=no`
    >   
        <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no">
- [ ] Проект адаптирован под различные разрешения экрана. Горизонтальный скролл не должен возникать на разрешениях от 320 пикселей и больше. Скрывать полосу прокрутки свойством `overflow: hidden` нельзя.

    *Появляется горизонтальный скролл на разрешении экрана ниже 1900px
- [x] Отзывчивая вёрстка, которая корректно тянется на всех промежуточных разрешениях.
      
     *Хорошее решение, блоки не заползают друг на друга. Сайтом удобно пользоваться.
- [ ] Корректно работают ссылки на внешние ресурсы: ни одна ссылка не ведёт в пустоту или на якорь, внешние ссылки открываются в новой вкладке.

    *Не работают ссылки на социальные сети:
    >   
        <p class="footer__links">
          <a href="#" class="footer__social-icon" target="_blank">
            <img src="./images/git.svg" alt="Logo">
          </a>
          <a href="#" class="footer__social-icon" target="_blank">
            <img src="./images/facebook.svg" alt="Logo">
          </a>
        </p> 
- [ ] В коде используется семантическая разметка: применяются семантические теги, выбор элементов при вёрстке корректен (параграф должен быть параграфом, список — списком); структура DOM-дерева состоит не только из контейнеров div.
    
     Для использования формы следует заменить тег `<div>` на `<form>` 
                 
    >   
        <div class="header__form">   
    `<section>` существует вне блока `<main>`. Класс указывается в "". 
    >   
        <section class=preloader> 
        ...
        <section class="about results__about">
    Не следует использовать теги заголовков (`<h4>`, `<h5>`) для системных ответов на запросы.
   
    >   
        <section class=preloader>
         <div class="preloader__message" id="preloader-searching">
           <i class="circle-preloader"></i>
           <h5 class="preloader__subtitle">Идет поиск новостей...</h5>
         </div>
         <div class="preloader__message preloader__hide" id="preloader-not-found">
           <img class="preloader__icon" src="./images/not-found.svg" alt="no">
           <h4 class="preloader__title">Ничего не найдено</h4>
           <h5 class="preloader__subtitle">К сожалению по вашему запросу ничего не найдено.</h5>
         </div>
       </section>    
    На странице отстуствует `<h1>`, поэтому использовать `<h3>` несемантично
    >   
        <main class="results">
            <h3 class="results__title">Результаты поиска</h3> 
    
    Связанные элементы для удоюства желательно поместить в одну обёртку
    >   
        <div class="card__icon"></div>
        <p class="card__warning">Войдите, чтобы сохранять статьи</p> 
    Текст из нескольких параграфов лучше оборачивать в `<div>` или `<article>`, а внутри разбивать на параграфы 
     >   
        <p class="card_text">It is a long  ...              
    Для кратких текстовых вставок (строчных элементов) желательно использовать `<span>` вместо `<p>`
    Пример:
    >   
        <p class="card_src">lipsum.com</p> 
    Отсутствует тип кнопки
    >   
        <button class="button results__button">Показать еще</button>
    
          
- [ ] Нет лишних DIV-оберток.
    
    Лишняя DIV-обертка.
    >   
        <section class="about results__about">
          <div>
- [ ] Кнопки, инпуты и ссылки реализованы во всех состояниях 
    
    *Не реализовано состояние focus.
    
    Hover назначен не для всех элементов (например, ссылки в `<footer>`)
- [ ] Элементы формы должны выделяться, когда на них установлен фокус.
- У формы должны быть:
    - [x] заданы плейсхолдеры;
    - [ ] валидированы обязательные поля.
- [x] Шрифты подключены через @font-face.
- [ ] Для каждого шрифта указаны альтернативные варианты из системных шрифтов.
- [ ] Для позиционирования элементов выбран верный подход, описанный корректным синтаксисом. 

    *Отступы между блоками лучше назначать блокам, а не их внутренним элементам:
    
    >  
        .header__title {
            ...
            margin: 80px 0 0;
            ...
        }
    
    Блокам `results`, `footer` следует задать общие отсупы слева и справа вместо указания отступов для каждого внутреннего элемента. 
    
    Блок `results__about` выпадает из ширины вёрстки страницы.   
- [ ] Для изображений задан атрибут alt с подходящий значением.
    
     *Атрибут задан, но значения некорректны
- [x] Каркас макета реализован на Flex-layout или Grid-layout;
- [x] Растровые и векторные изображения оптимизированы;
- [ ] Контентные и декоративные изображения выделены корректно
     
     *В данном случае изображение является частью контента страницы, необходимо поместить его в html-код
    >   
        <div class="card_image-wrapper">
                <div class="card_img"></div>
              </div>
- [ ] Графика оптимизирована для мобильных и планшетных устройств


## Доп. Комментарии:
