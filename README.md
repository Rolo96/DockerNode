# Orders API (Node Docker) 

```
Technological Institute of Costa Rica
Project2 CompraTec
Teacher: Raul Madrigal Acuña
Students: Raul Arias, Rony Paniagua
Script docker swarm
```
## Installation
You need to have Node JS and npm installed in your development environment.
```
1. Download the source repository.
2. Run "npm install".
3. Run "npm start".
4. In your browser navigate to: localhost:8000/graphql
```
## Orders model
```
id: int
date: string
userid: int
products: json array
amount: int
```

## API usage

### Consult
To consult all the orders, the following query is used: 
```
{
  Orders{
    id date userid total products {id amount cost}
  }
}
```
To consult one order, the following query is used: 
```
{
  Order(id:1){
    id date userid total
  }
}
```

### Insert
To insert an order the following mutation is used:
```
mutation{
  CreateOrder(order:{userid:1, products:[{id:1, amount:1, cost:1}], total:1}){
    info
  }
}
```
The result of the mutation will be returned in info.

### Update
To update the orders the following mutation is used:
```
mutation{
  UpdateOrder(order:{id:1,userid:1, products:[{id:1, amount:1, cost:1}], total:1}){
    info
  }
}
```
Where the id of the order is received as parameters to modify the other attributes. In the info you will see the result of the mutation

## Delete
To delete the orders the following mutation is used:
```
mutation{
  DeleteOrder(id:1){
    info
  }
}
```
Where the id of the order to be deleted is received as a parameter, and in the info you will see the result of the mutation.
