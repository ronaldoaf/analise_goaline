# analise_goaline

```sql
INSERT INTO stats2 
SELECT CAST(LEFT(jogo_id, CHAR_LENGTH(jogo_id)-1) AS SIGNED), data FROM data WHERE RIGHT(jogo_id,1)='s'

INSERT INTO odds
SELECT CAST(LEFT(jogo_id, CHAR_LENGTH(jogo_id)-1) AS SIGNED), data FROM data WHERE RIGHT(jogo_id,1)='o'


SELECT s.*,o.*,r.* FROM stats2 s INNER JOIN odds o INNER JOIN resultados r ON s.jogo_id=o.jogo_id AND s.jogo_id=r.jogo_id
```
