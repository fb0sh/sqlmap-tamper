# sqlmap-tamper

SQLmap tamper scripts

General tamper option and tamper's list

```
tamper=name_of_the_tamper
sqlmap 1.9.2#stable
/usr/share/sqlmap/tamper
```

| Tamper                  | Description                                                                                                                        |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| apostrophemask.py       | Replaces apostrophe character with its UTF-8 full width counterpart                                                                |
| apostrophenullencode.py | Replaces apostrophe character with its illegal double unicode counterpart                                                          |
| appendnullbyte.py       | Appends encoded NULL byte character at the end of payload                                                                          |
| base64encode.py         | Base64 all characters in a given payload                                                                                           |
| between.py              | Replaces greater than operator ('>') with 'NOT BETWEEN 0 AND #'                                                                    |
| bluecoat.py             | Replaces space character after SQL statement with a valid random blank character.Afterwards replace character = with LIKE operator |
| chardoubleencode.py | Double url-encodes all characters in a given payload (not processing already encoded) |
| commalesslimit.py | Replaces instances like 'LIMIT M, N' with 'LIMIT N OFFSET M' |
| commalessmid.py | Replaces instances like 'MID(A, B, C)' with 'MID(A FROM B FOR C)' |
| concat2concatws.py | Replaces instances like 'CONCAT(A, B)' with 'CONCAT_WS(MID(CHAR(0), 0, 0), A, B)' |
| charencode.py | Url-encodes all characters in a given payload (not processing already encoded) |
| charunicodeencode.py | Unicode-url-encodes non-encoded characters in a given payload (not processing already encoded) |
| equaltolike.py | Replaces all occurances of operator equal ('=') with operator 'LIKE' |
| escapequotes.py | Slash escape quotes (' and ") |
| greatest.py | Replaces greater than operator ('>') with 'GREATEST' counterpart |
| halfversionedmorekeywords.py | Adds versioned MySQL comment before each keyword |
| ifnull2ifisnull.py | Replaces instances like 'IFNULL(A, B)' with 'IF(ISNULL(A), B, A)' |
| modsecurityversioned.py | Embraces complete query with versioned comment |
| modsecurityzeroversioned.py | Embraces complete query with zero-versioned comment |
| multiplespaces.py | Adds multiple spaces around SQL keywords |
| nonrecursivereplacement.py | Replaces predefined SQL keywords with representations suitable for replacement (e.g. .replace("SELECT", "")) filters |
| percentage.py | Adds a percentage sign ('%') infront of each character |
| overlongutf8.py | Converts all characters in a given payload (not processing already encoded) |
| randomcase.py | Replaces each keyword character with random case value |
| randomcomments.py | Add random comments to SQL keywords |
| securesphere.py | Appends special crafted string |
| sp_password.py | Appends 'sp_password' to the end of the payload for automatic obfuscation from DBMS logs |
| space2comment.py | Replaces space character (' ') with comments |
| space2dash.py | Replaces space character (' ') with a dash comment ('--') followed by a random string and a new line ('\n') |
| space2hash.py | Replaces space character (' ') with a pound character ('#') followed by a random string and a new line ('\n') |
| space2morehash.py | Replaces space character (' ') with a pound character ('#') followed by a random string and a new line ('\n') |
| space2mssqlblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
| space2mssqlhash.py | Replaces space character (' ') with a pound character ('#') followed by a new line ('\n') |
| space2mysqlblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
| space2mysqldash.py | Replaces space character (' ') with a dash comment ('--') followed by a new line ('\n') |
| space2plus.py | Replaces space character (' ') with plus ('+') |
| space2randomblank.py | Replaces space character (' ') with a random blank character from a valid set of alternate characters |
| symboliclogical.py | Replaces AND and OR logical operators with their symbolic counterparts (&& and | | ) |
| unionalltounion.py | Replaces UNION ALL SELECT with UNION SELECT |
| unmagicquotes.py | Replaces quote character (') with a multi-byte combo %bf%27 together with generic comment at the end (to make it work) |
| uppercase.py | Replaces each keyword character with upper case value 'INSERT' |
| varnish.py | Append a HTTP header 'X-originating-IP' |
| versionedkeywords.py | Encloses each non-function keyword with versioned MySQL comment |
| versionedmorekeywords.py | Encloses each keyword with versioned MySQL comment |
| xforwardedfor.py | Append a fake HTTP header 'X-Forwarded-For' |
| 0eunion.py | Replaces instances of <int> UNION with <int>e0UNION |
| binary.py | Injects keyword binary where possible |
| charunicodeescape.py | Unicode-escapes non-encoded characters in a given payload (not processing already encoded) (e.g. SELECT -> \u0053\u0045\u004C\u0045\u0043\u0054) |
| commentbeforeparentheses.py | Prepends (inline) comment before parentheses (e.g. ( -> /\*\*/() |
| decentities.py | HTML encode in decimal (using code points) all characters (e.g. ' -> &#39;) |
| dunion.py | Replaces instances of <int> UNION with <int>DUNION |
| equaltorlike.py | Replaces all occurrences of operator equal ('=') with 'RLIKE' counterpart |
| hex2char.py | Replaces each (MySQL) 0x<hex> encoded string with equivalent CONCAT(CHAR(),...) counterpart |
| hexentities.py | HTML encode in hexadecimal (using code points) all characters (e.g. ' -> &#x31;) |
| htmlencode.py | HTML encode (using code points) all non-alphanumeric characters (e.g. ' -> &#39;) |
| if2case.py | Replaces instances like 'IF(A, B, C)' with 'CASE WHEN (A) THEN (B) ELSE (C) END' counterpart |
| ifnull2casewhenisnull.py | Replaces instances like 'IFNULL(A, B)' with 'CASE WHEN ISNULL(A) THEN (B) ELSE (A) END' counterpart |
| informationschemacomment.py | Add an inline comment (/\*\*/) to the end of all occurrences of (MySQL) "information_schema" identifier |
| least.py | Replaces greater than operator ('>') with 'LEAST' counterpart |
| lowercase.py | Replaces each keyword character with lower case value (e.g. SELECT -> select) |
| luanginx.py | LUA-Nginx WAFs Bypass (e.g. Cloudflare) |
| misunion.py | Replaces instances of UNION with -.1UNION |
| ord2ascii.py | Replaces ORD() occurences with equivalent ASCII() calls |
| overlongutf8more.py | Converts all characters in a given payload to overlong UTF8 (not processing already encoded) (e.g. SELECT -> %C1%93%C1%85%C1%8C%C1%85%C1%83%C1%94) |
| plus2concat.py | Replaces plus operator ('+') with (MsSQL) function CONCAT() counterpart |
| plus2fnconcat.py | Replaces plus operator ('+') with (MsSQL) ODBC function {fn CONCAT()} counterpart |
| schemasplit.py | Splits FROM schema identifiers (e.g. 'testdb.users') with whitespace (e.g. 'testdb 9.e.users') |
| scientific.py | Abuses MySQL scientific notation |
| sleep2getlock.py | Replaces instances like 'SLEEP(5)' with (e.g.) "GET_LOCK('ETgP',5)" |
| space2morecomment.py | Replaces (MySQL) instances of space character (' ') with comments '/**\_**/' |
| substring2leftright.py | Replaces PostgreSQL SUBSTRING with LEFT and RIGHT |