

# PostgreSQL


## Reset password

On windows: https://www.youtube.com/watch?v=_mrNgqO5Tic
- Example: `ALTER USER postgres WITH PASSWORD 'ilovepizza';`



## List databases

- Open SQL shell
- `\list`


# Drop Database

- Open SQL shell
- Terminate processes (replace myCoolDbName): `sql SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE datname = 'myCoolDbName';`
- Drop DB (replace myCoolDbName): `sql DROP DATABASE "myCoolDbName";`

