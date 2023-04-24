# hmapi.aoirint.com

```shell
npm install -g hasura-cli

git clone https://github.com/aoirint/harmonica-hasura.git
cd harmonica-hasura

export "HASURA_GRAPHQL_ADMIN_SECRET=$(read -s -p "Admin Secret: "; echo $REPLY)"

hasura migrate apply --project="./hasura" --endpoint="https://hmapi.aoirint.com" --all-databases
hasura metadata apply --project="./hasura" --endpoint="https://hmapi.aoirint.com"
```
