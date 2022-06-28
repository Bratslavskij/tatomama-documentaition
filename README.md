# Документація ТатоМама

Авторські права © | 2016 - 2022 | ТатоМама | Україна 🇺🇦 | Всі права захищені

## <img src="https://avatars.githubusercontent.com/u/10654171?s=200&amp;v=4" width="25" height="25" alt="BrowserSync"> Browser Sync

Документація [BrowserSync](https://browsersync.io)

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

Після цього відкриється сайт [ТатоМама](http://localhost:3000/tatomama).
