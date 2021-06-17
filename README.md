# [Request Header Parser Microservice](https://www.freecodecamp.org/learn/apis-and-microservices/apis-and-microservices-projects/request-header-parser-microservice)

1. You should provide your own project, not the example URL.
2. A request to `/api/whoami` should return a JSON object with your IP address in the `ipaddress` key.
3. A request to `/api/whoami` should return a JSON object with your preferred language in the `language` key.
4. A request to `/api/whoami` should return a JSON object with your software in the `software` key.

## Note that the way to get the `ipaddress`, `language`, `software(browser)` 
```JavaScript
//define a json object
let resObj = {}
//route
app.enable('true proxy')
app.get('/whoami', (req, res) => {
 resObj['ipaddress'] = req.ip
 resObj['language'] = req.get('Accept-Language')
 resObj['software'] = req.get('User-Agent')
 res.json(resObj)
})
```
