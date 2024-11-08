# Static-jinja-plus-ports

Посмотреть на исходники скрипта можно [тут](https://github.com/MrDave/StaticJinjaPlus)

Чтобы собрать образы у вас уже должен быть установлен [Docker](https://www.docker.com/products/docker-desktop/)

Также вы должны [зарегистрироваться](https://docs.docker.com/reference/cli/docker/login/)

В репозитории представлены следующии версии:

`/develop/python_slim `- легкая версия, содержащая последнии изменения из оригинального репозитория

`/develop/ubuntu` - Версия с загруженной ubuntu 24.04, содержащая последнии изменения из оригинального репозитория

`/v0.1.0&0.1.0/python-slim` - Этим Dockerfile можно собрать две стабильные версии (0.1.0 & 0.1.1) на базе легкой версии

`/v0.1.0&0.1.0/ubuntu` - Этим Dockerfile можно собрать две стабильные версии (0.1.0 & 0.1.1) на базе ubuntu

## Как собрать

Перейдите в папку с Dockerfile или используйте флаг `-f`

``docker build -t <Имя образа>:тег .``

Примеры:

### develop ubuntu

```Dockerfile
docker build -t stmkv/static-jinja-plus:develop-ubuntu .
```

### develop python-slim

```Dockerfile
docker build -t stmkv/static-jinja-plus:develop-python-slim .
```


### Стабильные версии

Python-slim-0.1.0

```
docker build --build-arg VERSION="0.1.0" --build-arg CHECKSUM="3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444" -t stmkv/static-jinja-plus:0.1.0-python-slim .
```

Python-slim-0.1.1

```
docker build --build-arg VERSION="0.1.1" --build-arg CHECKSUM="30d9424df1eddb73912b0e2ad5375fa2c876c8e30906bec91952dfb75dcf220b" -t stmkv/static-jinja-plus:0.1.1-python-slim .
```

ubuntu-0.1.0

```
docker build --build-arg VERSION="0.1.0" --build-arg CHECKSUM="3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444" -t stmkv/static-jinja-plus:0.1.0-ubuntu .
```

Ubuntu-0.1.1

```
docker build --build-arg VERSION="0.1.1" --build-arg CHECKSUM="30d9424df1eddb73912b0e2ad5375fa2c876c8e30906bec91952dfb75dcf220b" -t stmkv/static-jinja-plus:0.1.1-ubuntu .
```


## Запуск

```
docker run --rm -v "$(pwd)/templates:/app/templates" -v "$(pwd)/build:/app/build" <Название вышего образ>/static-jinja-plus:<tag>
```
