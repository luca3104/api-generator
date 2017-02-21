# api-generator
Node.js RESTful API Generator

## Usage
### Create JSON file
```json
{
  "endpoint" : {
    "response-key":"response-value"
  }
}
```
### Execute node
`$ node api-gen [json file]`

### Check with curl command
`$ curl -X GET http://127.0.0.1:3000/endpoint`  
Return Value is  
`{"response-key":"response-value"}`


## Example
Create json file [test.json]
```json:test.json
{
  "test" : {
    "params":{
      "param1":"param",
      "param2":100
    }
  },
  "test/test" : {
    "param1":"param",
    "param2":{
      "param2-1":"param",
      "param2-2":100
    }
  }
}
```
Execute node command  
`$ node api-gen test.json`  
Execute curl comamnd  
`$ curl -X GET http://127.0.0.1:3000/test/test`  
Return  
`{"param1":"param","param2":{"param2-1":"param","param2-2":100}`  

## License
MIT
