

学習メモ：  
* 匿名クラス → ラムダ式  
以下のコードで、`jdbcTemplate.queryForObject`がSQLの実行結果を受け取ることから、第３引数にはオブジェクトマッピングを定義する`RowMapper`が推論される。
```
Customer result = jdbcTemplate.queryForObject(sql, param, (rs, rowNum) ->
				new Customer(rs.getInt("id"), rs.getString("first_name"), rs.getString("last_name"))
		);
```
