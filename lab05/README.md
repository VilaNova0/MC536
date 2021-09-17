# Aluno
* `213081`: `André Vila Nova Wagner da Costa`

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
  MATCH (m:Marcador)
  MATCH (c:Categoria)
  WHERE ((m)-[:Pertence]->(c {id: "Serviços}))
  RETURN (m)
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
  MATCH (m:Marcador)
  MATCH (c1:Categoria)
  MATCH (c2:Categoria)
  WHERE ((m)-[:Pertence]->(c1 {id: "Serviços"})) OR
        ((m)-[:Pertence]->(c1) AND (c1)-[:Superior*1..3]->(c2 {id: "Serviços"}))
  RETURN (m)
~~~
