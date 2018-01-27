- 麻生さんから教えてもらったやつの名前を忘れた　汗

### 修正したぜ！
### 直でいじったぜ！

***

- インフラ

```shell

    composer install

    [Y,n] -> y

    `
    
    gitTest/config/app.default.php

    app.php 作成 -> app.default.php ソースをこぴぺ

    データベース接続設定、ユーザーとパスを設定
    
    `

    'Datasources' => [
        'default' => [
            'className' => 'Cake\Database\Connection',
            'driver' => 'Cake\Database\Driver\Postgres',
            'persistent' => false,
            'host' => 'localhost',
            'username' => 'ユーザ',
            'password' => 'パス',
            'database' => '_20180126',
            'encoding' => 'utf8',
            'timezone' => 'UTC',
            'flags' => [],
            'cacheMetadata' => true,
            'log' => false,

            /**
             * Set identifier quoting to true if you are using reserved words or
             * special characters in your table or column names. Enabling this
             * setting will result in queries built using the Query Builder having
             * identifiers quoted when creating SQL. It should be noted that this
             * decreases performance because each query needs to be traversed and
             * manipulated before being executed.
             */
            'quoteIdentifiers' => false,

            /**
             * During development, if using MySQL < 5.6, uncommenting the
             * following line could boost the speed at which schema metadata is
             * fetched from the database. It can also be set directly with the
             * mysql configuration directive 'innodb_stats_on_metadata = 0'
             * which is the recommended value in production environments
             */
            //'init' => ['SET GLOBAL innodb_stats_on_metadata = 0'],

            'url' => env('DATABASE_URL', null),
        ],
    ],
```

- データベースの初期化

```shell

    `SQL/initDatabase.sqlをpostgres || mysqlに入れる`

    cd bin

    cake migrations migrate


    cake bake all items

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
