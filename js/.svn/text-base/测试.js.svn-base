//连接数据库
var mysql = require('mysql');
var connection = mysql.createConnection({
	host: 'localhost',
	user: 'root',
	password: 'qwertyuiop123',
	database: 'users'
});

connection.connect();
//查询
connection.query('select * from `users`', function(err, rows, fields) {
	if (err) throw err;
	console.log('查询结果为: ', rows);
});
//增 add
var userAddSql = 'INSERT INTO users(id,username,password,age) VALUES(0,?,?,?)';
var userAddSql_Params = ['Wilson','wilim',55];
connection.query(userAddSql, userAddSql_Params, function(err, result) {
	if (err) {
		console.log('[INSERT ERROR] - ', err.message);
		return;
	}
	console.log('-------INSERT----------');
	console.log('INSERT ID:',result.insertId);       
	console.log('INSERT ID:', result);
	console.log('#######################');
});
//改 up
var userModSql = 'UPDATE users SET username = ?,age = ? WHERE id = ?';
var userModSql_Params = ['Hello World', 99, 1];
connection.query(userModSql, userModSql_Params, function(err, result) {
	if (err) {
		console.log('[UPDATE ERROR] - ', err.message);
		return;
	}
	console.log('----------UPDATE-------------');
	console.log('UPDATE affectedRows', result.affectedRows);
	console.log('******************************');
});
//查 query
var userGetSql = 'SELECT * FROM users';
connection.query(userGetSql, function(err, result) {
	if (err) {
		console.log('[SELECT ERROR] - ', err.message);
		return;
	}

	console.log('---------------SELECT----------------');
	console.log(result);
	console.log('$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$');
});
//删
var userDelSql = 'DELETE FROM users WHERE id =2';
connection.query(userDelSql, function(err, result) {
	if (err) {
		console.log('[DELETE ERROR] - ', err.message);
		return;
	}

	console.log('-------------DELETE--------------');
	console.log('DELETE affectedRows', result.affectedRows);
	console.log('&&&&&&&&&&&&&&&&&');
});
//关闭连接
connection.end();
