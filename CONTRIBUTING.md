# Разработка s-ui-node

Репозиторий основан на [alireza0/s-ui](https://github.com/alireza0/s-ui). Интерфейс разрабатывается в [serbo26-lab/s-ui-frontend-node](https://github.com/serbo26-lab/s-ui-frontend-node).

## Получение исходников

```bash
git clone --recurse-submodules https://github.com/serbo26-lab/s-ui-node.git
cd s-ui-node
```

Подмодуль `frontend/` закреплён за конкретным коммитом. Когда изменение интерфейса готово, обновляй указатель подмодуля отдельным PR в backend.

## Проверки

Перед PR проверь `gofmt`, `go vet ./...` и `go test` с профилем `test` из `build-tags.sh`. Для frontend используй `npm ci`, `npm run lint -- --max-warnings=0`, `npm test` и `npm run build`.

Релизы должны собираться из проверенного backend и закреплённого frontend. В PR объясняй, что изменилось, зачем, как проверено и есть ли риск для совместимости. Изменения установщика, обновлений и базы данных требуют отдельной проверки.

Лицензия проекта: GPL-3.0 ([LICENSE](LICENSE)).
