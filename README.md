# cnft_test
Для запуска необходимо собрать контейнеры с помощью команды
```
docker-compose up
```

Затем для восстановления из бекапов:
```
docker exec -i $(docker ps -q -f name='test_cnft_psql_src_1') pg_restore /pgdump_folder/ -d checknft -U 'etl'
docker exec -i $(docker ps -q -f name='test_cnft_psql_dst_1') pg_restore /pgdump_folder/ -d checknft -U 'etl'
```

Внутри контейнера checknft_dst в базе данных checknft лежит таблица public.marketCap
