Provides a Bot REST API

1) Add a web connector in admin interface with /test relative path.

2) Send text: `curl localhost:8080/test --data '{"query":"Hello","userId":"id"}'`

response:
```
{
  "responses": [
    {
      "text": "Welcome to the Tock Open Data Bot! :)"
    },
    {
      "text": "This is a Tock framework demonstration bot: https://github.com/voyages-sncf-technologies/tock"
    },
    {
      "text": "Hey!",
      "buttons": [
        {
          "title": "Itineraries",
          "payload": "search?_previous_intent=greetings"
        },
        {
          "title": "Departures",
          "payload": "departures?_previous_intent=greetings"
        },
        {
          "title": "Arrivals",
          "payload": "arrivals?_previous_intent=greetings"
        }
      ]
    }
  ]
}
```

3) Select a button: `curl localhost:8080/test --data '{"payload":"search?_previous_intent=greetings","userId":"id"}'`
```
{
  "responses": [
    {
      "text": "For which destination?"
    }
  ]
}
```