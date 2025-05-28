# A chave _id no MongoDB

Todo documento salvo em uma collection no MongoDB possui automaticamente um campo chamado _id, que funciona como um identificador único para cada registro.

## Funções e características do _id

 ### indentificador único: 
 garante que cada documento tenha um valor exclusivo de _id, evitando registros duplicados.

 ### baseado no tempo 
 por padrão, o mongoDB gera um ObjectId, que inclui informações como: 

 - Timestamp de criação ( primeiros bytes )

 - intentificador da máquina

 - PID do processo 

 - Um contador incremental

 Isso faz com que, mesmo que vários documentos sejam inseridos ao "mesmo tempo", seus _id, sejam diferentes.

 ### Índice automático: 
 O MongoDB cria automaticamente um índice primário no campo _id.
Isso torna consultas, atualizações e exclusões por _id muito mais rápidas e eficientes.

## exemplos: 
``` json
{
  "_id": ObjectId("66560f4b52f6a61d7996fd28"),
  "nome": "Daniel",
  "idade": 25
}
```

Personalizar o _id (opcional)

Você também pode definir manualmente o valor do _id na hora de inserir o documento:

```
db.usuarios.insertOne({
  _id: "user_daniel",
  nome: "Daniel",
  idade: 25
})
```