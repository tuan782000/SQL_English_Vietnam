# Wildcards quiz

## Example 1

```sql
SELECT * from users
    WHERE name LIKE 'or_%';
```

answer

"Các giá trị bắt đầu bằng 'hoặc' và có độ dài ít nhất 3 ký tự.",
"Các giá trị kết thúc bằng 'hoặc' và có độ dài ít nhất 3 ký tự.",
"Các giá trị bắt đầu bằng 'hoặc' và có chính xác 3 ký tự.",
"Các giá trị kết thúc bằng 'hoặc' và có chính xác 3 ký tự."

## Example 2

```sql
SELECT * from users
    WHERE name LIKE '__ing';
```

answer: 

"singing",
"thing",
"bling",
"sling"
