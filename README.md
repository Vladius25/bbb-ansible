# Плейбук для настройки BigBlueButton

## Настройка
В `hosts` добавить сервер:
```
example ansible_host=example.com
```
В `host_vars/example.yml` добавить (для каждого хоста свой .yml файл):
```
---
hostname: example.com
greenlight_repo: git@github.com:bigbluebutton/greenlight.git

```
Настроить ключи для git, если репозиторий приватный.

## Запуск
Скопировать свой ssh-ключ на сервер под рута и запустить:
```bash
ssh-copy-id root@example.com
ansible-playbook setup-bbb.yml -u root -i hosts
```

## Тестирование
```bash
vagrant up --provider virtualbox
```
