# BillProvider API
This a service that allow a company create a bill and make it available to be payed in all vinti4 channels.

## Create BillProvider
To create a new bill you should do a post following the specification below.

### URL
In test you must do post to the URL below
```
https://test.faxi.online/api/bill-provider
```

### Headers
To authenticate with the API you should send
the token provided by Faxi in HTTP Headers
- Authorization: token
- Content-Type: application/json

### Body
The HTTP body should be a JSON with those properties:
- *entity* - the identifier of the entity provided by SISP
- *amount* - the cost of the bill
```json
{
	"amount": "999",
	"entity": "4"
}
```

### Response
The response will be a JSON with those properties:
- *success* - a boolean value that say if the bill is created successfully or not
- *message* - a description of the action done, it will be useful in case of errors
- *id* - the id of BillProvider created in Faxi
- *entity* - the identifier of the entity provided by SISP
- *amount* - the cost of the bill
- *reference* - the reference number that should be use to pay it in vinti4 channel.
```json
{
    "success": "true",
    "message": "Create bill successfully",
    "id": 1,
    "entity": 4,
    "reference": 1,
    "amount": 999
}
```