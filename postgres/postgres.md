Filtrar data dos ultimos 15 dias

```
SELECT email
FROM table
WHERE created_at >= CURRENT_DATE - 15
```