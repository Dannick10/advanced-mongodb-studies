# Removendo Banco no MongoDB

⚠️ **Atenção:** Ao executar o comando para remover um banco de dados, **todos os dados contidos nela serão permanentemente apagados**. Use com cuidado e sempre faça backup se os dados forem importantes.

## Definição

```javascript
db.usuarios.dropDatabase()
```

Remove o banco de dados atual, excluindo os arquivos de dados associados.


## Parâmetros Opcionais

| Campo          | Descrição                                                                                                                  |
|----------------|----------------------------------------------------------------------------------------------------------------------------|
| `writeConcern` | Opcional. Um documento que expressa a write concern a ser usada se for maior que "majority". `{ w: <value>, j: <boolean>, wtimeout: <number> }`. Quando emitida em um conjunto de réplicas, se a write concern especificada resultar em menos confirmações de membro do que a write concern "majority" , a operação usará "majority" . Caso contrário, a write concern especificada será usada |


## Exemplo de Uso

```javascript 

db.dropDatabase()


db.dropDatabase({ writeConcern: { w: "majority", wtimeout: 5000 } })

```

## como verificar se o Banco foi removido ?

 ```javascript 
show dbs
 ```
 Se o banco de dados excluído não aparecer na lista, a exclusão foi bem-sucedida.


 ## Diferença entre dropDatabase() e drop()

 | Comando           | O que faz                                                                 |
|------------------|---------------------------------------------------------------------------|
| `dropDatabase()`          |	Remove apenas uma collection específica dentro do banco atual.             |
| `drop()`  | Remove apenas uma collection específica dentro do banco atual.|
