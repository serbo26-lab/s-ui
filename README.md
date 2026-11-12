# s-ui-node

Форк [S-UI](https://github.com/alireza0/s-ui) для самостоятельной разработки. Backend написан на Go; интерфейс развивается отдельно в [s-ui-frontend-node](https://github.com/serbo26-lab/s-ui-frontend-node).

Исходные имена бинарника, службы и каталогов (`sui`, `s-ui`) пока сохранены для совместимости.

## Установка

После публикации первого **стабильного** релиза в [Releases](https://github.com/serbo26-lab/s-ui-node/releases) установка последней версии на Linux выполняется от root:

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/serbo26-lab/s-ui-node/main/install.sh)
```

Установщик скачивает архив и контрольные суммы из **serbo26-lab/s-ui-node**, а команда `s-ui update` проверяет обновления в этом же репозитории.

Пока первый стабильный релиз не опубликован, команда не сможет получить `releases/latest`. Новую сборку сначала проверяй на отдельном тестовом сервере, а не на действующей установке.

## Разработка

```bash
git clone --recurse-submodules https://github.com/serbo26-lab/s-ui-node.git
cd s-ui-node
```

Backend использует frontend как Git submodule `frontend/`, закреплённый за конкретным коммитом. Изменения frontend не попадают в сборку автоматически: указатель подмодуля обновляется отдельным PR в backend.

```bash
go vet ./...
. ./build-tags.sh
go test -tags "$(tags_for test)" ./...
```

Сборка frontend: `cd frontend && npm ci && npm run build`. CI проверяет обе части. Release workflow создаёт релиз по тегу `v*`, Docker workflow запускается вручную.

## Лицензия и авторство

GNU General Public License v3.0 — см. [LICENSE](LICENSE).

Оригинальный проект: [alireza0/s-ui](https://github.com/alireza0/s-ui). Оригинальный интерфейс: [alireza0/s-ui-frontend](https://github.com/alireza0/s-ui-frontend).

История Git и исходные уведомления об авторстве сохранены. Это независимый форк, не официальный релиз первоначального автора.
