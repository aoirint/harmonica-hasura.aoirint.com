# harmonica-hasura.aoirint.com

[aoirint/harmonica-hasura](https://github.com/aoirint/harmonica-hasura)の個人用インスタンス。

```shell
npm install -g hasura-cli

git clone https://github.com/aoirint/harmonica-hasura.git
cd harmonica-hasura

export "HASURA_GRAPHQL_ADMIN_SECRET=$(read -s -p "Admin Secret: "; echo $REPLY)"

hasura migrate apply --project="./hasura" --endpoint="https://harmonica-hasura.aoirint.com" --all-databases
hasura metadata apply --project="./hasura" --endpoint="https://harmonica-hasura.aoirint.com"
```

## Backup & Restore

```shell
DUMP_SQL=$(sudo docker compose exec postgres pg_dump -U postgres --schema public --no-owner --no-acl --data-only --disable-triggers) && echo "$DUMP_SQL" > backups/dump_$(date -u "+%Y-%m-%dT%H-%M-%S_%6NZ").sql

cat backups/dump_2023-01-01T00-00-00_000000Z.sql | sudo docker compose exec -T postgres psql -U postgres --single-transaction
```
