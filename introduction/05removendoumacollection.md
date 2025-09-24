# Removendo uma Collection no MongoDB

⚠️ **Atenção:** Ao executar o comando para remover uma collection, **todos os dados contidos nela serão permanentemente apagados**. Use com cuidado e sempre faça backup se os dados forem importantes.

---

## Comando Básico

```javascript
db.<collection>.drop()
```

## Parâmetros Opcionais

O método **drop()** pode receber um objeto opcional o campo: 
| Campo          | Descrição                                                                                                                  |
|----------------|----------------------------------------------------------------------------------------------------------------------------|
| `writeConcern` | Define o nível de confirmação da operação de exclusão. O padrão do MongoDB será usado se omitido. Por exemplo: `{ w: "majority", wtimeout: 5000 }`. Isso garante que a exclusão seja registrada na maioria dos nós do cluster antes de confirmar sucesso. |


## exemplo de uso

```javascript
db.usuarios.drop()

db.usuarios.drop({ writeConcern: { w: "majority", wtimeout: 5000 } })
```
## Como verificar se a collection foi removida ?

```javascript
db.getCollectionNames()
```
Se a collection removida não aparecer na lista, a exclusão foi bem-sucedida

## Diferença entre **drop()** e **deleteMany()**

| Comando           | O que faz                                                                 |
|------------------|---------------------------------------------------------------------------|
| `drop()`          | Remove a collection inteira, incluindo seus dados e índices.             |
| `deleteMany({})`  | Remove todos os documentos da collection, mas mantém a estrutura e os índices. |

