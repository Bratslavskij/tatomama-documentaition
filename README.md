# Документація ТатоМама <img src="./images/tatomama.svg" width="25" height="25" alt="logo tatomama">

Авторські права © | 2016 - 2022 | **ТатоМама** | Україна 🇺🇦 | Всі права захищені

## Панель навігації

[Browser Sync](-browser-sync)
<img src="./images/browser-sync.png" width="15" height="15" alt="BrowserSync">

## Browser Sync

Browser Sync — це програма яка автоматично оновляє веб-сторінку, коли її редагують.
Ось вам посилання документації [BrowserSync](https://browsersync.io).

### Команда запуску Browser Sync у терміналі bash VSCode:

```bash
browser-sync start --proxy "localhost/tatomama" --files "**/*" --no-notify
```

#### Результат:

```bash
[Browsersync] Proxying: http://localhost
[Browsersync] Access URLs:
 -----------------------------------------------
       Local: http://localhost:3000/tatomama
    External: http://192.168.0.103:3000/tatomama
 -----------------------------------------------
          UI: http://localhost:3001
 UI External: http://localhost:3001
 -----------------------------------------------
[Browsersync] Watching files...
[Browsersync] Reloading Browsers...
```

Після цього відкриється сайт [ТатоМама](http://localhost:3000/tatomama) з Browser Sync.
