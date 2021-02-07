# {{ page.title }}
## Introduction
Mysqlのクエリを同期的に実行したい！
## Contents
```js
let mysql = require('mysql');
const util = require('util');

const pool = mysql.createPool({
    host: 'localhost',
    user: 'root',
    password: 'hogehoge',
    database: 'hogehoge',
    dateStrings: true
});
pool.query = util.promisify(pool.query);

getlog();

async function getlog(pool_hoge) {
    try {
        let sql = 'select * from log limit 1;';
        let log = await pool_hoge.query(sql);
        console.log(log);
        console.log('get log 1');
    } catch (err) {
        console.log(err);
    }
}

pool.end();
```
他の順番も同期的にするため，awaitを多用するかも...
## Conclusion
## References
- [Node.jsのMySQLでAsync/Awaitする方法](https://qiita.com/reon777/items/d3781e40ba518a6544f8)
