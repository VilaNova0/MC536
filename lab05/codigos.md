# Código para a solução de cada tarefa

## Tarefa 1
```
  MATCH (m:Marcador)
  MATCH (c:Categoria)
  WHERE ((m)-[:Pertence]->(c {id: "Serviços}))
  RETURN (m)
```

## Tarefa 2
```
  MATCH (m:Marcador)
  MATCH (c1:Categoria)
  MATCH (c2:Categoria)
  WHERE ((m)-[:Pertence]->(c1 {id: "Serviços"})) OR
        ((m)-[:Pertence]->(c1) AND (c1)-[:Superior*1..3]->(c2 {id: "Serviços"}))
  RETURN (m)
```
