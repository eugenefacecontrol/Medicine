# Medicine table

В папке лежит локальная таблица аптечки:

- `medicine_table.html` - страница с поиском, фильтрами, картинками и разделением по коробкам.
- `medicine_index.json` - данные по лекарствам и соответствие `файл -> название`.
- `_previews_full/` - JPEG-превью для отображения в таблице.
- `First box/`, `Second box/` - исходные HEIC-фото.

## GitHub Pages

Онлайн-версия таблицы:

```text
https://eugenefacecontrol.github.io/Medicine/medicine_table.html
```

Для GitHub Pages в репозитории должны быть закоммичены:

- `_previews_full/` - картинки для таблицы;
- `.nojekyll` - чтобы GitHub Pages отдавал папку с `_` в начале имени.

## Как запустить

Открой PowerShell в папке `C:\Source\Medicine` и запусти:

```powershell
& 'C:\Users\Yauhe\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe' -m http.server 8021 --bind 127.0.0.1
```

Потом открой в браузере:

```text
http://127.0.0.1:8021/medicine_table.html
```

## Как пользоваться

- В поле поиска можно писать название, действующее вещество, описание или часть имени файла.
- Фильтр `Все коробки` переключает между `First box` и `Second box`.
- Фильтр уверенности помогает найти записи, которые стоит перепроверить: `medium` или `low`.
- Клик по картинке открывает JPEG-превью крупнее.
- Клик по имени файла открывает исходный HEIC, если браузер умеет его показывать.

## Если порт занят

Можно выбрать другой порт, например `8022`:

```powershell
& 'C:\Users\Yauhe\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe' -m http.server 8022 --bind 127.0.0.1
```

И открыть:

```text
http://127.0.0.1:8022/medicine_table.html
```

## Быстрый поиск без браузера

Например, найти парацетамол:

```powershell
rg -n "paracetamol|парацетамол" medicine_index.json
```

Или аллергию:

```powershell
rg -n "allerg|cetiriz|цетрин|atarax|hydroxyz" medicine_index.json
```
