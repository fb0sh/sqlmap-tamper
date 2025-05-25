# sqlmap-tamper

SQLmap Tamper 脚本

通用 Tamper 选项 和 tamper 列表

```
tamper=name_of_the_tamper
sqlmap 1.9.2#stable
/usr/share/sqlmap/tamper
```

| Tamper                         | 描述                                                                                                        |
|-------------------------------|-------------------------------------------------------------------------------------------------------------|
| apostrophemask.py             | 将撇号字符替换为 UTF-8 全角版本                                                                             |
| apostrophenullencode.py       | 将撇号字符替换为非法的双重 Unicode 编码版本                                                                 |
| appendnullbyte.py             | 在 payload 末尾追加编码后的 NULL 字节                                                                       |
| base64encode.py               | 对 payload 中的所有字符进行 Base64 编码                                                                     |
| between.py                    | 将大于操作符（'>'）替换为 'NOT BETWEEN 0 AND #'                                                              |
| bluecoat.py                   | 将 SQL 语句后的空格替换为合法的随机空白字符，并将等号 '=' 替换为 LIKE 操作符                               |
| chardoubleencode.py           | 对 payload 中所有字符进行双重 URL 编码（已编码字符不处理）                                                   |
| commalesslimit.py             | 将 'LIMIT M, N' 替换为 'LIMIT N OFFSET M'                                                                   |
| commalessmid.py               | 将 'MID(A, B, C)' 替换为 'MID(A FROM B FOR C)'                                                              |
| concat2concatws.py            | 将 'CONCAT(A, B)' 替换为 'CONCAT_WS(MID(CHAR(0), 0, 0), A, B)'                                               |
| charencode.py                 | 对 payload 中所有字符进行 URL 编码（已编码字符不处理）                                                      |
| charunicodeencode.py          | 对 payload 中未编码字符进行 Unicode-URL 编码（已编码字符不处理）                                            |
| equaltolike.py                | 将所有等号 '=' 操作符替换为 'LIKE' 操作符                                                                   |
| escapequotes.py               | 使用斜杠转义引号字符（' 和 "）                                                                               |
| greatest.py                   | 将大于操作符 '>' 替换为 'GREATEST' 函数                                                                     |
| halfversionedmorekeywords.py  | 在每个关键字前添加 MySQL 版本化注释                                                                         |
| ifnull2ifisnull.py            | 将 'IFNULL(A, B)' 替换为 'IF(ISNULL(A), B, A)'                                                               |
| modsecurityversioned.py       | 用版本化注释包裹整个查询语句                                                                                |
| modsecurityzeroversioned.py   | 用零版本注释包裹整个查询语句                                                                                |
| multiplespaces.py             | 在 SQL 关键字周围添加多个空格                                                                               |
| nonrecursivereplacement.py    | 将预定义的 SQL 关键字替换为适合绕过 .replace("SELECT", "") 等过滤器的形式                                   |
| percentage.py                 | 在每个字符前添加 '%'                                                                                         |
| overlongutf8.py               | 将 payload 中所有字符转换为超长 UTF-8 编码（不处理已编码字符）                                               |
| randomcase.py                 | 将每个关键字字符替换为随机大小写形式                                                                        |
| randomcomments.py             | 在 SQL 关键字中插入随机注释                                                                                  |
| securesphere.py               | 在 payload 末尾添加特制字符串                                                                                |
| sp_password.py                | 在 payload 末尾添加 'sp_password' 以自动规避 DBMS 日志                                                       |
| space2comment.py              | 将空格替换为注释                                                                                             |
| space2dash.py                 | 将空格替换为 '--' 注释，加上随机字符串和换行                                                                 |
| space2hash.py                 | 将空格替换为 '#' 注释，加上随机字符串和换行                                                                  |
| space2morehash.py             | 同上，使用更多 '#' 注释                                                                                      |
| space2mssqlblank.py           | 将空格替换为 MSSQL 中可识别的随机空白字符                                                                   |
| space2mssqlhash.py            | 将空格替换为 '#' 并加换行（适用于 MSSQL）                                                                    |
| space2mysqlblank.py           | 将空格替换为 MySQL 中可识别的随机空白字符                                                                   |
| space2mysqldash.py            | 将空格替换为 '--' 并加换行（适用于 MySQL）                                                                   |
| space2plus.py                 | 将空格替换为加号 '+'                                                                                         |
| space2randomblank.py          | 将空格替换为任意合法的空白字符                                                                              |
| symboliclogical.py            | 将逻辑运算符 AND/OR 替换为符号 && 和 \|\|                                                                   |
| unionalltounion.py            | 将 'UNION ALL SELECT' 替换为 'UNION SELECT'                                                                  |
| unmagicquotes.py              | 将撇号替换为多字节组合 %bf%27，并在结尾添加通用注释以实现绕过                                               |
| uppercase.py                  | 将每个关键字字符替换为大写形式（如 'SELECT'）                                                                |
| varnish.py                    | 添加 HTTP 头部 'X-originating-IP'                                                                            |
| versionedkeywords.py          | 使用 MySQL 版本注释包裹每个非函数关键字                                                                      |
| versionedmorekeywords.py      | 使用 MySQL 版本注释包裹每个关键字                                                                            |
| xforwardedfor.py              | 添加伪造的 HTTP 头部 'X-Forwarded-For'                                                                       |
| 0eunion.py                    | 将 <int> UNION 替换为 <int>e0UNION                                                                            |
| binary.py                     | 在可用位置插入关键字 'binary'                                                                                |
| charunicodeescape.py          | 将字符 Unicode 转义（如 SELECT -> \u0053\u0045\u004C\u0045\u0043\u0054）                                    |
| commentbeforeparentheses.py   | 在括号前插入注释（如 '(' -> '/**/('）                                                                        |
| decentities.py                | 将字符转为 HTML 十进制实体（如 ' -> &#39;）                                                                  |
| dunion.py                     | 将 <int> UNION 替换为 <int>DUNION                                                                             |
| equaltorlike.py               | 将等号 '=' 替换为 'RLIKE' 运算符                                                                             |
| hex2char.py                   | 将 MySQL 中的 0x<hex> 字符串替换为 CONCAT(CHAR(),...)                                                        |
| hexentities.py                | 将字符转为 HTML 十六进制实体（如 ' -> &#x31;）                                                               |
| htmlencode.py                 | 将非字母数字字符转为 HTML 实体（如 ' -> &#39;）                                                               |
| if2case.py                    | 将 'IF(A, B, C)' 替换为 'CASE WHEN (A) THEN (B) ELSE (C) END'                                                |
| ifnull2casewhenisnull.py      | 将 'IFNULL(A, B)' 替换为 'CASE WHEN ISNULL(A) THEN (B) ELSE (A) END'                                        |
| informationschemacomment.py   | 在所有 "information_schema" 标识符后添加注释                                                                 |
| least.py                      | 将 '>' 替换为 'LEAST' 函数                                                                                   |
| lowercase.py                  | 将每个关键字字符替换为小写形式（如 SELECT -> select）                                                        |
| luanginx.py                   | 针对 LUA-Nginx WAF 绕过（如 Cloudflare）                                                                      |
| misunion.py                   | 将 UNION 替换为 -.1UNION                                                                                      |
| ord2ascii.py                  | 将 ORD() 替换为 ASCII()                                                                                       |
| overlongutf8more.py           | 将所有字符转换为超长 UTF-8（如 SELECT -> %C1%93%C1%85%C1%8C%C1%85%C1%83%C1%94）                              |
| plus2concat.py                | 将 '+' 操作符替换为 MSSQL 的 CONCAT() 函数                                                                   |
| plus2fnconcat.py              | 将 '+' 操作符替换为 MSSQL 的 ODBC 函数 {fn CONCAT()}                                                         |
| schemasplit.py                | 将 'testdb.users' 替换为带空格的形式 'testdb 9.e.users'                                                      |
| scientific.py                 | 利用 MySQL 科学记数法特性进行绕过                                                                            |
| sleep2getlock.py              | 将 'SLEEP(5)' 替换为 'GET_LOCK('xxx',5)'                                                                      |
| space2morecomment.py          | 将空格替换为注释 '/**_**/'（MySQL）                                                                          |
| substring2leftright.py        | 将 PostgreSQL 的 SUBSTRING 替换为 LEFT 和 RIGHT                                                               |
