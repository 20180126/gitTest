### 20180124

***

- データベースの初期化

```shell

    `SQL/initDatabase.sqlをpostgres || mysqlに入れる`

    cd bin

    cake migrations migrate

```



- 表示コントローラを作成

```php

    `src/Controller/ItemsController`

    public function viewContent(){

        $items = $this->paginate($this->Items);

        $this->set(compact('items'));
    }

```


```shell

    cake bake all items

    cake server

    `http://localhost:8765/items || http://localhost:8765/items/viewContent`

```
