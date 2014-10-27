Quest experiment
================
```json
{
  "states": {
    "s1": {
      "title": "Initial state",
      "contents": "Choose your drink",
      "functions": [
        {
          "title": "First choice",
          "contents": "Tea"
        },
        {
          "title": "Second choice",
          "contents": "Coffee"
        },
        {
          "title": "Third choice",
          "contents": "Beer",
          "if": {
            "equals": ["$v1", true]
          }
        }
      ]
    }
  },
  "variables": {
    "v1": {
      "title": "Is adult",
      "default": false
    }
  }
}
```
