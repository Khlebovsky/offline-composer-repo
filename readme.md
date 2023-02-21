<h2>
Оффлайн-репозиторий для зависимостей Composer
</h2>

Инструкции:

1) Указать необходимые пакеты в файле offline-repo/satis.json
2) Собрать проект: docker-compose up -d --build
3) Выполнить команду для сборки репозитория: <br> docker exec -it composer-repo-application php ../satis/bin/satis build
   satis.json .

На странице localhost:8080 будет доступен список загруженных вендоров

Для подключения в проект необходимо добавить репозиторий в composer.json нужного проекта:

```json
{
  "repositories": [
    {
      "type": "composer",
      "url": "http://localhost"
    }
  ]
}
```

Файлы вендоров будут доступны в папке /offline-repo